# Deployment Guide – FusionFlavours

This document explains how to deploy the FusionFlavours static website on an
AWS EC2 Ubuntu instance using Nginx.

## Prerequisites
- AWS EC2 instance (Ubuntu)
- Port 80 open in Security Group
- Git installed

## Deployment Steps

1. SSH into the EC2 instance:
   ssh ubuntu@<EC2-PUBLIC-IP>

2. Update system packages:
   sudo apt update

3. Install Nginx:
   sudo apt install nginx -y

4. Clone the repository:
   git clone https://github.com/<your-username>/FusionFlavours.git
   cd FusionFlavours

5. Configure Nginx:
   sudo vim /etc/nginx/sites-available/default

   Update the root directive to:
   root /home/ubuntu/FusionFlavours;

6. Set permissions:
   sudo chmod -R 755 /home/ubuntu/FusionFlavours
   sudo chmod o+x /home/ubuntu

7. Test and reload Nginx:
   sudo nginx -t
   sudo systemctl reload nginx

8. Access the website:
   http://<EC2-PUBLIC-IP>
