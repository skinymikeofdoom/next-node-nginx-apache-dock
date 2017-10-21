FROM sinet/nginx-node:latest

RUN npm install -g react react-dom create-react-app pm2 next

COPY default.conf /etc/nginx/conf.d/

WORKDIR /var/www

CMD ["nginx", "-g", "daemon off;"]
