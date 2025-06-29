# ⚠️ Challenges Faced – Host-Based IDS (OSSEC) Setup

---

## 🧩 Repository & Package Issues

- Faced GPG key error while running `apt update`  
- Error: `NO_PUBKEY ED65462EC8D5E4C5`  
- Kali's repo changed from `non-free` to `non-free-firmware`  
- Solution: Manually updated `/etc/apt/sources.list`  
- Reference: [Kali Blog - Non-Free Firmware](https://www.kali.org/blog/non-free-firmware-transition)  
- Lesson: Always verify source lists before modifying  

---

## 📦 Missing Dependencies

- `libssl-dev`, `lsystemd`, and other dependencies were missing  
- Errors: `Unable to locate package`, `ld: cannot find -lsystemd`  
- Solution: Ran updates, fixed held packages, retried installs  
- Command used: `sudo apt --fix-broken install`  
- Lesson: Dependency resolution is a critical step in Linux installs  

---

## 🛠️ Build & Install Errors

- During `make`, encountered:  
  `make: *** [Makefile:930: ossec-maild] Error 1`  
- Related to missing OpenSSL headers  
- Solved by installing `libssl-dev` and dependencies manually  
- Lesson: Always install required libraries before compiling  

---

## 📧 Email Configuration Problems

- Error when starting OSSEC: `Invalid SMTP Server`  
- SMTP not set in `<smtp_server>` tag  
- Solution: Disabled email alerts:  
  `<email_notification>no</email_notification>`  
- Lesson: Default configs must be adjusted or disabled properly  

---

## 🧪 Final Testing & Validation

- Ran `sudo /var/ossec/bin/ossec-control start` successfully  
- Verified services via logs in `/var/ossec/logs/ossec.log`  
- Took screenshots for portfolio and GitHub README  
- Lesson: Every failed attempt improved troubleshooting skills  

---
