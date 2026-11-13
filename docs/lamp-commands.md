# **LAMP Command Reference**

A practical reference for Linux commands, Apache configuration, MySQL administration, PHP management, security and troubleshooting.

## 1. Connect to your VPS

```bash
ssh root@your_droplet_ip
```

## 2. Check the current nameservers for your domain

```bash
dig -t ns example.com
```

## 3. Check the current nameservers for your domain

```bash
dig -t ns example.com
```

## 4. Installing DNS Server (BIND9)

```bash
sudo apt update && apt install bind9 bind9utils bind9-doc
```

## 5. Check the status of BIND9

```bash
sudo systemctl status bind9
```

## 6. Enable and start BIND9

```bash
sudo systemctl enable bind9
```

```bash
sudo systemctl start bind9
```

## 7. Install terminal-based text editor - vim

```bash
sudo apt install vim
```

## 8.  Restart BIND9

```bash
sudo systemctl reload-or-restart bind9
```

## 9. Test whether your server is resolving DNS queries

```bash
sudo dig -t a @localhost google.com
```

## 10. Test your DNS from another machine

```bash
sudo dig -t ns example.com
```

## **Installing a Web Server (Apache2)**

### 1. Updated package lists and install the server

```bash
sudo apt update && apt install apache2
```

### 2. Apache 2 status

```bash
sudo systemctl status apache2
```

### 3. To ensure Apache starts automatically at boot time

```bash
sudo systemctl is-enable apache2
```
Or

Disable it from starting at boot time

```bash
sudo systemctl disable apache2
```

### 4. Status of uncomplicated firewall (UFW)

```bash
sudo ufw status
```

### 5. Enable both HTTP and HTTPS

```bash
sudo ufw allow 'Apache Full'
```

### 6. Get info about public IP address

```bash
ip addr
```

```bash
curl -4 ident.me
```