![docker-publish-to-dh](https://github.com/swaglive/docker-openresty/workflows/docker-publish-to-dh/badge.svg)

## Running

Example
```
docker run -it --rm --cap-add SYS_ADMIN --device /dev/fuse -v "$(pwd)/gcs.json:/gcs.json:ro" -e "GCSFUSE_OPTIONS=--key-file /gcs.json" -e GOOGLE_CLOUD_STORAGE_BUCKET=mybucket 17media/openresty:gcs
```
