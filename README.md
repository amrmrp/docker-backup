# docker-backup
 
#### declare example volume 
```
docker create volume hello
```


#### docker backup volume and mount path $(pwa)
 ```
back up volume docker 
docker run --rm -v hello:/data -v $(pwd):/backup debian:jessie tar czvf /backup/hello_backup.tar.gz -C /data .
```

#### docker backup volume 
```
docker run --rm -v hello:/data debian:jessie tar czvf /backup/hello_backup.tar.gz -C /data .
```

