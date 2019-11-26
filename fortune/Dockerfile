FROM node:latest

#set env variable
ENV APP_ROOT=/app
ENV APP_PORT=3000

#create dir and cd in
WORKDIR ${APP_ROOT}

#copy the files into the image
#files will be copied into /app
ADD main.js .
ADD package.json .
ADD public public
ADD views views

#run commands
RUN npm install

#how an image is provision/run - execution
#what port our container will expose
EXPOSE ${APP_PORT}

#add health check to the application
HEALTHCHECK --interval=30s --timeout=30s --retries=3 \
	CMD -f http://localhost:${APP_PORT}/health > /dev/null || exit 1

ENTRYPOINT ["node","main.js"]
CMD [""]

