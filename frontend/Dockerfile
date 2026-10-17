# Create your Dockerfile here

#Stage 1: build the React application 
FROM node:18-alpine as builder

#set working directory 
WORKDIR /app

#copy package files
COPY package*.json ./

#install dependencies 
RUN npm install

#copy source code 
COPY . .

#build the production application 
RUN npm run build 

#Stage 2: serve with nginx
FROM nginx:alpine

#copy built files from previous stage
COPY --from=builder /app/dist /usr/share/nginx/html 

#expose port 80 *nginx default 
EXPOSE 80

#start nginx 
CMD [ "nginx", "-g", "daemon off;"]