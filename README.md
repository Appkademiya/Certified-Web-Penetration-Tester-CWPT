# Appkademiya Certified Web Penetration Tester (CWPT) 🌐

Welcome to the official practical lab for the **Certified Web Penetration Tester (CWPT)** exam.

Modern web applications are the primary attack surface for most organizations. This certification tests a candidate's ability to identify, exploit, and chain common web application vulnerabilities (OWASP Top 10) in a realistic corporate portal.

You will start with zero knowledge of the application and must progressively find vulnerabilities to escalate your privileges, achieve remote code execution (RCE), and ultimately dump the backend database.

---

## 🏗️ Lab Architecture

This cyber range consists of a two-tier architecture:

1. **Corporate Web Portal:** An exposed Apache/PHP web application running on port `8080`.
2. **Backend Database:** A highly restricted, internal-only MySQL database containing sensitive corporate secrets.

---

## 🛠️ Prerequisites

- [Docker Desktop](https://www.docker.com/products/docker-desktop/) or Docker Engine installed.
- A penetration testing OS (Kali Linux, Parrot OS, or a custom Linux setup).
- A web browser and intercepting proxy (e.g., Burp Suite Community Edition or OWASP ZAP).
- Standard web exploitation tools (e.g., Gobuster/Dirb, SQLMap, `curl`).

---

## 🚀 Getting Started

### 1. Launch the Cyber Range

Clone this repository and spin up the environment using Docker Compose:

```bash
git clone https://github.com/Appkademiya/Certified-Web-Penetration-Tester-CWPT-.git
cd Certified-Web-Penetration-Tester-CWPT-
docker-compose up -d
```

> **Note:** Docker will automatically pull the pre-built, obfuscated lab images from the Appkademiya Docker Hub registry.

### 2. Access the Target

Once the containers are running, open your web browser and navigate to:

```
http://localhost:8080
```

---

## 🎯 Exam Objectives

Your goal is to extract **10 Flags** formatted as `FLAG{...}` by exploiting different vulnerabilities across the application. Submit these flags into the Appkademiya Certification Engine to earn your CWPT badge.

Here is your attack path:

1. **Reconnaissance:** Enumerate directories and inspect hidden webmaster files to find leaked source code.
2. **Authentication Bypass:** Exploit SQL Injection to bypass the staff login portal.
3. **Broken Access Control:** Use Insecure Direct Object References (IDOR) to access confidential invoices.
4. **Session Manipulation:** Forge or manipulate your session cookies to elevate your privileges.
5. **Local File Inclusion (LFI):** Abuse path traversal flaws to read local system files (e.g., `/etc/passwd`).
6. **Unrestricted File Upload:** Bypass upload filters to drop a payload onto the server.
7. **Server-Side Request Forgery (SSRF):** Trick the application into querying its own internal administrative services.
8. **Command Injection:** Exploit a network diagnostic tool to achieve Remote Code Execution (RCE).
9. **Database Extraction:** Use your access to dump the master secrets from the isolated backend database.

---

## 🛑 Teardown

When you are finished with the exam, or if you need to reset the environment to a clean state, run:

```bash
docker-compose down
```

To completely wipe the environment (including any uploaded files or database changes) and start fresh, run:

```bash
docker-compose down -v
```

---

Good luck, and happy hacking!
