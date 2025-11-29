# Hetzner Set Up and Management

Cloud work for solveit course.
Note: **liquidweb** is another option for a cloud server.

## Hetzner Server Setup Recipe

### Prerequisites
1. Generate SSH key pair (if you don't have one):
```
ssh-keygen -t ed25519 -C "your_email@example.com"
```
This creates `~/.ssh/id_ed25519` (private) and `~/.ssh/id_ed25519.pub` (public)

### Steps to Create Server
1. Sign up at https://www.hetzner.com/
2. Enable 2FA for account security
3. Create new Cloud project
4. Add server with these settings:
- Type: x86 (not Arm64)
- Location: Helsinki (cost-optimized) or choose based on your location
- Image: Ubuntu 24.04 LTS
- Type: CPX11 (2 vCPU, 4GB RAM, 40GB NVMe) - ~$4/month
- SSH Key: Paste contents of `~/.ssh/id_ed25519.pub` (Give it a name corresponding to your local machine)
- Skip: Volumes, Firewalls, Backups, Cloud config
5. Click "Create & Buy"

### Connect to Server
```
ssh root@YOUR_SERVER_IP
```

Accept the host fingerprint when prompted. (Enter 'yes')

### Initial Setup
```
sudo apt update 
sudo apt install tree
``` 
or other tools you need