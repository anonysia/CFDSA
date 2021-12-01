FROM python:latest
## build

ARG APP_DIR=/app

WORKDIR ${APP_DIR}

#copy files from local into image
ADD main.py .
ADD run.sh .
ADD static static
ADD templates templates

# install dependencies

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt


## run
ENV APP_DIR=/app
ENV PORT=3000

# what are the required ports
EXPOSE ${PORT}

#WORKDIR $(APP_DIR}

#run the application
#ENTRYPOINT [ "python3", "main.py"]
ENTRYPOINT [ "./run.sh"]

#CMD [ "--port", "3000"]