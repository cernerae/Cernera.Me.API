FROM node:14.2-alpine

ARG auto_email
ARG auto_email_password

ENV EMAIL $auto_email
ENV PASSWORD $auto_email_password

RUN echo "EMAIL: $EMAIL"
RUN echo "PASSWORD: $PASSWORD"

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY package*.json ./

USER node

RUN npm install

COPY --chown=node:node . .

EXPOSE 3001

CMD [ "npm", "run", "start" ]
