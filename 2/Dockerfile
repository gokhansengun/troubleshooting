FROM node:8.9.1 AS build-env

COPY ./ /usr/src/react-app/

WORKDIR /usr/src/react-app/

RUN npm install

RUN npm run build

FROM nginx:1.10 AS runtime-env

COPY nginx.conf /etc/nginx/conf.d/default.conf

COPY --from=build-env /usr/src/react-app/dist /usr/share/nginx/html/

