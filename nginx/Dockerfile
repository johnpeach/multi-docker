FROM nginx
COPY ./default.conf /etc/nginx/conf.d/default.conf
RUN mkdir -p /app/node_modules/.cache
RUN chmod -R 777 /app/node_modules/.cache
