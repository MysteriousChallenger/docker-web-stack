FROM nginx
WORKDIR /
COPY ./bin /usr/local/bin
COPY ./templates /etc/nginx/templates
ENTRYPOINT ["/docker-entrypoint.sh"]
CMD ["nginx", "-g", "daemon off;"]