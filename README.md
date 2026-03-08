# 14-cloudkicker
This project demonstrates the deployment of a secure web application on a Google Cloud Platform (GCP) virtual machine. The core objective was to implement a "Defense in Depth" strategy by using Nginx as a reverse proxy to shield a Flask backend.

**Live Deployment**

Public IP: http://34.68.50.202

Access Protocol: Standard HTTP (Port 80)

**Deployment Verification**

The following configuration has been implemented to ensure the application core is isolated from direct public access, satisfying the Cloud Dweller badge conditions:

Public Entry Point: The application is accessible via http://34.68.50.202/ (Standard HTTP Port 80).

Reverse Proxy: Nginx is configured as a shield on Port 80, forwarding traffic to the internal backend.

Backend Isolation: The Flask server is bound strictly to 127.0.0.1:5000.

Firewall Status: The GCP Cloud Firewall allows only TCP Port 80; direct external access to Port 5000 is blocked.

Confirmation: Flask bound to 127.0.0.1:5000, Nginx on 80.

**Security Confirmation** (Cloud Dweller Compliance)

To satisfy the Cloud Dweller badge conditions, the following network configuration has been verified:

Flask Binding: The application is bound strictly to 127.0.0.1:5000. It is hidden from the public internet and only accessible locally by Nginx.

Nginx Configuration: Nginx is listening on Port 80 and acting as the sole public gateway.

Firewall Hardening: The GCP Cloud Firewall permits traffic only on Port 80. Direct external access to Port 5000 is blocked.

**Technical Stack**

OS: Ubuntu 24.04 LTS (GCP e2-micro)

Development Platform: Kali Linux

Backend: Python 3 + Flask Framework

Web Server: Nginx (Reverse Proxy)

Environment: Python Virtual Environments (venv)

🏅 Accomplishments
**Cloud Dweller Badg**e: Successfully verified that the application is publicly accessible via the IP address without direct exposure of the Flask development server.
