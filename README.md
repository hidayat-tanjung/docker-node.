# docker-node.
![nodejs](https://user-images.githubusercontent.com/48172784/208683632-f3463c31-50f3-448a-bbfa-bbf4f5fe24ab.svg)
# Installation
```console
hidayat@code:~$ https://github.com/hidayat-tanjung/docker-node.
```
# Componen 
Installing Docker Container and Docker Compose in your device <a href="https://www.hidayatcode.xyz/search?q=docker" rel="nofollow">klik</a>

# Add File Docker
docker-compose.yml
```console
version: "3.3"

services:
  app:
    container_name: "app"
    build: .
    volumes:
      - .:/app
      - node_modules:/app/node_modules
    ports:
      - 7314:7314
    stdin_open: true
    environment:
      - PORT=7314
    command: npm start
volumes:
  node_modules:
```

Dockerfile
```console
FROM node:alpine

WORKDIR /app

COPY package*.json ./
RUN npm install --silent

COPY . ./

EXPOSE 7314
```

# Run your file
```console
hidayat@code:~$ sudo docker-compose -f docker-compose.yml up 
```
