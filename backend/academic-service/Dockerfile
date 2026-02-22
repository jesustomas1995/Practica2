FROM node:20-alpine

ENV NODE_ENV=production
WORKDIR /app

RUN chown -R node:node /app
USER node

COPY --chown=node:node package*.json ./
RUN npm ci --omit=dev --no-audit --no-fund

COPY --chown=node:node . .

EXPOSE 3002
CMD ["node", "src/server.js"]
