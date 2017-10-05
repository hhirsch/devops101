# Devops 101

## SSL
### Create PK.

```
openssl genrsa -out yourdomain.key 2048
```

### Create CSR.

```
openssl req -new -newkey rsa:2048 -nodes -keyout yourdomain.key -out yourdomain.csr
```

### Concat Certificates

```
cat certificate.crt <(echo) intermediate.crt <(echo) root.crt > chained.crt
```

Without root certificate
```
cat certificate.crt <(echo) intermediate.crt > chained.crt  
```
### Extract the data from pkcs12 encoded files.

```
openssl pkcs12 -in domain.pfx -clcerts -nokeys -out domain.cer openssl pkcs12 -in domain.pfx -nocerts -nodes -out domain.key
```

### Create self signed SSL certificate

```
openssl req -subj '/CN=domain.com/O=My Company Name LTD./C=US' -new -newkey rsa:2048 -days 365 -nodes -x509 -keyout server.key -out server.crt
```
