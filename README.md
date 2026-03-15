<div align="center">

<img src="https://img.shields.io/badge/⚓-MARINENET-0a1628?style=for-the-badge&logoColor=c9a84c" alt="MarineNet"/>

# MarineNet — Vulnerable Web Application

### A One Piece themed intentionally vulnerable web machine for cybersecurity training

[![Docker Pulls](https://img.shields.io/docker/pulls/anv1000/marinesnet?style=flat-square&logo=docker&logoColor=white&color=2496ED)](https://hub.docker.com/r/anv1000/marinesnet)
[![Docker Image Size](https://img.shields.io/docker/image-size/anv1000/marinesnet/latest?style=flat-square&logo=docker&logoColor=white&color=2496ED)](https://hub.docker.com/r/anv1000/marinesnet)
[![License](https://img.shields.io/badge/License-MIT-gold?style=flat-square)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-Docker-blue?style=flat-square&logo=docker)](https://hub.docker.com/r/anv1000/marinesnet)
![NodeJS](https://img.shields.io/badge/Node.js-20-green?style=flat-square&logo=node.js)
![Vulnerabilities](https://img.shields.io/badge/Vulnerabilities-15+-red?style=flat-square)

<br/>

> **⚠️ WARNING: This application is intentionally vulnerable.**
> It is designed for **educational and security training purposes only**.
> **Never deploy on a public server or production environment.**

<br/>

</div>

---

## 📖 About

**MarineNet** is a deliberately vulnerable web application themed around the *One Piece* anime universe. Students play the role of attackers attempting to compromise the Marine Headquarters internal intelligence portal — complete with pirate databases, classified files, bounty records, finance systems, and personnel management.
Built specifically for hands-on web application penetration testing training.



---

## 🚀 Quick Start

### Prerequisites
- [Docker Desktop](https://www.docker.com/products/docker-desktop/) installed
- That's it — no Node.js, no npm, no configuration needed

### ▶️ Run with Docker (one command)

```bash
docker run -d -p 3000:3000 --name marinenet anv1000/marinesnet
```

Then open your browser:

```
http://localhost:3000
```

### 🐙 Run with Docker Compose

```yaml
version: '3.8'
services:
  marinenet:
    image: anv1000/marinesnet
    container_name: marinenet-lab
    ports:
      - "3000:3000"
    restart: unless-stopped
```

```bash
docker compose up -d
```

---

## 🛠️ Managing the Lab

```bash
# ▶  Start the lab
docker start marinenet

# ⏹  Stop the lab
docker stop marinenet

# 🔄  Reset to a clean state (wipes the database)
docker rm -f marinenet
docker run -d -p 3000:3000 --name marinenet anv1000/marinesnet

# 📋  View live logs
docker logs -f marinenet

# 🗑️  Remove everything
docker rm -f marinenet
docker rmi anv1000/marinesnet
```

---

## 🎯 Vulnerabilities Covered

MarineNet contains **15+ intentional vulnerabilities** spanning the OWASP Top 10 and beyond. Find and exploit them independently.

| # | Category | OWASP Reference |
|---|----------|----------------|
| 01 | SQL Injection | A03:2021 |
| 02 | Stored Cross-Site Scripting (XSS) | A03:2021 |
| 03 | Reflected Cross-Site Scripting (XSS) | A03:2021 |
| 04 | HTML Injection | A03:2021 |
| 05 | Insecure Direct Object Reference (IDOR) | A01:2021 |
| 06 | Broken Authentication | A07:2021 |
| 07 | Broken Access Control | A01:2021 |
| 08 | Sensitive Data Exposure | A02:2021 |
| 09 | IDOR on Classified Records | A01:2021 |
| 10 | OS Command Injection | A03:2021 |
| 11 | Path Traversal | A01:2021 |
| 12 | Open Redirect | A01:2021 |
| 13 | Insecure Cookie Configuration | A07:2021 |
| 14 | Mass Assignment | A04:2021 |
| 15 | Verbose Error / Stack Trace Exposure | A05:2021 |

> 🔒 Vulnerability locations and exploitation methods are intentionally **not disclosed** in this README. Discover and exploit them independently.

---

## 🗺️ Application Map

```
MarineNet Portal
│
├── /                   → Public landing page
├── /login              → Authentication portal
├── /dashboard          → Marine HQ overview & announcements
├── /pirates            → Pirate intelligence database (searchable)
├── /pirates/:id        → Individual pirate dossier
├── /bounties           → Active bounty board
├── /files              → Classified document repository
├── /files/:id          → Document viewer
├── /messages           → Internal secure messaging
├── /profile            → Personnel record viewer/editor
├── /search             → Global search across all records
├── /finance            → Finance division records (restricted)
├── /admin              → Fleet Admiral control panel (restricted)
├── /admin/ping         → Network diagnostic tool (restricted)
└── /api/               → Internal API endpoints
```

---

## 👥 User Roles

The application has three access levels. Credentials are provided separately to course instructors.

| Role | Access |
|------|--------|
| **admin** | Full system access — users, logs, all data, network tools |
| **finance** | Finance records, budgets, bounty payment logs |
| **soldier** | Pirate database, bounty board, files, messaging |

---

## 🧰 Recommended Tools

| Tool | Purpose |
|------|---------|
| [Burp Suite Community](https://portswigger.net/burp/communitydownload) | HTTP interception, SQLi, XSS |
| [OWASP ZAP](https://www.zaproxy.org/) | Automated scanning |
| [sqlmap](https://sqlmap.org/) | SQL injection automation |
| [ffuf](https://github.com/ffuf/ffuf) | Directory and endpoint fuzzing |
| Browser DevTools | Cookie inspection, JS analysis |

---

## 🏗️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Runtime | Node.js 20 |
| Framework | Express.js |
| Database | sql.js (SQLite) |
| Templates | EJS |
| Container | Docker (node:20-alpine) |

---

## 🐳 Build from Source

```bash
# Clone the repository
git clone https://github.com/anv1000/marinenet-lab.git
cd marinenet-lab

# Build image locally
docker build -t marinenet-lab .

# Run locally built image
docker run -d -p 3000:3000 --name marinenet marinenet-lab
```

---

## ⚖️ Legal & Ethical Use

This tool is provided for **authorized security education only**.

- ✅ Use on your own machine for learning
- ✅ Use in classroom / CTF environments with student consent
- ✅ Use on isolated lab networks
- ❌ Do NOT expose to the public internet
- ❌ Do NOT use techniques learned here against systems you do not own
- ❌ Do NOT use for any malicious or unauthorized activity

The authors are not responsible for misuse of this software. By using MarinesNet, you agree to use it only for lawful, ethical security training.

---

## 📜 License

Permission is granted only to students and individual learners to use this Application for personal cybersecurity training purposes.

Copying, modifying, redistributing, sublicensing, commercial use, corporate training use, institutional use, and deployment in paid educational platforms are strictly prohibited without prior written permission from the author.

www.linkedin.com/in/abhinavnathv

This application must only be used in isolated lab environments and must not be deployed on public production systems.

---

## 🙏 Acknowledgements

Inspired by:
- [DVWA](https://dvwa.co.uk/) — Damn Vulnerable Web Application
- [WebGoat](https://owasp.org/www-project-webgoat/) — OWASP WebGoat
- [One Piece](https://onepiece.com/) — Eiichiro Oda (theme and lore)

---

<div align="center">

**⚓ Marine Headquarters — 「正義」JUSTICE ⚓**

Made with ❤️ for the cybersecurity training community

[![Docker Hub](https://img.shields.io/badge/Docker%20Hub-anv1000%2Fmarinesnet-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://hub.docker.com/r/anv1000/marinesnet)

</div>
