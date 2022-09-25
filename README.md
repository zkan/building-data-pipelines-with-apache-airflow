# Building Data Pipelines with Apache Airflow

## Starting Airflow

```sh
mkdir -p mnt/dags mnt/logs mnt/plugins
echo -e "AIRFLOW_UID=$(id -u)" > .env
docker-compose up
```

## Airflow S3 Connection to MinIO

Since MinIO offers S3 compatible object storage, we can set the connection type to S3. However, we'll need to set an extra option, so that Airflow connects to MinIO instead of S3.

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
