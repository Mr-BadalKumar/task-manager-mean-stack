# Use an official Node runtime as a parent image
FROM node:10.15-alpine

# Set the working directory to /app
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY frontend /usr/local/app/

# Install dependencies
RUN npm install

# Copy the rest of the application code to the working directory

# Build the application
RUN npm run build --prod

# Expose port 80 for the Angular application
EXPOSE 80

# Start the Angular application
CMD ["npm", "run", "start"]
