FROM node:6.4.0
RUN apt-get update -qq && apt-get -y install build-essential
RUN mkdir -p /dockerstack/web
WORKDIR /dockerstack/web
ADD package.json /dockerstack/web/package.json
RUN npm install
ADD . /dockerstack/web
