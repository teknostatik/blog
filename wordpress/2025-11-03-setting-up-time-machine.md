----
title: "Backing up part 2 : Using Linux as a Time Machine backup destination"
date: "2025-11-03"
----

## On Linux

### 1. Install Samba on the Linux Server

```bash
# Ubuntu/Debian
sudo apt update
sudo apt install samba avahi-daemon

# RHEL/CentOS/Fedora
sudo dnf install samba avahi
```

### 2. Create a Directory for Time Machine Backups

```bash
sudo mkdir -p /mnt/timemachine
sudo chown your_username:your_username /mnt/timemachine
sudo chmod 755 /mnt/timemachine
```

### 3. Configure Samba

Edit the Samba configuration file:

```bash
sudo nano /etc/samba/smb.conf
```

Add this configuration at the end:

```ini
[TimeMachine]
   comment = Time Machine Backup
   path = /mnt/timemachine
   browseable = yes
   writable = yes
   valid users = your_username
   create mask = 0600
   directory mask = 0700
   spotlight = yes
   vfs objects = catia fruit streams_xattr
   fruit:aapl = yes
   fruit:time machine = yes
```

### 4. Set Up Samba User Password

```bash
sudo smbpasswd -a your_username
```

### 5. Restart Samba and Avahi

```bash
# Ubuntu/Debian
sudo systemctl restart smbd nmbd avahi-daemon
sudo systemctl enable smbd nmbd avahi-daemon

# RHEL/CentOS/Fedora
sudo systemctl restart smb nmb avahi-daemon
sudo systemctl enable smb nmb avahi-daemon
```

### 6. Configure Firewall (if needed)

```bash
# Ubuntu/Debian with ufw
sudo ufw allow samba

# RHEL/CentOS/Fedora with firewalld
sudo firewall-cmd --permanent --add-service=samba
sudo firewall-cmd --reload
```

## On the Mac

### 1. Connect to the Share

Open **Finder** and press `Cmd + K`, then enter:

```
smb://server_ip_or_hostname/TimeMachine
```

Enter your username and password when prompted.

### 2. Enable Time Machine to Use Network Drives

If the share doesn't appear in Time Machine preferences, you may need to enable unsupported volumes:

```bash
sudo tmutil setdestination /Volumes/TimeMachine
```

Or directly set it:

```bash
sudo tmutil setdestination smb://username@server_ip/TimeMachine
```

### 3. Configure Time Machine

1. Open **System Settings** → **General** → **Time Machine**
2. Click the **+** button to add a backup disk
3. Select your network share
4. Start the backup

## Tips and Considerations

- **Space Requirements**: Ensure you have enough space on the Linux server (Time Machine typically uses 1-2x your Mac's storage)
- **Performance**: Network backups are slower than local ones, especially for the initial backup
- **Reliability**: Use a wired connection for the first backup if possible
- **Size Limits**: You can set a quota using Samba or filesystem quotas to prevent Time Machine from using all available space

## Optional: Set a Size Limit for Time Machine

On your Mac, create a sparse bundle with a maximum size:

```bash
sudo tmutil setdestination /Volumes/TimeMachine
hdiutil create -size 500g -type SPARSEBUNDLE -fs "HFS+J" \
  -volname "Time Machine Backups" \
  ~/Desktop/TimeMachine.sparsebundle
```

Then move this to your network share and use it as the backup destination.
