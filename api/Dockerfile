FROM ruby:2.3.1
RUN apt-get update -qq && apt-get -y install build-essential libpq-dev
RUN mkdir -p /dockerstack/api
WORKDIR /dockerstack/api
ADD Gemfile /dockerstack/api/Gemfile
ADD Gemfile.lock /dockerstack/api/Gemfile.lock
RUN bundle install
ADD . /dockerstack/api
