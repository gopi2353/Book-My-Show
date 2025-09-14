# Start from official Node.js LTS version
FROM node:18-alpine

# Set working directory
WORKDIR /usr/src/app

# Copy only package files first for faster caching
COPY package*.json ./

# Install dependencies (with PostCSS fix)
RUN npm install --legacy-peer-deps
RUN npm install postcss@8.4.21 postcss-safe-parser@6.0.0 --save-dev

# Copy the rest of the source code
COPY . .

# Expose the app port
EXPOSE 3000

# Environment variables
ENV NODE_OPTIONS=--openssl-legacy-provider
ENV PORT=3000

# Start the app
CMD ["npm", "start"]
