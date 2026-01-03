FROM node:18-alpine

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm ci --only=production

# Copy source code
COPY . .

# Create data directory for SQLite database
RUN mkdir -p /data

# Expose port
EXPOSE 5000

# Set environment variables
ENV NODE_ENV=production
ENV DATABASE_PATH=/data/forum.db

# Start the server
CMD ["node", "server.js"]
