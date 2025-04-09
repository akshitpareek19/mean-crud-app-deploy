# Stage 1: Build Angular app
FROM node:18 AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build --prod

# Stage 2: Serve with Nginx
FROM nginx:alpine

# Replace 'frontend' if your Angular output folder has a different name
COPY --from=build /app/dist/angular-15-crud /usr/share/nginx/html

EXPOSE 80
