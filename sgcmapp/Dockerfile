FROM node:18-slim AS build
COPY . /home/app/
RUN npm install -g @angular/cli@15
WORKDIR /home/app/
RUN npm install && ng build

FROM nginx:stable-alpine-slim
COPY --from=build /home/app/dist/sgcmapp/* /usr/share/nginx/html
EXPOSE 80
