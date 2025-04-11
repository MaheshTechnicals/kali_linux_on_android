# Logging into Ubuntu without SSH Key Authentication

## Overview
This guide explains how to configure an Ubuntu server to accept password authentication instead of requiring SSH key pairs.

## Steps

1. First, log in to your Ubuntu server using your existing SSH key:
```bash
ssh -i your_key.pem username@server_ip
```

2. Switch to root user:
```bash
sudo su
```

3. Edit the SSH configuration file:
```bash
nano /etc/ssh/sshd_config
```

4. Find and modify the following lines:
```
# Change these settings
PasswordAuthentication yes
PermitRootLogin yes
```

5. Save the file (Ctrl+O, then Enter, then Ctrl+X to exit)

6. Restart the SSH service to apply changes:
```bash
sudo service ssh restart
```

7. Reboot the server (optional but recommended):
```bash
sudo reboot
```

## After Configuration
Now you can log in to your Ubuntu server using a password instead of an SSH key:
```bash
ssh username@server_ip
```

## Security Note
Enabling password authentication may reduce security compared to SSH key authentication. Consider:
- Using strong, unique passwords
- Implementing fail2ban to prevent brute force attacks
- Limiting access to specific IP addresses if possible


