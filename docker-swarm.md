# Docker Swarm

Contrairement à Compose qui va communiquer directement avec Docker Engine, le Swarm est une couche supplémentaire entre Docker et Compose.

## Initialisé un swarm
```shell
docker swarm init --advertise-addr 127.0.0.1
```
## Network
SEULEMENT les réseaux de type Overlay sont disponibles pour le Swarm.
```shell
docker network create --driver overlay ${NOM_DU_RESEAU}
```
## Volumes
Les volumes montés en relatif ne fonctionnent pas ` ./myfolder:/var/run/docker-folder`.
Privilégier les montages externes ou de cette sorte :
```yaml
services:
  mon-service:
    image: ...
    volumes:
      - mon-volume:/chemin/dossier

volumes:
  mon-volume:
```