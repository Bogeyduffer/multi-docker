# First phase of the "nginx build" process
FROM node:16-alpine as builder
#create the working directory
WORKDIR "/app"

# add json packages from local
COPY ./package.json ./

# pull all dependences
RUN npm install

# add everything inside the current direcotry to the app directory 
COPY . . 

# Build the container
RUN npm run build

# Second phase of the "nginx build" process
FROM nginx

# Instruction to AWS to expost the port of the container
EXPOSE 3000

# Copy over the config ".conf" file to be used (replaces the defaul file in nginx)
COPY ./nginx/default.conf etc/nginx/conf.d/default.conf

# Copy the first phase build assets
COPY --from=builder /app/build /usr/share/nginx/html