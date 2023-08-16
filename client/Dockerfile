FROM node:16-alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm install
RUN mkdir -p /app/node_modules/.cache
RUN chmod -R 777 /app/node_modules/.cache
COPY . .
RUN npm run build

FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default
COPY --from=builder /app/build /usr/share/nginx/html

