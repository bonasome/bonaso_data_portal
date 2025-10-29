## Checklist For Resetting Domain

#### Edit nginx.conf
    - Edit server_name (both port 80: HTTP & port 443: HTTPS)
    - Edit sslcertificate/key
#### Get new Certbot cert:
```bash
sudo certbot certonly --webroot -w /home/bonasoadmin/bonaso_data_portal/certbot/www -d domain.co.bw -d www.domain.co.bw
```

#### Restart Nginx Container
```bash
sudo docker compose restart nginx
```