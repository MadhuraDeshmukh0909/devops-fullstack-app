# Use an official Node.js runtime as the base image
FROM node:alpine as build

# Set the working directory in the container
WORKDIR /app

# Copy the package.json and package-lock.json files to the container
COPY frontend/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code to the container
COPY frontend/ ./

# Build the application
RUN npm run build

# Use nginx as the base image for serving the application
FROM nginx:alpine

# Copy the built React app from the previous stage to the nginx web server directory
COPY --from=build /app/build /usr/share/nginx/html

# Expose port 80 to the outside world
EXPOSE 80

# Command to start the nginx server
CMD ["nginx", "-g", "daemon off;"]
