# Nginx 安裝

```
sudo apt install nginx
# 啟動nginx
sudo systemctl start nginx
sudo systemctl status nginx
```
# 開啟ufw防火牆並設定

```
sudo ufw enable

# Available applications:
#  Nginx Full
#  Nginx HTTP
#  Nginx HTTPS
sudo ufw allow 'Nginx FULL'

sudo ufw status
```

# 測試
http://your_server_ip



