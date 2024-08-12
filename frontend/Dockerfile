# Use the official Node.js image
FROM node:18

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json first
COPY vue_project/package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the Vue.js application code into the container
COPY vue_project/ ./

# Build the Vue.js application
RUN npm run build

# Install a simple web server to serve the static files
RUN npm install -g serve

# Expose port 5000
EXPOSE 5000

# Command to run the static file server
CMD ["serve", "-s", "dist", "-l", "5000"]
