# 🚀 EC2 Web Server - Manual Bootstrapping using nano (By Subir)

This project demonstrates how to manually set up a web server on an AWS EC2 instance. Instead of automation tools, the server is bootstrapped using hands-on CLI work, manual editing with `nano`, and SSH access for real-world learning.

---

## What was done:

- Launched an EC2 instance (Amazon Linux 2)
- Configured security groups for:
  - **Port 22 (SSH)**
  - **Port 80 (HTTP)**
- SSH’d into the EC2 instance using a key pair
- Installed and started Apache (`httpd`)
- Used `nano` to manually create an `index.html` file
- Displayed dynamic content using Linux commands: hostname & public IP
- Successfully served the webpage publicly

**Keynote:** Public IP changes on every start/stop instances as of this learning

<img width="1366" height="768" alt="ec2_webserver" src="https://github.com/user-attachments/assets/f07c1f47-459a-4d92-acca-9a078881803c" />
