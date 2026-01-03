# Deployment Guide – FusionFlavours

This document explains how to deploy the FusionFlavours static website on an
AWS EC2 Ubuntu instance using Nginx.

## Prerequisites
- AWS EC2 instance (Ubuntu)
- Port 80 open in Security Group
- Git installed

## Deployment Steps

1. SSH into the EC2 instance:
   ```bash
   ssh ubuntu@<EC2-PUBLIC-IP>
   ```

2. Update system packages:
   ```bash
   sudo apt update
   ```
3. Install Nginx:
   ```bash
   sudo apt install nginx -y
   ```
4. Clone the repository:
   ```bash
   git clone https://github.com/<your-username>/FusionFlavours.git
   ```
   ```bash
   cd FusionFlavours
   ````
5. Configure Nginx:
   ```bash
   sudo vim /etc/nginx/sites-available/default
   ```

   Update the root directive to:
   ```bash
   root /home/ubuntu/FusionFlavours;
   ```

6. Set permissions:
    ```bash
   sudo chmod -R 755 /home/ubuntu/FusionFlavours
   sudo chmod o+x /home/ubuntu
   ```

7. Test and reload Nginx:
   ```bash
   sudo nginx -t
   sudo systemctl reload nginx
   ```

8. Access the website:
   `http://<EC2-PUBLIC-IP>`

   Your Website is deployed !
   
