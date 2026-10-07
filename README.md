# AWS Lightsail 

## Points to Remember

| Point | Details |
|---|---|
| Lightsail | Simplified AWS VPS/cloud hosting service |
| Best for | Websites, WordPress, small apps, dev/test |
| Instance | VM with bundled CPU, RAM, SSD and transfer |
| Blueprint | OS or preconfigured application |
| Static IP | Fixed public IP; attach it to the instance |
| Firewall | Controls allowed inbound ports |
| Snapshot | Backup of instance/disk |
| DNS Zone | Manage domain DNS records |
| Load Balancer | Distributes traffic across instances |
| Database | Managed database option available |
| Containers | Lightsail Container Service available |
| Pricing | Predictable monthly bundles |

### Basic Flow

```text
User
  ↓
Domain / DNS
  ↓
Static IP / Load Balancer
  ↓
Lightsail Firewall
  ↓
Lightsail Instance
  ↓
Website / Application
```

## Basic Steps

1. AWS Console → **Lightsail**
2. **Create instance**
3. Select region and Availability Zone
4. Select platform: **Linux/Unix** or Windows
5. Select blueprint:
   - OS Only → Ubuntu / Amazon Linux
   - App → WordPress / LAMP / Node.js etc.
6. Select instance plan
7. Enter instance name
8. **Create instance**
9. Create and attach **Static IP**
10. Configure firewall: `22`, `80`, `443`
11. Connect using browser SSH or terminal
12. Install/deploy application
13. Point domain DNS to the Static IP

## Useful Commands

Connect:

```bash
ssh -i key.pem ubuntu@STATIC_IP
```

Ubuntu web server:

```bash
sudo apt update
sudo apt install apache2 -y
sudo systemctl enable --now apache2
```

Amazon Linux:

```bash
sudo dnf install httpd -y
sudo systemctl enable --now httpd
```

Create test page:

```bash
echo "<h1>AWS Lightsail Working</h1>" | sudo tee /var/www/html/index.html
```

Check:

```bash
curl http://localhost
curl http://STATIC_IP
```

AWS CLI Lightsail commands:

```bash
aws lightsail get-instances

aws lightsail get-instance \
  --instance-name myserver

aws lightsail get-static-ips

aws lightsail get-instance-port-states \
  --instance-name myserver

aws lightsail get-instance-snapshots
```

### Most Important

**Instance → Static IP → Firewall → Web Server → DNS → Domain**

For a web server, remember:

```text
22   SSH
80   HTTP
443  HTTPS
```
