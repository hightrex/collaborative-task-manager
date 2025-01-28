# Development stage
FROM node:18-alpine AS development

WORKDIR /app

# Copy package files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy source code
COPY . .

# Set environment variables
ENV HOST=0.0.0.0
ENV PORT=3000

# Start development server with hot reload
CMD ["npm", "run", "dev"]

# Build stage
FROM node:18-alpine AS builder

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .
RUN npm run build

# Production stage
FROM node:18-alpine AS production

WORKDIR /app

COPY --from=builder /app/build ./build
COPY --from=builder /app/package.json .

RUN npm install --production

EXPOSE 3000

CMD ["node", "build"]