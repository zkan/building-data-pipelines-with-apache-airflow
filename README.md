# Building Data Pipelines with Apache Airflow

## Starting Airflow

```sh
mkdir -p mnt/dags mnt/logs mnt/plugins
echo -e "AIRFLOW_UID=$(id -u)" > .env
docker-compose up
```

## Airflow S3 Connection to MinIO

- Connection Name: `minio` or any name you like
- Connection Type: S3
- Login: `<replace_here_with_your_minio_access_key>`
- Password: `<replace_here_with_your_minio_secret_key>`
- Extra: a JSON object with the following properties:
  ```json
  {
    "host": "http://minio:9000"
  }
  ```
