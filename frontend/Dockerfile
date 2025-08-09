FROM node:24-alpine AS build

WORKDIR /app

RUN corepack enable

COPY package*.json ./

RUN npm install

COPY . .

RUN npm run build

# EXPOSE 3000
# CMD ["npm", "run", "start"]

FROM node:22-alpine
WORKDIR /app

# Only `.output` folder is needed from the build stage
COPY --from=build /app/.output/ ./

# Change the port and host
ENV PORT=80
ENV HOST=0.0.0.0

EXPOSE 80

CMD ["node", "/app/server/index.mjs"]