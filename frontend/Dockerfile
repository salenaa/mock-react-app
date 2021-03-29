#Build Phase
FROM node:alpine

RUN mkdir -p /usr/src/app/react/frontend

WORKDIR /usr/src/app/react/frontend

COPY package.json /usr/src/app/react/frontend

RUN npm install

COPY public /usr/src/app/react/frontend/public
COPY src /usr/src/app/react/frontend/src

RUN npm run build

#Run Phase
FROM nginx

COPY --from=0 /usr/src/app/react/frontend/build /usr/share/nginx/html