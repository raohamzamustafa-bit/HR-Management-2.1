FROM node:20-alpine AS base
WORKDIR /app

# Copy root and server package files for workspaces
COPY package*.json ./
COPY server/package.json ./server/

# Install all dependencies (including dev for tsx)
RUN npm ci

# Copy source code
COPY . .

EXPOSE 4000

# For development with hot reload via volume mount
CMD ["npm", "run", "dev", "--workspace=server"]