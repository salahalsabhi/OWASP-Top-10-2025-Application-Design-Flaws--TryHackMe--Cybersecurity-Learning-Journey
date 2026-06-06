# OWASP-Top-10-2025-Application-Design-Flaws--TryHackMe--Cybersecurity-Learning-Journey
I just completed OWASP Top 10 2025: Application Design Flaws room on TryHackMe! Learn about A02, A03, A06, and A10 and how they related to design flaws in the application.


# OWASP Top 10 2025 – Application Design Flaws (TryHackMe Room Write-up)

## 🧠 Overview
This repository documents my completion of the **OWASP Top 10 2025: Application Design Flaws** TryHackMe room.  
The focus of this room is understanding how insecure *design decisions* (not just coding bugs) can lead to critical vulnerabilities.

It covers real-world attack patterns related to:
- A02: Broken Authentication
- A03: Injection
- A06: Vulnerable & Outdated Components
- A10: Server-Side Request Forgery (SSRF) / Design-level trust issues (context-dependent in 2025 mapping)

---

## 🎯 Objectives
- Understand how insecure design leads to exploitable applications
- Identify weaknesses in authentication logic
- Exploit injection flaws (SQLi)
- Recognize risks from outdated or vulnerable dependencies
- Explore SSRF and trust boundary issues
- Practice real-world exploitation techniques in a controlled lab

---

## 🔐 Key Concepts Learned

### 🟠 A02 – Broken Authentication
- Weak login logic and poor session handling
- Trusting client-side input (e.g., cookies, headers, User-Agent)
- Missing rate-limiting and brute-force protections

**Key takeaway:**  
Authentication must never rely on client-controlled data.

---

### 🟡 A03 – Injection
- SQL Injection via GET parameters (`search` parameter vulnerability)
- Boolean-based blind SQLi
- Error-based SQLi
- Time-based blind SQLi
- Stacked queries (PostgreSQL)

**Key takeaway:**  
All user input must be treated as untrusted and parameterized queries should always be used.

---

### 🔵 A06 – Vulnerable & Outdated Components
- Exposure of system details (Linux kernel, Apache version, PostgreSQL version)
- Risk of known CVEs in outdated software stacks
- Information disclosure helps attackers pivot faster

**Key takeaway:**  
Security patches and version hygiene are part of application design, not optional maintenance.

---

### 🔴 A10 – SSRF / Trust Boundary Failures (Design Flaw Category)
- Server trusting attacker-controlled headers (e.g., User-Agent, X-Forwarded-For)
- Device-based access control bypass (mobile-only logic)
- Improper trust in client-side identity signals

**Key takeaway:**  
Never trust client-provided metadata for access control decisions.

---

## 🧪 Lab Summary

### Target 1 – SQL Injection Discovery
- Endpoint: `search` parameter
- Confirmed PostgreSQL backend
- Multiple injection types identified:
  - Boolean-based blind
  - Error-based
  - Time-based blind
  - Stacked queries

---

### Target 2 – Design Flaw (Mobile-Only Access Control)
- Application restricted access based on User-Agent
- Bypass tested using curl with spoofed headers
- Demonstrated insecure design assumption:
  > “Only mobile devices will access this service”

**Result:** Access control based on User-Agent is not secure.

---

## 🛠 Tools Used
- `curl`
- `sqlmap`
- Linux terminal
- Browser dev tools (inspection)
- TryHackMe lab environment

---

## 📌 Key Security Lessons
- Security must be enforced server-side, not inferred from client behavior
- Design flaws are often more dangerous than coding bugs
- Attackers can fully control HTTP headers and parameters
- SQL injection remains one of the most critical real-world vulnerabilities
- Version disclosure significantly increases attack surface

---

## 🚀 Conclusion
This lab reinforced the importance of secure application design principles.  
Most vulnerabilities exploited were not complex coding mistakes, but **fundamental trust issues in application architecture**.

Understanding design flaws is essential for both offensive security (pentesting) and defensive development (secure coding).

---
LinkedIn: [
X :[https://x.com/charisma1385/status/2063350573802406133]


#OWASP #CyberSecurity #TryHackMe #Pentesting #WebSecurity #SQLInjection #SSRF #Authentication #Infosec #Hacking #EthicalHacking #ApplicationSecurity #SecurityResearch #Linux #PostgreSQL
