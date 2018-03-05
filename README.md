Generate public and private keys

```
openssl genrsa -out keypair.pem 2048
openssl rsa -in keypair.pem -out public.pem -outform PEM -pubout
```

Sign the file 

```
openssl dgst -sha256 -sign keypair.pem -out O7yLqqq.sha256 O7yLqqq.jpg
```

Encode in base64

```
openssl base64 -in O7yLqqq.sha256 -out O7yLqqq.signature
```

Decode from base64
```
openssl base64 -d -in O7yLqqq.signature -out O7yLqqq.sha256
```

Verify signature
```
openssl dgst -sha256 -verify public.pem -signature O7yLqqq.sha256 O7yLqqq.jpg
```

NOTE: never share your private key!!!