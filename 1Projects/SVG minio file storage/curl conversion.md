# 1. getting the different SVG files in the storage

#### library call
```bash
curl --silent --location 'https://api.dev.apps.yokogawa.build/vis-file-svc/v1/resource/' \
--header "$AUTH_HEADER"
```

#### MINIO call
```bash

```


---

> MINIO makes use of websockets for the data transfer
> bash does not have any native support for the use of websockets
> the only way is to make use of MINIO CLI client - MC


# MINIO CLI client (MC)
#### installing MC
```bash
curl https://dl.min.io/client/mc/release/linux-amd64/mc -o mc
chmod +x mc
sudo mv mc /usr/local/bin/
```
this will install the MC onto the system

#### configuring the client
```bash
mc alias set myminio https://your-minio-url ACCESSKEY SECRETKEY
```
- ==this is the part which we need to look after==
- this required us to provide the access key and the secret key while the installation of the tool itself
	- not feasible due to this script being run on different places