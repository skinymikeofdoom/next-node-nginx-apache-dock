FROM sinet/nginx-node:latest

RUN npm install -g create-react-app pm2

COPY default.conf /etc/nginx/conf.d/

WORKDIR /var/www

CMD ["nginx", "-g", "daemon off;"]
