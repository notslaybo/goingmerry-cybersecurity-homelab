# Phase 1: Linux Server Setup

## Overview

Going Merry is a cybersecurity homelab built around a ThinkPad running Ubuntu Linux. The ThinkPad is configured as a headless server, meaning it can operate without a dedicated monitor, keyboard, or mouse.

The server is designed to provide a platform for learning Linux administration, system hardening, secure remote access, security monitoring, networking, and eventually controlled attack-and-defense exercises.

## Why I Used a Dedicated Server

Instead of running the entire lab through virtual machines on my main computer, I wanted a dedicated system that could remain online and be accessed remotely.

This allows me to practice working with a system more like a real server rather than treating the environment as a temporary virtual machine.

## Current Architecture

My MacBook serves as my primary administration computer.

The basic environment currently looks like:

MacBook
   |
   | SSH
   |
Tailscale Private Network
   |
   |
Going Merry ThinkPad
   |
Ubuntu Linux Server

The ThinkPad remains at home while I can securely administer it remotely from my MacBook through Tailscale and SSH.

## Server Configuration

- Hostname: `goingmerry`
- Operating System: Ubuntu Linux
- Administration: SSH
- Remote Networking: Tailscale
- Host Firewall: UFW
- Brute-force Protection: Fail2Ban
- Authentication: SSH public-key authentication

## Security Approach

The server is being configured using a defense-in-depth approach.

Rather than relying on a single security control, multiple layers protect remote administration:

1. Tailscale controls private network connectivity.
2. UFW controls which network traffic can reach the server.
3. SSH controls remote administration.
4. Public-key authentication verifies authorized SSH clients.
5. Direct root SSH login is disabled.
6. Password-based SSH authentication is disabled.
7. Fail2Ban monitors repeated failed authentication attempts.

This creates multiple security controls that an unauthorized user would have to overcome rather than relying only on a username and password.

## Next Steps

The next phase of the project will focus on security monitoring and logging. Wazuh will be evaluated as the first major monitoring platform for the lab.
