FROM node:21 AS frontend-builder
WORKDIR /app
COPY package.json ./
RUN npm install
RUN npm run test
COPY ..
FROM node:21-slim
WORKDIR /app
COPY --from=frontend-builder /app .
COPY .env.docker .env.local
EXPOSE 3000
CMD ["npm","run","dev", "--","--host"]
