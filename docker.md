# Docker

## Verifier les configurations d'un docker-compose.yml
```shell
docker compose config
```
Cela va interpreter le .env pour lire le docker-compose.yml
## Relocalisation du répertoire /vat/lib/docker

_**Problème d'espace disque avec Docker**_   

J'ai dû déplacer ma librairie docker (/vat/lib/docker) car je n'avais plus d'espace sur ma partition.  
Voici la procédure que j'ai mis en place :
```shell
# arrêt du service docker
systemctl stop docker

# déplacement du répertoire 
mv /var/lib/docker ${DESTINATION}/

# creation du lien symbolique
ln -s ${DESTINATION}/docker/ /var/lib/

# redémarage du service docker
systemctl start docker
```
Merci la source :ocean:  
Source : https://unix.stackexchange.com/questions/414483/docker-increase-available-disk-space
