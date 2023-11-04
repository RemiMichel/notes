# Docker Compose

## Communication entre conteneur
### Réseaux
Afin que plusieurs projets issus de plusieurs docker-compose puisse communiquer entre eux, ils doivent tout se trouver dans le meme réseaux.
Créez en premier le réseau via docker
```shell
docker network create ${NOM_DE_MON_RESEAU}
```
Attribuer le réseau dans les docker-compose.yml concernés comme ceci :
```yaml
services:
  service:
    image: ...
    networks:
      - mon_network

networks:
  mon_network:
    external: true
```

## .ENV et Compose
Le fichier `.env` est automatiquement interprété lors du `docker compose up`, s'il se trouve au meme endroit que le fichier `docker-compose.yml`

## Verifier les configurations d'un docker-compose.yml
```shell
docker compose config
```
Cela va interpreter le .env pour lire le docker-compose.yml