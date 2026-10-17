# Create your Dockerfile here

#Use Node.js base image
FROM node:18-alpine

#set working directory inside container
WORKDIR /app

#copy package files first for better caching 
COPY package*.json ./

#install dependencies 
RUN npm install

#copy application code 
COPY . .

#create directory for data files
RUN mkdir -p /app/data

#expose the port the app runs on 
EXPOSE 5000

#start the application 
CMD [ "npm" , "start"]