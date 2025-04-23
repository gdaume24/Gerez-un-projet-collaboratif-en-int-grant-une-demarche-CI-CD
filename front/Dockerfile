# Étape de build
FROM node:18.18.0 AS build  # Node LTS compatible avec Angular 15/16

WORKDIR /usr/local/app
COPY ./ /usr/local/app/

# Forcer une version compatible de TypeScript
RUN yarn install
RUN yarn add typescript@4.8.4 -D  # Compatible avec Angular CLI
RUN npm run build

# Étape de prod
FROM nginx:latest as production
COPY nginx.conf /etc/nginx/conf.d/default.conf
COPY --from=build /usr/local/app/dist/bobapp /usr/share/nginx/html
EXPOSE 80
