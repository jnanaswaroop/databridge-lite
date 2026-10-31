FROM node:18-slim

# Create app directory
WORKDIR /app

# Install OS-level build tools required for native npm modules
RUN apt-get update && apt-get install -y \
    python3 \
    make \
    g++ \
    && rm -rf /var/lib/apt/lists/*

# Install app dependencies
COPY package*.json ./
RUN npm install

# Bundle app source
COPY . .

# Expose port 3000
EXPOSE 3000

# Start command
CMD [ "npm", "start" ]