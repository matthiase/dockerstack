FROM node:6.4.0
RUN apt-get update -qq && apt-get -y install build-essential
RUN mkdir -p /dockerstack/web
WORKDIR /dockerstack/web
COPY package.json /dockerstack/web
RUN npm install
COPY . /dockerstack/web
#EXPOSE 8080
#CMD [ "npm", "start" ]
