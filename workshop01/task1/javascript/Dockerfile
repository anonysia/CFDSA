FROM node:17
## build

ARG APP_DIR=/app 

WORKDIR ${APP_DIR}

#copy files from local into image
ADD main.js .
ADD package.json .
ADD package-lock.json .
ADD public public
ADD views views

# install dependencies
RUN npm ci 

## run
ENV APP_DIR=/app 
ENV PORT=3000

# what are the required ports
EXPOSE ${PORT}

#WORKDIR $(APP_DIR}

#HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
#   CMD curl http://localhost:${PORT}/healthz || exit 1


#run the application
ENTRYPOINT [ "node", "main"]

#CMD [ "--port", "3000"]