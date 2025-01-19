FROM node:21 AS backend-builder
WORKDIR /app
COPY ..
RUN npm i
RUN npm run test
