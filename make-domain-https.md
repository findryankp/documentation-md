# SET HTTPS with PROXY pass NGINX, Lets encrypt
**Development by:** 
- Findryankp

## Tutorial
```shell
sudo apt update && sudo apt upgrade -y
```
- install and get status **nginx**
```shell
sudo apt install nginx
sudo systemctl status nginx
```
- Install cerbot
```shell
sudo apt install certbot python3-certbot-nginx

certbot --version
```

- Set Up in nginx
```shell
sudo nano /etc/nginx/sites-available/your-domain.com
```

- example
```text
server {
  listen        80;
  server_name   your-domain.com www.your-domain.com;

  location / {
    proxy_pass  http://127.0.0.1:8080;
  }
}
```
- in command line copy this
```shell
sudo ln -s /etc/nginx/sites-available/your-domain.com /etc/nginx/sites-enabled/your-domain.com
```
- restart Nginx
```shell
sudo systemctl restart nginx
```
- Run Cerbot
```shell
sudo certbot --nginx
```

**Your Domain is https now**

