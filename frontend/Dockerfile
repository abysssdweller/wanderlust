FROM node:21
RUN groupadd -r frontendgroup && useradd -r -g frontendgroup frontenduser

WORKDIR /frontend
COPY package*.json ./
RUN npm i &&\
    chown -R frontenduser:frontendgroup /frontend
USER frontenduser

COPY . .
COPY .env.sample .env.local

EXPOSE 3000

CMD ["npm","run","dev","--host"]
