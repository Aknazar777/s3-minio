# S3-minio

## Dev
1. Create ssl in namespace minio-dev
2. Create DNS name in path: /

| Service | DNS |
| ------ | ------ |
| minio | sme-s3-dev.p-s.kz |
| minio-console | sme-s3-console-dev.p-s.kz |

3. Root password in secret minio-root in namespace: minio-dev
4. Create user for service with console
5. Create bucket
6. If need HA, need change mode in dev.yml. Now mode: standalone.





## PROD
```sh
kubectl label nodes minio1 storage=minio
kubectl label nodes minio2 storage=minio
kubectl label nodes minio3 storage=minio
kubectl label nodes minio4 storage=minio
kubectl get nodes  --show-labels
```

1. Create ssl in namespace minio-prod
2. Create DNS name in path: /

| Service | DNS |
| ------ | ------ |
| minio | s3.prime-cloud.kz |
| minio-console | s3-console.prime-cloud.kz |

3. Root password in secret minio-root in namespace: minio-prod
4. Create user for service with console
5. Create bucket
6. mode: gateway. Replica: 4
