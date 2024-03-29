# Docker

## Secret Docker
**Les secrets Docker fonctionne uniquement en mode Swarm.**  
_Voir les notes sur Docker Swarm_
### Géneration
```shell
# Générer un secret depuis une chaîne de caractères
printf "${MON_SECRET}" | docker secret create ${NOM_DU_SECRET} -
# Générer un secret depuis un fichier
docker secret create ${NOM_DU_SECRET} ${PATH_DU_FICHIER}
```
### Localisation des fichiers de secret
`/run/secrets/<NOM_DU_SECRET>`

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
