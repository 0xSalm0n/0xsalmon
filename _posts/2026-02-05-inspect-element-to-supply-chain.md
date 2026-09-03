---
layout: post
title: "From Client-Side JavaScript to GitHub Admin: A Supply Chain Exposure"
date: 2026-02-05 17:00:00 +0530
categories: [Bug Bounty, Web Security]
tags: [supply-chain, github, secrets-exposure, recon, javascript]
image:
  path: /assets/img/admin-access.jpg
  alt: OAuth Security Vulnerability
author: Salmon Kumar
---

**TL;DR:** During testing of a private bug bounty program, I discovered a live GitHub token with administrative access exposed inside a production JavaScript bundle. The token allowed write access to internal repositories and posed a potential supply-chain risk. The issue was responsibly disclosed and fully remediated before publication.  
All identifying details have been modified or generalized.

---

## Why Manual JavaScript Recon Still Matters

Most bug bounty workflows today are heavily automated. That’s efficient, but automation misses context. Some of the highest-impact findings still come from manually reading client-side JavaScript and understanding how modern build pipelines work.

While testing a web application as part of a private program, I followed a standard recon process:

- Reviewed client-side bundles in DevTools  
- Checked network calls and configuration objects  
- Looked for environment variables embedded during build  
- Searched for common secret patterns  

Eventually, a large bundled file stood out. It contained configuration values that clearly didn’t belong on the client side.

---

## The Discovery: Secrets in a Production Bundle

Inside a minified JavaScript bundle, I found several environment-style variables that appeared to be injected during the build process. Among them were several sensitive credentials, including a Slack Webhook URL and a high-privileged GitHub token.

This immediately raised a few questions:

1. Is the token still valid?  
2. What permissions does it have?  
3. Does it belong to a service account?  

Client-side bundles should **never** contain long-lived credentials. Even if scoped narrowly, exposure creates unnecessary risk.

---

## Responsible Verification

When validating exposed credentials, the objective is to confirm impact without interacting with sensitive data or modifying any assets.

To do this safely, I performed a series of minimal, non-destructive checks using the GitHub API. The goal was only to verify:

- Whether the token was active  
- Whether it belonged to an internal automation account  
- Whether it had elevated permissions  

No repositories were cloned, no code was accessed, and no changes were made at any stage.

### Token Validity Check

### Step 1: Identity Verification

```bash
curl -H "Authorization: token ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" https://api.github.com/user

```

**Response:**

```json
{
  "login": "internal-service-account",
  "id": 9XXXXX,
  "type": "User",
  "site_admin": false
}

```

**Result:** The token belongs to an active service account (`internal-service-account`).

### Step 2: Organization Access

```bash
curl -H "Authorization: token ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" https://api.github.com/user/orgs

```

**Result:** The account is a member of the target organization (**TheOrg**).

### Step 3: Privilege Assessment

```bash
curl -H "Authorization: token ghp_xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx" \
  https://api.github.com/user/repos?type=private&per_page=5

```

**Response (Redacted):**

```json
[
  {
    "name": "[REDACTED-1]",
    "private": true,
    "permissions": { "admin": true, "push": true, "pull": true }
  },
  {
    "name": "[REDACTED-2]",
    "private": true,
    "permissions": { "admin": true, "push": true, "pull": true }
  }
  ....
]

```
This demonstrated that the exposed token had administrative and write access to private repositories, creating a potential supply-chain risk if abused.

All verification steps were performed responsibly and within the scope of the bug bounty program. The affected credentials were revoked by the organization before this write-up was published.


## 4. Business Impact Analysis

The exposure of this credential represented a critical risk to the organization's supply chain:

1. **CI/CD Pipeline Compromise:** With write access to the repositories, an attacker could inject malicious code into the build pipeline, leading to automatic deployment of backdoors in production.
2. **Intellectual Property Theft:** Full access to clone and download all private repositories containing business logic and proprietary algorithms.
3. **Infrastructure Control:** Administrative privileges allowed for the modification of repository settings, removal of branch protections, or addition of malicious collaborators.
4. **Internal Phishing:** The exposed Slack webhook permitted posting authenticated messages to internal channels, increasing the success rate of social engineering attacks.

## 5. Timeline & Resolution

* **Day 1:** Vulnerability reported.
* **Day 1 (+2 hours):** Initial response received; Proof of Concept provided.
* **Day 1 (+4 hours):** Issue triaged.
* **Day 4:** **$1,700** Bounty awarded.

### Additional Findings

During the remediation phase, I identified a second JavaScript bundle leaking an **AWS Access Key** (S3 Write Access) and a **Stripe Secret Key**. These were immediately reported and included in the credential rotation plan.

## 6. Key Takeaways

1. **Manual Analysis is Critical:** Automated scanners often miss context-specific leaks in build artifacts. Inspecting Webpack chunks paths in client-side code is a high-value methodology.
2. **Responsible Verification:** Impact can be demonstrated using API metadata (scopes, user info) without accessing or exfiltrating private code.
3. **Build Pipeline Security:** Ensure that server-side environment variables are strictly separated from client-side bundles during the build process.

— **Salmon Kumar**

*Disclaimer: All sensitive details have been redacted to adhere to responsible disclosure guidelines.*
