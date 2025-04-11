# How To Install XRDP on Linux VM

## Installation Steps

1. Update package lists:
```bash
sudo apt-get update
```

2. Install XRDP server:
```bash
sudo apt-get -y install xrdp
```

3. Install XFCE desktop environment:
```bash
sudo apt-get -y install xfce4
```

4. Enable XRDP service to start on boot:
```bash
sudo systemctl enable xrdp
```

5. Configure XRDP to use XFCE:
```bash
echo xfce4-session > ~/.xsession
```

6. Restart XRDP service to apply changes:
```bash
sudo service xrdp restart
```

## Firewall Configuration

Ensure that port 3389 is open in your firewall:
```bash
sudo ufw allow 3389/tcp
```

## Connecting to XRDP

1. Use a Remote Desktop client (like Microsoft Remote Desktop)
2. Connect to your server's IP address
3. Default port: 3389
4. Login with your username and password

## Troubleshooting

If you encounter connection issues:
- Check that XRDP service is running: `sudo systemctl status xrdp`
- Verify firewall settings allow port 3389
- Ensure your VM provider allows RDP connections 
