## Multi stage build

### Before

```bash
docker build -t before_msb -f mlflow/Dockerfile --build-arg MLFLOW_VERSION=2.3.2 mlflow && docker run -p 5000:5000 before_msb
```

### After

```bash
docker build -t after_msb -f mlflow/Dockerfile-multistage-build --build-arg MLFLOW_VERSION=2.3.2 mlflow && docker run -p 5000:5000 after_msb
```

## Docker Compose

- Up and running MLFlow application with Docker Compose
  ```shell
  docker compose -f mlflow-docker-compose.yaml up -d
  ```
- Similarly, you can do it for Trino
  ```shell
  docker compose -f trino-docker-compose.yaml up -d
  ```

## .env
```
POSTGRES_HOST=localhost
POSTGRES_PORT=5432
POSTGRES_DB=mlflowdb
POSTGRES_USER=mlopsvn
POSTGRES_PASSWORD=mlopsvn

BACKEND_STORE_URI=postgresql://${POSTGRES_USER}:${POSTGRES_PASSWORD}@${postgresql}:${POSTGRES_PORT}/${POSTGRES_DB}
MLFLOW_VERSION=2.3.2
```
