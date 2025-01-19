# docker-backup
 
#### declare example volume 
```
docker create volume hello
```

---
#### docker backup volume and mount path $(pwa)
 ```
back up volume docker 
docker run --rm -v hello:/data -v $(pwd):/backup debian:jessie tar czvf /backup/hello_backup.tar.gz -C /data .
```
#### docker backup volume 
```
docker run --rm -v hello:/data debian:jessie tar czvf /backup/hello_backup.tar.gz -C /data .
```
#### docker restore volume 
###### step1
```
docker volume create new_volume_name
```
##### step2
```
docker run --rm -v new_volume_name:/data -v $(pwd):/backup busybox sh -c "cd /data && tar xzvf /backup/my_volume_backup.tar.gz"
```

---
#### docker image backup
```
docker save -o my_image_backup.tar my_image_name
```
#### docker image restore
```
docker load -i my_image_backup.tar
```



---
#### docker container backup 
```
docker export my_container_name > my_container_backup.tar
```

#### docker container restore 
```
docker import my_container_backup.tar my_new_container_image
```
---



