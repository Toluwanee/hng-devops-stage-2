# Use an official Node.js runtime as a parent image
FROM node:20 AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the entire project to the working directory
COPY . .


# Expose the port the app runs on
EXPOSE 5173

# Command to run the app
CMD ["npm", "run", "dev"]


