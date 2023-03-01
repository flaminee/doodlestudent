FROM node:16 as build

RUN apt-get -y update
RUN apt-get install -y git
RUN apt-get install -y curl

RUN git clone https://github.com/barais/doodlestudent.git

WORKDIR doodlestudent/front

RUN npm install
RUN npm install -g @angular/cli@latest
RUN ng build

FROM nginx:latest

COPY --from=build doodlestudent/front/dist/tlcfront /usr/share/nginx/html
COPY nginx.conf /etc/nginx/nginx.conf

EXPOSE 81

