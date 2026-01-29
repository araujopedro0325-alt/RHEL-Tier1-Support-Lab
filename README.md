# 🐧 RHEL Tier-1 Support Lab

## Learn Linux System Administration - A Beginner's Guide

Welcome! This project will teach you how to be a **Linux System Administrator** - specifically for Red Hat Enterprise Linux (RHEL), one of the most popular operating systems used by businesses worldwide.

---

## 🤔 What is This Project?

Imagine you're an IT support person at a company. When something breaks (a website goes down, a user can't log in, etc.), YOU are the person who fixes it.

This project simulates that experience by:
1. Building a mini "company network" on your computer
2. Breaking things on purpose
3. Teaching you how to fix them

**By the end, you'll have real skills that employers want!**

---

## 🎯 Who is This For?

- ✅ Complete beginners to Linux
- ✅ People switching careers to IT
- ✅ Students learning system administration
- ✅ Anyone preparing for help desk or support roles

**No prior experience needed!** I'll explain everything.

---

## 🖥️ What We're Building

We're creating 3 virtual computers (called Virtual Machines or "VMs") that talk to each other:

```
    YOUR COMPUTER
         │
         ▼
┌─────────────────────────────────────────────────┐
│           VirtualBox (Free Software)            │
│                                                 │
│  ┌─────────────┐ ┌─────────────┐ ┌───────────┐  │
│  │  CONTROLLER │ │   SERVER    │ │  CLIENT   │  │
│  │  (The Boss) │ │  (Website)  │ │  (Worker) │  │
│  └─────────────┘ └─────────────┘ └───────────┘  │
│                                                 │
└─────────────────────────────────────────────────┘
```

**Think of it like this:**
- **Controller** = The IT admin's computer (sends commands)
- **Server** = The company's website/application server
- **Client** = An employee's work computer

---

## 🛠️ Software You'll Need (All Free!)

| Software | What It Does | Where to Get It |
|----------|--------------|-----------------|
| **VirtualBox** | Creates virtual computers | [virtualbox.org](https://www.virtualbox.org/) |
| **RHEL** | The operating system | [Red Hat Developer](https://developers.redhat.com/) (free account) |
| **Termius** | Connects to your VMs | [termius.com](https://termius.com/) (free version) |

---

## 📚 What You'll Learn

| Skill | Real-World Use |
|-------|----------------|
| **Creating Users** | "New employee starting Monday - set up their account" |
| **Managing Services** | "The website is down - fix it!" |
| **Ansible Automation** | "Do this task on 100 servers at once" |
| **Containers** | "Run applications in isolated boxes" |
| **Documentation** | "Write notes so others can learn from your fix" |

---

## 📖 Table of Contents

Start from the beginning and work your way through:

| Step | Topic | Time Needed | Difficulty |
|------|-------|-------------|------------|
| 1 | [Lab Setup](./01-Lab-Setup/) | 2-3 hours | ⭐ Easy |
| 2 | [User Management](./03-User-Management/) | 30 min | ⭐ Easy |
| 3 | [Service Troubleshooting](./04-Service-Troubleshooting/) | 30 min | ⭐⭐ Medium |
| 4 | [Ansible Automation](./05-Ansible-Automation/) | 45 min | ⭐⭐ Medium |
| 5 | [Container Management](./06-Container-Management/) | 30 min | ⭐⭐ Medium |
| 6 | [Ticket Documentation](./07-Ticket-Documentation/) | 20 min | ⭐ Easy |

**Total time: About 5-6 hours** (can be spread over multiple days)

---

## 💡 Tips Before You Start

### Take Your Time
- Don't rush! Understanding is more important than speed
- If something doesn't work, that's GOOD - troubleshooting is a skill!

### Take Screenshots
- Screenshot your work as you go
- Great for your portfolio and remembering what you did

### Ask for Help
- Google is your friend
- Linux forums are very helpful
- Error messages tell you what's wrong (read them!)

---

## 🎓 After Completing This Project

You'll be able to say in interviews:

> "I built a 3-node RHEL lab environment from scratch. I practiced user management, service troubleshooting, and automation with Ansible. I also worked with containers using Podman and documented everything following professional standards."

**That's impressive for an entry-level candidate!**

---

## 📋 Quick Reference

See the [Command Cheatsheet](./cheatsheet.md) for all commands used in this project.

---

## 📧 Contact

**[Pedro Araujo]**
- LinkedIn: [www.linkedin.com/in/pedro-araujo-472297390]


---

## ⭐ If This Helped You

Give this repo a star! It helps others find it.

---

*Built with ❤️ for aspiring Linux administrators*
