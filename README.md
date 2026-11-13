# Rocky Linux System Administration Lab

## Overview

A hands-on Linux system administration project focused on deploying, configuring, and securing a Rocky Linux server in a virtualized environment.

The project demonstrates practical skills relevant to Linux system administration, IT infrastructure, and data center operations. Each implementation is tested and documented to demonstrate its functionality and the technical decisions behind it.

## Lab Environment

| Component | Technology / Configuration |
|---|---|
| Host Machine | Apple Silicon Mac (M1) |
| Virtualization | Oracle VirtualBox |
| Operating System | Rocky Linux 9 |
| Server Hostname | `dc-web01` |
| Network Configuration | NAT + Host-Only |
| Remote Administration | OpenSSH |
| Server Management | Linux CLI |

## Network Architecture

The virtual server uses two network interfaces to separate external network connectivity from host-to-server administration.

| Interface | Network | Purpose |
|---|---|---|
| `enp0s8` | NAT (DHCP) | Outbound network and internet connectivity |
| `enp0s9` | Host-Only (`192.168.56.2/24`) | Direct communication between the Mac host and Rocky Linux VM |

This configuration allows the server to access external resources while providing a dedicated network for remote administration from the host machine.

## Completed Implementations

### 1. Network and Hostname Configuration

- Configured NAT and Host-Only network interfaces.
- Assigned a static IPv4 address to the Host-Only interface.
- Configured the server hostname as `dc-web01`.
- Established network connectivity between the host machine and Rocky Linux server.
- Configured hostname-based SSH access from the host machine.
- Verified interface addressing, routing, and network connectivity.

### 2. SSH Authentication and Security Hardening

- Configured OpenSSH for remote server administration.
- Generated an RSA SSH key pair on the host machine and configured public-key authentication.
- Disabled password-based SSH authentication.
- Disabled direct root SSH login.
- Managed SSH security settings using a dedicated configuration file under `/etc/ssh/sshd_config.d/`.
- Verified successful key-based authentication and rejection of unauthorized authentication attempts.

[View SSH Security Documentation](Security/SSH/README.md)

## Verification

The implemented configurations were validated through practical testing, including:

- Network connectivity and routing checks.
- Successful SSH connections using the server hostname.
- Successful public-key authentication without a password.
- Rejected password-based SSH login attempts.
- Rejected direct root SSH login attempts.

## Technical Skills Demonstrated

Linux System Administration · Rocky Linux · Virtualization · TCP/IP Networking · Network Configuration · OpenSSH · Public-Key Authentication · SSH Hardening · Linux CLI · Troubleshooting
