# build stage
FROM node:16.1.0-alpine
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

EXPOSE 8080
CMD ["npm", "run", "serve"]
