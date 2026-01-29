# 📋 Step 6: Ticket Documentation

## Writing It Down (The Most Underrated Skill!)

You might think: "I'm in IT to work with computers, not write essays!"

But here's the truth: **Documentation is 50% of the job.**

---

## 🤔 Why Documentation Matters

### For Your Team
- Someone else can fix the same issue later
- Night shift can understand what day shift did
- New employees can learn from past tickets

### For You
- Prove you did the work
- Remember what you did 6 months ago
- Cover yourself if something goes wrong

### For the Company
- Legal requirements (some industries)
- Auditing and compliance
- Knowledge doesn't leave when people quit

---

## 😬 Bad vs Good Documentation

### ❌ Bad Documentation
```
Ticket #1042
Fixed the issue.
Status: Closed
```

**Problems:**
- What issue?
- How did you fix it?
- What if it happens again?
- Useless for everyone!

### ✅ Good Documentation
```
Ticket #1042 - Web Server Down
==============================
PRIORITY: HIGH

ISSUE: Website completely unreachable. Marketing received customer complaints.

ROOT CAUSE: Apache (httpd) was not installed on server.

RESOLUTION:
1. Installed httpd: sudo dnf install httpd -y
2. Started service: sudo systemctl start httpd
3. Enabled on boot: sudo systemctl enable httpd

VERIFICATION: Tested with curl - received "It works!" response.

STATUS: RESOLVED
```

**Why this is good:**
- ✅ Anyone can understand the issue
- ✅ Steps are clear and repeatable
- ✅ Verified the fix worked
- ✅ Future reference for similar issues

---

## 📝 The Ticket Template

Use this template for every ticket:

```
TICKET #[NUMBER] - [SHORT TITLE]
================================
PRIORITY: [HIGH / MEDIUM / LOW]

CUSTOMER ISSUE:
- What did they report? (Use their words!)

ENVIRONMENT:
- Server: [IP or hostname]
- OS: [RHEL 9, etc.]

INVESTIGATION:
- What did you check first?
- What commands did you run?
- What did you find?

ROOT CAUSE:
- What was actually wrong? (The real problem, not symptoms)

RESOLUTION:
1. First thing you did
2. Second thing you did
3. Third thing you did
(Include exact commands!)

VERIFICATION:
- How did you confirm it's fixed?
- What was the result?

STATUS: [RESOLVED / ESCALATED / IN PROGRESS]
Time to Resolution: [How long it took]

NOTES:
- Anything else worth mentioning
- Recommendations to prevent this in future
```

---

## 🎯 Priority Levels

When you receive a ticket, how urgent is it?

| Priority | Meaning | Response Time | Example |
|----------|---------|---------------|---------|
| 🔴 **HIGH/P1** | Business stopped | Within 15 min | Website down, can't take orders |
| 🟡 **MEDIUM/P2** | Significant impact | Within 2 hours | Email slow but working |
| 🟢 **LOW/P3** | Minor inconvenience | Within 24 hours | One user can't print |

---

## 📖 Real Example: Our Web Server Ticket

Let's document the web server issue we fixed earlier:

![Ticket Example](screenshots/ticket-example.png)

```
TICKET #1042 - Web Server Down
================================
PRIORITY: HIGH / P1

CUSTOMER ISSUE:
- Marketing reported: "Website is completely down!"
- Customers calling to complain they can't access site
- Business impact: Sales affected

ENVIRONMENT:
- Server: 192.168.56.10
- OS: RHEL 9
- Service: Apache HTTP Server (httpd)

INVESTIGATION:
- Connected via SSH: ssh pedro@192.168.56.10
- Checked service status: sudo systemctl status httpd
- Found: "Unit httpd.service could not be found"

ROOT CAUSE:
- Apache web server (httpd) was not installed on the server
- Likely missed during initial server setup

RESOLUTION:
1. Installed Apache:
   sudo dnf install httpd -y
   
2. Started the service:
   sudo systemctl start httpd
   
3. Enabled auto-start on boot:
   sudo systemctl enable httpd

VERIFICATION:
- Checked status: sudo systemctl status httpd
  Result: "active (running)"
  
- Tested website: curl http://localhost
  Result: Received "It works!" HTML response
  
- Marketing confirmed site is accessible

STATUS: RESOLVED
Time to Resolution: 10 minutes

NOTES:
- Recommend adding httpd installation to standard server build checklist
- Consider implementing monitoring to detect service failures
- Created Ansible playbook to prevent this on future servers
```

