# Use the official Node image as the base image
FROM node:14

# Set the working directory
WORKDIR /app

# Install the Angular CLI globally
RUN npm install -g @angular/cli

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install project dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose port 8081 (used by ng serve)
EXPOSE 8081

# Command to run the Angular development server
CMD ["ng", "serve", "--host", "0.0.0.0", "--port", "8081"]
