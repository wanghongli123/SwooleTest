FROM nginx:1.12-alpine

ARG INI_FILE
COPY ${INI_FILE} /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types
