---
permalink: /lab/
title: "Lab Challenges"
---
---

# 🧪 Lab Challenge — Spear Phishing Awareness Simulator (Spear Phishing)

**Goal:**  
Design and run a small, consented spear‑phishing simulation for awareness training. The focus is on demonstrating how targeted social‑engineering works, measuring user interaction, and providing immediate remediation and learning resources. All data collected must be sanitized, minimal, and handled ethically.

---

## 🔒 Safety & Ethics (must-read)
- **Written permission only.** Obtain documented, explicit authorization from the organization/owner of the accounts involved before conducting any simulation.
- **Scope & limits.** Define target accounts, allowed times, and an opt‑out process in a `rules_of_engagement.md`.
- **No real credentials.** Never store real credentials. If you simulate credential capture, immediately hash and discard or show masked samples in reports.
- **Transparent remediation.** Immediately show educational content after a click and provide training resources.
- **Sanitize screenshots.** Mask real names, emails, and IP addresses before publishing.

---

## 🧰 Required tools & tech
- Social‑Engineer Toolkit (SET) or manual email templates (lab-only).  
- A local SMTP server configured to **not** relay externally (e.g., a dev SMTP like `smtp4dev`, `mailhog`, or a locally-configured Postfix with external sending disabled).  
- Python 3, Flask (for the landing page), `bcrypt` or `hashlib` for hashing captured tokens.  
- SQLite or local JSON for ephemeral logging (optional).  
- Browser (for screenshots), and a sandbox VM for target test account(s).

---

## Lab setup (lab environment)
1. Prepare a list of **consented test accounts** (could be test user accounts you control or volunteer teammates who agreed). Save as `targets.csv`.
2. Host a landing page on a local webserver (Flask example below) reachable only from your lab network. Do **not** expose to the public internet.
3. Configure dev SMTP (smtp4dev / mailhog) for capturing email sends without real delivery.
4. Ensure all participants know a remediation and support contact (e.g., security@lab.local).

---

## Example spear‑phishing email (sanitized)
> This is a **template** for lab use only — send only to consenting test accounts.

**Subject:** Action required: Update your lab account access

**From:** IT Support &lt;it-support@lab.local&gt;  
**To:** `consented_user@lab.local`

**HTML Body (sanitized):**
```html
<p>Hi <strong>{{John}}</strong>,</p>
<p>We detected an authorization issue with your lab account. Please <a href="https://winformusic.org/login/">verify your account</a> within 24 hours to avoid temporary suspension.</p>
<p>If you did not request this, contact <em>security@lab.local</em>.</p>
<p>— IT Support</p>
```

## Lab Screenshots
![My avatar](/assets/images/1.png)
