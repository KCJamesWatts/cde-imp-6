# Build stage
FROM node:22.21.0-alpine AS build
WORKDIR /app
COPY frontend/package*.json ./
RUN npm update -g npm && npm ci
COPY frontend/ .
# If you use Vite, this creates /app/dist
RUN npm run build

# Runtime stage
FROM nginx:1.29.2-alpine
# Copy build output into Nginx
COPY --from=build /app/dist /usr/share/nginx/html

# Optional: SPA fallback + caching (see conf below)
COPY frontend/.docker/default.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
HEALTHCHECK CMD wget -qO- http://localhost/ || exit 1
