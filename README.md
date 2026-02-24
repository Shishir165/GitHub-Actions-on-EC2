GitHub Actions on EC2 – Static Site Deployment

This project demonstrates how to deploy a static website to an EC2 instance using GitHub Actions.
On every push to the main branch, the site is automatically copied to an Ubuntu EC2 server and served using Nginx.

🚀 What This Project Does

Uses GitHub Actions for CI/CD

Connects to EC2 via SSH

Copies static files (HTML, CSS, JS) to the server

Deploys the site to Nginx web root

Reloads Nginx after deployment

🛠️ Tech Stack

GitHub Actions

AWS EC2 (Ubuntu 22.04)

Nginx

SSH (appleboy scp & ssh actions)

📁 Project Structure
.
├── index.html
├── style.css
├── main.js
└── .github/
    └── workflows/
        └── deploy.yml
🔐 Required GitHub Secrets

Set these in Repository → Settings → Secrets → Actions:

Secret Name	Description
EC2_HOST	EC2 public IPv4 address
EC2_USER	ubuntu
EC2_SSH_KEY	Private SSH key for EC2
🌐 Deployment

The site is deployed to:

/var/www/html

Nginx serves the site on port 80

Deployment triggers on:

Push to main

Manual trigger (workflow_dispatch)

✅ Result

After a successful workflow run, visiting the EC2 public IP in a browser displays the deployed static website.

📌 Notes

SSH (port 22) must be open in the EC2 security group

HTTP (port 80) must be allowed

This setup is intended for learning/lab purposes
