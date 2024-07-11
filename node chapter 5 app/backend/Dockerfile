FROM node

WORKDIR /app

COPY package.json .

RUN npm install

COPY . .

EXPOSE 80

ENV MONGODB_CONTAINER=mongodb_chap_5

CMD ["npm", "start"]