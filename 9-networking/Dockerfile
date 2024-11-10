FROM node
USER node
RUN mkdir -p /home/node/code
WORKDIR /home/node/code
COPY package*.json ./
RUN npm ci
COPY --chown=node:node . .
CMD ["node", "index.js"]
