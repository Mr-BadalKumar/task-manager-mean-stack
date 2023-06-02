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
RUN npm run build


EXPOSE 4200

# Start the Angular application
CMD npm start
