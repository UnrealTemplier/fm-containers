# build stage
FROM node AS node-builder
USER node
RUN mkdir -p /home/node/app
WORKDIR /home/node/app
COPY --chown=node:node ./astro-app/package*.json ./
RUN npm ci
COPY --chown=node:node ./astro-app .
RUN npm run build

# prod stage
FROM nginx
COPY --from=node-builder /home/node/app/dist /usr/share/nginx/html
