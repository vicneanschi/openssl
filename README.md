Generate public and private keys

```
openssl genrsa -out keypair.pem 2048
openssl rsa -in keypair.pem -out public.pem -outform PEM -pubout
```

Sign the file 

```
openssl dgst -sha256 -sign keypair.pem -out file.signature O7yLqqq.jpg
```

Verify signature
```
openssl dgst -sha256 -verify public.pem -signature file.signature O7yLqqq.jpg
```

NOTE: never share your private key!!!