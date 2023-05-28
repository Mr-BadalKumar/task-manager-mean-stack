# Use an official Node runtime as a parent image
FROM node:10.15-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY frontend/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory
COPY frontend .

# Build the application
RUN npm run build --prod

# Expose port 80 for the Angular application
# EXPOSE 4200
#ng serve --host 0.0.0.0

# # Start the Angular development server
# CMD npm run start
# Stage 1: Build the Angular application

# Stage 2: Serve the Angular application using Nginx

FROM nginx:1.21.0-alpine
COPY  /app/dist /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
