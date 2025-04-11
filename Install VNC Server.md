# How To Install VNC Server on Linux VM

## Installation Steps

1. Update package lists:
```bash
sudo apt-get update
```

2. Install TightVNC Server:
```bash
sudo apt-get install tightvncserver
```

3. Install XFCE Desktop Environment:
```bash
sudo apt-get -y install xfce4
```

## Configuration

1. Set up VNC password (required first time):
```bash
vncserver
```

2. Verify VNC server is running on the correct port:
```bash
nc localhost 5901
```

## Firewall Configuration

Ensure port 5901 is open in your firewall/security group:
```bash
sudo ufw allow 5901/tcp
```

## Additional Software

Install Firefox Browser:
```bash
sudo apt-get install firefox
```

## Connecting to VNC Server

1. Use a VNC client on your local machine
2. Connect to: `your_server_ip:5901`
3. Enter the password you created earlier

## Stopping VNC Server

To stop the VNC server:
```bash
vncserver -kill :1
```

## Automatic Startup (Optional)

To configure VNC server to start automatically on boot:
1. Create a systemd service file
2. Enable the service with `systemctl enable`

## Troubleshooting

If you encounter connection issues:
- Check that VNC server is running: `ps aux | grep vnc`
- Verify ports are open: `sudo netstat -tulpn | grep 5901`
- Check firewall settings: `sudo ufw status` 