FROM node:latest

# Set image metadata
LABEL version="1.0"
LABEL description="Tiny server demo"

# Create app directory
WORKDIR /usr/src/app

# install dependencies
COPY package*.json ./
RUN npm cache clean --force && npm install


# copy app source to image _after_ npm install so that
# application code changes don't bust the docker cache of npm install step
COPY dist/ .

# set application PORT and expose docker PORT, 80 is what Elastic Beanstalk expects
EXPOSE 3000 8080

CMD [ "npm", "start" ]
