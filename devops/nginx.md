# nginx

cat /var/log/nginx/access.log \| awk '{print $1 " " $4 " " $5 " " $6 " " $7}' \| grep '92.184.99.62'\`

Search for ip in access log of nginx

