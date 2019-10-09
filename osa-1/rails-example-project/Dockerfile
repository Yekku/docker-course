FROM ruby:2.6.0

WORKDIR /app
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
COPY package.json /app
RUN npm install
COPY . /app
COPY Gemfile Gemfile.lock /app/
RUN gem install bundler
RUN bundle install

RUN rails db:migrate

EXPOSE 3000

CMD rails s