FROM node AS node-builder
WORKDIR /app
COPY . .
RUN npm ci
RUN npm run build

FROM nginx
COPY --from=node-builder /app/dist /usr/share/nginx/html