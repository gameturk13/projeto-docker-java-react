# Build da aplicação React
FROM node:20 AS build

WORKDIR /app

COPY app-react/package*.json ./
RUN npm install

COPY app-react/ .
RUN npm run build

# Servir com Nginx
FROM nginx:alpine

COPY --from=build /app/dist /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
