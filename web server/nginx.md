# Nginx 安裝
作業系統版本: ubuntu 20.04
```
sudp apt update
sudo apt install nginx
# 啟動nginx
sudo systemctl start nginx
sudo systemctl status nginx
```
# 開啟ufw防火牆並設定

```
sudo ufw allow OpenSSH
sudo ufw allow 'Nginx HTTP'
sudo ufw allow 'Nginx HTTPS'
sudo ufw enable
sudo ufw status
```

# 測試
http://your_server_ip


# 設定nginx 網站區塊

```
sudo mkdir -p /var/www/your_domain/html
sudo chown -R $USER:$USER /var/www/your_domain/html #系統會自動帶入$USER參數
sudo chmod -R 755 /var/www/your_domain

# 產生範例網頁
nano /var/www/your_domain/html/index.html

<html>
    <head>
        <title>Welcome to your_domain!</title>
    </head>
    <body>
        <h1>Success!  The your_domain server block is working!</h1>
    </body>
</html>

# 設定conf
sudo nano /etc/nginx/sites-available/your_domain

server {
        listen 80;
        listen [::]:80;

        root /var/www/your_domain/html;
        index index.html index.htm index.nginx-debian.html;

        server_name your_domain www.your_domain;

        location / {
                try_files $uri $uri/ =404;
        }
}

# 利用ln設定路徑映射
sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/
sudo systemctl restart nginx
# 測試
sudo nginx -t
```
