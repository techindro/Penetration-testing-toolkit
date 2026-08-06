# 🌐 Module 21: Nginx & Apache Web Server Shortcuts

Quick-reference commands and configuration snippets for managing Nginx and Apache web servers, testing syntax, reloading configurations, and configuring reverse proxies.

---

## 🟢 Level 1: Easy / Beginner Management Commands

```bash
# 1. Test Nginx configuration file syntax without restarting
sudo nginx -t

# 2. Reload Nginx configuration gracefully without dropping connections
sudo nginx -s reload

# 3. Check Apache web server configuration syntax
sudo apachectl configtest
```

---

## 🟡 Level 2: Medium / Intermediate Administration Commands

```bash
# 1. Restart Nginx service via systemd
sudo systemctl restart nginx

# 2. View real-time Nginx access and error logs
sudo tail -f /var/log/nginx/access.log /var/log/nginx/error.log

# 3. Obtain and install free SSL certificate via Let's Encrypt Certbot for Nginx
sudo certbot --nginx -d example.com -d www.example.com
```

---

## 🔴 Level 3: Hard / Advanced Reverse Proxy Configuration Example

Add reverse proxy configuration inside `/etc/nginx/sites-available/default`:

```nginx
server {
    listen 80;
    server_name api.example.com;

    location / {
        proxy_pass http://127.0.0.1:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        proxy_cache_bypass $http_upgrade;
    }
}
```
