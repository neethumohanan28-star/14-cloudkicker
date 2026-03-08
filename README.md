# 14-cloudkicker
This project demonstrates the deployment of a secure, production-ready web application on a Google Cloud Platform (GCP) virtual machine. The core objective was to implement a "Defense in Depth" strategy by using Nginx as a reverse proxy to shield a Flask backend. The application features a terminal-styled security portal for identity creation and authentication, specifically designed for a Security Operations Center (SOC) environment.

🔒 Security Architecture (Cloud Dweller Compliance)
The deployment is architected to ensure the backend core is never directly exposed to the public internet, satisfying the Cloud Dweller badge requirements:

Internal Binding: The Flask application is bound strictly to the loopback address 127.0.0.1:5000, ensuring it only accepts requests from the local VM.

Reverse Proxy Shield: Nginx serves as the primary entry point on Port 80, securely forwarding authorized traffic to the internal Flask service.

Firewall Hardening: The GCP Cloud Firewall is configured to permit only TCP Port 80 traffic (HTTP), while Port 5000 remains closed to all external networks.
