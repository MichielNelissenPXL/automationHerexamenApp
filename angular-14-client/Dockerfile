# Stage 1: Build the Angular application
FROM node:18 AS build

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build --prod

# Stage 2: Serve the Angular application with Nginx
FROM nginx:alpine

# Copy built Angular app to Nginx's default directory
COPY --from=build /app/dist/angular-14-crud-example /usr/share/nginx/html

EXPOSE 80

