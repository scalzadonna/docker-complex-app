FROM node:alpine as builder
WORKDIR '/app'
COPY ./package.json ./
RUN npm insall
COPY . .
RUN npm run build
#some minor comment
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/conf.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html