FROM       node:latest
MAINTAINER Mohd Faiz Hasim

ENV APP_PATH /user/src/myapp

EXPOSE 3000

ADD index.js $APP_PATH/index.js
RUN npm install --save express

WORKDIR $APP_PATH

CMD node index.js