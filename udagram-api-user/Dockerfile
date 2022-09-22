FROM node:12

USER node

RUN mkdir /usr/src/app

# Create app directory
WORKDIR /usr/src/app
# Install app dependencies
# A wildcard is used to ensure both package.json AND package-lock.json are copied where available (npm@5+)
COPY --chown=node:node package*.json .
RUN npm ci 
# Bundle app source
COPY --chown=node:node . .
EXPOSE 8080
CMD [ "npm", "run", "prod" ]