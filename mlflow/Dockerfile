FROM python:3.7.0-stretch
ENV MLFLOW_SERVER_HOST 0.0.0.0
ENV MLFLOW_S3_ENDPOINT_URL http://minio:9000
ENV AWS_ACCESS_KEY_ID=minio_access_key
ENV AWS_SECRET_ACCESS_KEY=minio_secret_key
ENV MLFLOW_SERVER_DEFAULT_ARTIFACT_ROOT=s3://minio/artifacts

WORKDIR /

COPY . /

RUN apt-get update
RUN pip install -r requirements.txt

ENTRYPOINT ["./startup.sh"]