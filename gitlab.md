# Gitlab
## Réinitialiser le mot de passe root
```shell
gitlab-rake "gitlab:password:reset[root]"
```
Apres un petit moment (environ 30 secondes, 1 minute) le prompt vous invitera à entrer puis confirmer le nouveau mot de passe.
### Avec Docker
Enter dans le conteneur avant de jouer la commande précédente
```shell
# RAPPEL : Entrer dans le conteneur
docker exec -it <GITLAB_INSATNCE> bash
```
Merci la source :ocean:  
Source : https://stackoverflow.com/questions/55747402/docker-gitlab-change-forgotten-root-password