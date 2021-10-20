FROM node:16.4.0-alpine as build-stage
WORKDIR /app
ENV PATH /app/node_modules/.bin:$PATH
COPY . /app
RUN yarn install
COPY ./ .
RUN yarn build

FROM nginx:latest
COPY --from=build-stage /app/build /usr/share/nginx/html