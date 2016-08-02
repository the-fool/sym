FROM node:6

RUN npm install -g typescript typings webpack-dev-server rimraf webpack
RUN npm install -g karma protractor

# Bundle app source
ADD *.js* /opt/app/
ADD package.json /tmp/package.json
RUN cd /tmp && npm install
RUN cp -a /tmp/node_modules /opt/app

ADD typings.json /tmp/typings.json
RUN cd /tmp && typings install
RUN cp -a /tmp/typings /opt/app

WORKDIR /opt/app

EXPOSE 3000
EXPOSE 3001
CMD [ "npm", "start" ]
