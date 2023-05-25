# Certificats SSL

## Générer un certificat auto-signé
```shell
openssl genrsa -out server.key 2048
openssl rsa -in server.key -out server.key
openssl req -sha256 -new -key server.key -out server.csr -subj '/CN=localhost'
openssl x509 -req -sha256 -days 365 -in server.csr -signkey server.key -out server.crt
```

Pour les combinées dans un .pem
```shell
cat server.crt server.key > cert.pem
```


Merci la source :ocean:  
Source : https://stackoverflow.com/questions/10175812/how-to-generate-a-self-signed-ssl-certificate-using-openssl
