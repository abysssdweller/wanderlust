# Base image for backend
FROM node:21 
RUN groupadd -r appgroup && useradd -r -g appgroup appuser

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install required dependencies
RUN npm install &&\
    chown -R appuser:appgroup /app
USER appuser

# Copy the rest of the application code to the working directory
COPY . .
COPY .env.sample .env
# Expose the port the app runs on
EXPOSE 5000
CMD ["npm", "start"]
