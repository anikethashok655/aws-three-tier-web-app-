# Stage 1: Build the React app
FROM node:18 AS builder
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build
# Stage 2: Serve with NGINX
FROM nginx:stable-alpine
# Remove default config

# Copy custom nginx config to correct location

# Copy build output to NGINX web root
COPY --from=builder /app/build /usr/share/nginx/html
# Expose port
EXPOSE 80
# Start NGINX
CMD ["nginx", "-g", "daemon off;"]
