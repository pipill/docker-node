FROM pipill/armhf-node:4.8.3

RUN [ "cross-build-start" ]

RUN mkdir -p /usr/src/app

RUN [ "cross-build-end" ]

WORKDIR /usr/src/app

ONBUILD ARG NODE_ENV
ONBUILD ENV NODE_ENV $NODE_ENV
ONBUILD COPY package.json /usr/src/app/
ONBUILD RUN npm install && npm cache clean
ONBUILD COPY . /usr/src/app

CMD [ "npm", "start" ]
