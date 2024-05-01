**README.md**

---

# Remote Ubuntu with Microsoft Remote Desktop

This guide outlines the steps to remotely access an Ubuntu desktop using Microsoft Remote Desktop. 

## Prerequisites

- A machine running Ubuntu
- Administrative privileges on the Ubuntu machine
- Access to the internet

## Step 1: Create a New User

```bash
sudo adduser xrdpuser
```
Set the password for the new user (e.g., `12345678`).

## Step 2: Grant Sudo Privileges to the User

```bash
sudo usermod -aG sudo,adm xrdpuser && su xrdpuser
```

## Step 3: Update and Upgrade Ubuntu

```bash
sudo apt-get update && sudo apt-get upgrade -y
```
Enter the password for `xrdpuser` when prompted.

## Step 4: Install Ubuntu Desktop Environment

```bash
sudo apt install ubuntu-desktop
```

## Step 5: Install Google Chrome

```bash
curl -O https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb
sudo dpkg -i google-chrome-stable_current_amd64.deb
sudo apt-get install -f
```

## Step 6: Reboot the System

```bash
sudo reboot
```

## Step 7: Install and Enable XRDP

```bash
sudo apt install xrdp
sudo systemctl enable xrdp
```

## Step 8: Configure Firewall

```bash
sudo apt install ufw
sudo ufw allow from any to any port 3389 proto tcp
```

## Step 9: Find the IP Address

```bash
ip address
```

## Step 10: Connect Using Microsoft Remote Desktop

- Open Microsoft Remote Desktop application.
- Enter the IP address of the Ubuntu machine.
- Use the following credentials:
  - **Username:** xrdpuser
  - **Password:** 12345678

---

## Authors

- [Koding88](https://github.com/koding88)