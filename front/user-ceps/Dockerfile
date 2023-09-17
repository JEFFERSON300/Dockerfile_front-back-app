FROM node:18 as constructor

WORKDIR /application/
COPY . .
RUN npm i
RUN npm run build

FROM nginx:alpine as server

COPY --from=constructor /application/dist /usr/share/nginx/html
EXPOSE 80



