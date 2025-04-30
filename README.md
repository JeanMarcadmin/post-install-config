<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1 align="center">osTicket - Post-Installation Configuration Guide</h1>

Once osTicket is installed, it’s important to complete several configurations to ensure it is secure, fully functional, and ready for ticket management. This guide walks through the essential post-installation steps.

---

## 🧠 Purpose

This document provides best practices and configuration steps immediately **after** installing osTicket, including admin setup, email piping, system settings, and security hardening.

---

## ⚙️ Admin Dashboard Configuration

### 1. Access the Admin Panel

- Go to: `http://localhost/osticket/scp/`
- Login with the admin account created during installation

---

### 2. Rename and Secure the `ost-config.php` File

- Navigate to: `C:\inetpub\wwwroot\osticket\include\ost-config.php`
- Right-click → **Properties** → **Security**
- Remove `Everyone` or change permissions to **Read Only** for IIS/IUSR

---

### 3. Remove Setup Directory

- Delete the `setup` folder from `C:\inetpub\wwwroot\osticket\`
- This prevents re-installation or unauthorized access

---

## 📧 Email Configuration (SMTP & Fetching)

### 1. Setup Outgoing Email (SMTP)

- Admin Panel → **Emails** → **Email Addresses**
- Select your support email
- Under **SMTP Settings**, input your mail server:
  - SMTP Host: `smtp.yourdomain.com`
  - Port: `587` or `465`
  - Auth: ON
  - Username & Password: your email credentials

---

### 2. Enable Auto-Cron or Mail Fetching

- Admin Panel → **Emails** → **Settings**
- Enable:
  - Email Fetching
  - Auto-Responders
  - Alerts & Notices

> Optionally configure a scheduled task (cron job) on the server if not using auto-cron.

---

## 🧾 Ticket System Settings

### 1. Customize Help Topic Categories

- Admin Panel → **Manage** → **Help Topics**
- Add topics like:
  - IT Support
  - Hardware Request
  - Software Installation

---

### 2. Configure SLA Plans

- Admin Panel → **Manage** → **SLA Plans**
- Create custom SLAs (e.g. "High Priority – 4hr response")

---

### 3. Configure Departments

- Admin Panel → **Staff** → **Departments**
- Examples:
  - Technical Support
  - HR Support
  - Facilities

---

### 4. Add Teams and Agents

- Admin Panel → **Staff** → **Agents**
- Assign agents to teams and departments
- Set access levels (Admin, Staff)

---

## 🔒 Security and Optimization

### 1. Configure Access Control

- Force HTTPS via IIS or web.config
- Enable IP restriction or VPN access if needed

---

### 2. Update osTicket

- Always use the latest version for security patches
- Admin Panel → **Dashboard** → **System Updates**

---

### 3. Setup Backups

- Backup the following regularly:
  - MySQL Database (e.g. `osticket`)
  - `ost-config.php` and attachments folder
- Consider using automated backup scripts or Windows Task Scheduler

---

## 📸 Example Screenshots

> Replace these with your own if documenting your setup.

<p>
  <img src="https://i.imgur.com/DJmEXEB.png" width="80%" alt="Email Settings Screenshot"/>
</p>

---

## ✅ Final Checklist

- [x] `ost-config.php` is read-only and secured
- [x] Setup folder is deleted
- [x] Admin panel and agents configured
- [x] SMTP and fetch settings tested
- [x] Help topics, SLAs, and departments created
- [x] Backup routine is in place

---

## 📄 License

This project is for educational use only.

---

## 🙋‍♀️ Need Help?

- Visit [osTicket Support Forums](https://forum.osticket.com/)
- Check the [osTicket Documentation](https://docs.osticket.com/)
