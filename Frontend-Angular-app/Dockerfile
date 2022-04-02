##FROM node:7.7-alpine
FROM node:latest as builder

# create working direcotry
RUN mkdir -p /opt/to-do-app

WORKDIR /opt/to-do-app

#copy project files
COPY . .

#Install dependencies 
RUN npm install

#Build Project

RUN npm run build --prod

# run
EXPOSE 8080
CMD ["sh", "-c", "node initialize && node server"]