---

## ✍️ Writing Tips

### Be Specific, Not Vague

| ❌ Vague | ✅ Specific |
|---------|-----------|
| "Checked the server" | "Ran: sudo systemctl status httpd" |
| "Restarted stuff" | "Restarted Apache: sudo systemctl restart httpd" |
| "Fixed permissions" | "Changed ownership: sudo chown pedro:pedro /home/pedro" |

### Include Exact Commands

```
❌ "I installed the web server"

✅ "Installed Apache:
    sudo dnf install httpd -y
    Output: Complete!"
```

### Use the Customer's Words

```
❌ ISSUE: HTTP service non-functional

✅ ISSUE: Customer reported "Website is completely down! 
   Customers are calling to complain!"
```

---

## 🚀 When to Escalate

Sometimes you can't fix the issue. That's OK! But document what you tried:

```
TICKET #1099 - Database Connection Errors
=========================================
PRIORITY: HIGH

CUSTOMER ISSUE:
- Application showing "Cannot connect to database"

INVESTIGATION:
1. Checked database service: running ✓
2. Checked network connectivity: OK ✓
3. Checked firewall: Port 3306 open ✓
4. Tested connection: mysql -u app -p
   ERROR 1045 (Access denied for user 'app')

ROOT CAUSE:
- Appears to be database user permission issue
- Beyond Tier-1 scope

WHAT I TRIED:
- Verified service is running
- Confirmed network is working
- Tested credentials (failed)

ESCALATION REASON:
- Database permission issues require DBA access
- Tier-1 does not have MySQL admin credentials

STATUS: ESCALATED TO TIER-2
Time Spent: 25 minutes
```

**Key point:** Even when escalating, show what you DID do. This helps the next person!

---

## 📊 Documentation Checklist

Before closing a ticket, verify:

| Check | Item |
|-------|------|
| ⬜ | Issue clearly described |
| ⬜ | Environment documented (server, IP, OS) |
| ⬜ | Investigation steps listed |
| ⬜ | Root cause identified |
| ⬜ | Resolution includes exact commands |
| ⬜ | Verification proves it's fixed |
| ⬜ | Status is accurate |
| ⬜ | Would a coworker understand this? |

---

## 💡 Key Lessons

1. **Write for someone else** - Pretend you're explaining to a new coworker

2. **Commands > Descriptions** - "I ran `sudo systemctl start httpd`" beats "I started the service"

3. **Document failures too** - What DIDN'T work is valuable information

4. **Write as you work** - Don't wait until the end; you'll forget details

5. **Quality over speed** - Taking 5 extra minutes to document saves hours later

---

## 🎓 You've Completed the Training!

Congratulations! 🎉 You've learned:

| Skill | What You Can Do |
|-------|-----------------|
| **Lab Setup** | Build virtual environments |
| **User Management** | Create, modify, delete users |
| **Service Troubleshooting** | Fix broken services |
| **Ansible Automation** | Automate tasks across servers |
| **Container Management** | Run containerized applications |
| **Documentation** | Write professional ticket notes |

---

## 🚀 What's Next?

### Keep Practicing
- Redo these exercises from memory
- Break things on purpose and fix them
- Create new scenarios

### Get Certified
- Red Hat Certified System Administrator (RHCSA)
- The company in the job posting will help you get this!

### Build Your Portfolio
- Add this project to your GitHub
- Screenshot your work
- Reference it in interviews

---

## 📧 Final Notes

When interviewing, you can now confidently say:

> "I built a 3-node RHEL lab from scratch, including a controller for Ansible automation. I practiced common Tier-1 scenarios like user management, service troubleshooting, and container deployment. I documented everything following professional ticketing standards."

**That's impressive for any entry-level IT position!**

---

## 📸 Screenshots for This Section

| Screenshot | Description |
|------------|-------------|
| ticket-example.png | Example of well-documented ticket |

---

## 🏠 Back to Main Page

[← Return to Project Overview](../README.md)

---

*Congratulations on completing the RHEL Tier-1 Support Lab! 🎓*
