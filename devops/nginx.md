# nginx

### Search an ip in the nginx access log

cat /var/log/nginx/access.log \| awk '{print $1 " " $4 " " $5 " " $6 " " $7}' \| grep '92.184.99.62'\`

Search for ip in access log of nginx

### Reverse proxy

* [https://www.hostinger.com/tutorials/how-to-set-up-nginx-reverse-proxy/](https://www.hostinger.com/tutorials/how-to-set-up-nginx-reverse-proxy/)

