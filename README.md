# Going Merry Cybersecurity Homelab

A hands-on cybersecurity homelab built around a Linux server running on a ThinkPad. This project is focused on developing practical experience with Linux administration, system hardening, secure remote access, network security, security monitoring, and eventually attack-and-defense exercises in an isolated environment.

## 🎯 Project Goals

The goal of this project is to build a small enterprise-style cybersecurity environment where I can practice both defensive security and ethical hacking.

As the lab develops, I plan to implement:

- Linux server administration and hardening
- Secure remote access
- Firewall configuration
- Authentication security
- Security monitoring and logging
- SIEM
- Network intrusion detection
- Network segmentation
- Windows Active Directory
- Vulnerability testing
- Controlled penetration testing
- Incident detection and response

## 🖥️ Current Environment

### Going Merry Server

- Ubuntu Linux
- Headless ThinkPad server
- Remote administration through SSH
- Tailscale private networking
- UFW host firewall
- Fail2Ban intrusion prevention
- SSH public-key authentication

## 🔐 Security Implemented

### Secure Remote Access

Remote administration is performed through Tailscale and SSH rather than exposing SSH directly to the public internet.

### SSH Hardening

SSH has been configured to:

- Use public-key authentication
- Disable password authentication
- Disable direct root login
- Restrict remote SSH access using firewall rules

### Firewall

UFW is configured with a default-deny policy for incoming connections. SSH access is limited to trusted network paths, including the Tailscale interface.

### Fail2Ban

Fail2Ban monitors SSH authentication activity and temporarily blocks clients that repeatedly fail authentication.

## 🛣️ Project Roadmap

### Phase 1 — Secure Linux Server

- [x] Install Ubuntu Linux
- [x] Configure headless server
- [x] Configure SSH
- [x] Configure Tailscale
- [x] Configure UFW firewall
- [x] Install and configure Fail2Ban
- [x] Configure SSH public-key authentication
- [x] Disable SSH password authentication
- [x] Disable direct root SSH login

### Phase 2 — Security Monitoring

- [ ] Deploy Wazuh
- [ ] Configure centralized security logging
- [ ] Create security alerts and monitoring
- [ ] Analyze authentication and system events

### Phase 3 — Network Security

- [ ] Deploy Suricata IDS/IPS
- [ ] Capture and analyze network traffic
- [ ] Implement network segmentation
- [ ] Configure isolated lab networks

### Phase 4 — Active Directory Lab

- [ ] Deploy Windows Server
- [ ] Configure Active Directory Domain Services
- [ ] Create domain users and groups
- [ ] Deploy Windows client endpoints
- [ ] Configure Group Policy

### Phase 5 — Attack & Defense

- [ ] Deploy Kali Linux attack workstation
- [ ] Deploy intentionally vulnerable targets
- [ ] Perform controlled security assessments
- [ ] Generate and analyze attack telemetry
- [ ] Detect attacks using Wazuh and Suricata
- [ ] Document incidents and mitigations

## 🧠 Skills Being Developed

- Linux System Administration
- Linux Security Hardening
- SSH
- Public-Key Authentication
- Firewalls
- Network Security
- Identity and Access Management
- Security Monitoring
- SIEM
- Intrusion Detection
- Incident Response
- Active Directory
- Ethical Hacking
- Security Troubleshooting

## 📚 What I've Learned

One of the main goals of this project is understanding **why security controls work**, rather than simply installing security tools.

For example, while hardening SSH, I discovered that changing the main SSH configuration did not actually disable password authentication. By inspecting the effective SSH configuration, I identified a cloud-init configuration file that was overriding the main setting. After correcting the configuration, I validated the SSH configuration and verified that the server was using public-key authentication with password authentication disabled.

This project will continue to be updated as new security tools, systems, and attack-and-defense exercises are added.

## ⚠️ Disclaimer

All penetration testing and security testing documented in this repository is performed only against systems that I own or intentionally deploy for testing in an isolated lab environment.
