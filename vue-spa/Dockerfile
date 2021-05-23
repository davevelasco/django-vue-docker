FROM node:16.2.0-alpine3.13
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .

ADD https://github.com/Yelp/dumb-init/releases/download/v1.2.5/dumb-init_1.2.5_x86_64 /usr/local/bin/dumb-init
RUN chmod +x /usr/local/bin/dumb-init

EXPOSE 8080
CMD ["dumb-init", "npm", "run", "serve"]