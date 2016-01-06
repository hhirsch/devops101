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
awk 'FNR==1{print ""}1' *.crt >> chained.crt
```
