# Use Node.js 18
FROM node:18

WORKDIR /app

COPY package.json package-lock.json ./

RUN npm install --legacy-peer-deps

# Copy project files
COPY . .

# Build React app
RUN npm run build

# Install a simple static server to serve the build folder
RUN npm install -g serve

# Expose port 3000
EXPOSE 3000

# Start the app in production mode
CMD ["serve", "-s", "build", "-l", "3000"]
