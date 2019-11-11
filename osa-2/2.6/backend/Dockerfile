FROM ubuntu:16.04

WORKDIR /app 
RUN apt-get update && apt-get install -y curl
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
COPY package.json /app
RUN npm install
COPY . /app
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD npm start