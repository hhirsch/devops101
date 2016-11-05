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

>Extract the data from pkcs12 encoded files.

```
openssl pkcs12 -in domain.pfx -clcerts -nokeys -out domain.cer openssl pkcs12 -in domain.pfx -nocerts -nodes -out domain.key
```
