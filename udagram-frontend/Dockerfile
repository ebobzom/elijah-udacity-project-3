## Build
FROM node:14.15.5-alpine3.13 AS ionic

USER node

RUN mkdir /usr/src/app

# Create app directory
WORKDIR /usr/src/app
# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied
COPY --chown=node:node package*.json ./usr/src/app
RUN npm ci
RUN npm i -g @ionic/cli
# Bundle app source
COPY --chown=node:node . .
RUN ionic build
## Run 
FROM nginx:alpine
#COPY www /usr/share/nginx/html
COPY --from=ionic  /usr/src/app/www /usr/share/nginx/html