FROM node:22-alpine AS builder

WORKDIR /app

COPY . .

RUN npm install

RUN npm run build

#--nginx web serverr to serve--

FROM nginx:alpine

COPY --from=builder /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

