# dwva-waf
This lab demonstrates a vulnerable web application (DVWA) protected by a SafeLine WAF. The setup includes an attacker (Kali Linux) and a victim (Ubuntu with DVWA), simulating attacks such as SQL Injection and observing SafeLine’s automated protections.

## Lab Setup

![Lab Environment](screenshots/01-lab-environment.png)

- Ubuntu VM: DVWA host
- Kali VM: Attacker
- Bridged networking for full connectivity

---

## Apache & DVWA Setup

**Apache listening on IPv4:**

![Apache Listening](screenshots/02-apache-listening.png)

**DVWA running locally (Ubuntu):**

![DVWA Local](screenshots/03-dvwa-local.png)

**DVWA accessible remotely (Kali):**

![DVWA Remote](screenshots/04-dvwa-remote.png)

---

## DNS Resolution

Custom hostname mapped to the WAF IP (dvwa.local) to ensure all traffic goes through SafeLine.

![DNS Resolution](screenshots/11-dns-resolution.png)

Shows that Kali resolves DVWA through the WAF, not directly to the backend.

---

## DVWA Login

**Successful login from Kali through SafeLine WAF:**

![DVWA Kali Login](screenshots/05-kali-login.png)

**DVWA Security set to Low for testing:**

![DVWA Security](screenshots/06-security-low.png)

---

## SafeLine WAF

**SafeLine dashboard showing DVWA application:**

![SafeLine Dashboard](screenshots/07-safeline-dashboard.png)

**SQL Injection attack attempt from Kali:**

![SQLi Attempt](screenshots/08-sqli_attempt.png)

**SafeLine blocking the attack:**

![SafeLine Block](screenshots/09-safeline-block.png)

**SafeLine logs showing detected attacks:**

![SafeLine Logs](screenshots/10-safeline-logs.png)

---

## Key Learnings

- Built a multi-VM lab (attacker + victim)
- Configured Apache & DVWA for remote access
- Tested vulnerabilities (SQLi) safely
- Validated WAF protections via SafeLine
- Documented attacks and logs for SOC-level insight
