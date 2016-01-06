# devops101

## SSL
>Create PK.

```
openssl genrsa -out yourdomain.key 2048
```

>Create CSR.

```
openssl req -new -newkey rsa:2048 -nodes -keyout yourdomain.key -out yourdomain.csr
```

>Concat Certificates

```
cat certificate.crt <(echo) intermediate.crt <(echo) root.crt > chained.crt
```
