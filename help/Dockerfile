FROM ubuntu:latest

RUN apt-get update
RUN apt-get install -yq curl git nano
RUN apt-get install -y npm
RUN npm install -g npm
RUN curl -sL https://deb.nodesource.com/setup_9.x | bash -
RUN apt-get install -y nodejs
RUN npm install -g http-server

RUN mkdir -p /usr/src/apps
RUN mkdir -p /usr/app/www

WORKDIR /usr/src/apps
RUN git clone https://github.com/TheCodingLand/tutorial-engine.git
WORKDIR /usr/src/apps/tutorial-engine
RUN npm install
RUN npm run build
RUN mkdir -p /usr/app/www/
RUN yes | cp -rf /usr/src/apps/tutorial-engine/build/* /usr/app/www/





WORKDIR /usr/app/www/
#CMD ["npm", "start"]

CMD ["http-server"]
