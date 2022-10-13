FROM nginxinc/nginx-unprivileged:latest

WORKDIR /app

COPY . .

USER 1001

COPY default.conf /etc/nginx/conf.d/
