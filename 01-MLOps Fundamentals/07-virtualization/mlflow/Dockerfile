FROM python:3.9-slim

LABEL maintainer="vuvanthanhtb"
LABEL organization="mlopsvn"

WORKDIR /mlflow/

ARG MLFLOW_VERSION

RUN apt-get update -y
RUN apt-get install -y iputils-ping
RUN pip install --no-cache-dir mlflow==${MLFLOW_VERSION} psycopg2-binary

EXPOSE 5000

# Ref: https://github.com/mlflow/mlflow/issues/6274#issuecomment-1196106372
CMD mlflow server \
    --backend-store-uri ${BACKEND_STORE_URI} \ 
    --serve-artifacts \
    --host 0.0.0.0 \
    --port 5000

# docker build -t before_msb -f mlflow/Dockerfile --build-arg MLFLOW_VERSION=2.3.2 mlflow
# docker run before_msb
# docker exec -ti before_msb bash
# docker run -d --name mlflow -p 5000:5000 before_msb