# Use the official Node.js image as the base image
FROM node:lts-alpine

# Create and set the working directory
WORKDIR /MediaFusion

ENV PATH /MediaFusion/node_modules/.bin:$PATH

# Copy package.json and package-lock.json (or yarn.lock) to the working directory
COPY package.json package-lock.json ./

# Install application dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the Nx application (adjust <app-name> to your actual app name)
RUN npm run build:mediafusion

# Expose the port the application will run on
EXPOSE 3000

# Run the application (adjust <app-name> to your actual app name)
CMD ["npm", "run", "start:mediafusion"]