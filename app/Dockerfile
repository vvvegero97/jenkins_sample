FROM node:12-alpine as build
WORKDIR /usr/src/app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm run build

FROM node:12-alpine
WORKDIR /usr/src/app
COPY --from=build /usr/src/app/build .
EXPOSE 3000
CMD [ "node", "server.js" ]