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

## Ajouter un Runner dans un réseau docker existant
Lors de l'exécution d'un job le runner sera déployer dans un réseau isolé.  
Voici comment on le relit à un réseau docker existant :
- Éditez le fichier à l'emplacement `/etc/gitlab-runner/config.toml`
- Ajoutez la ligne suivante dans `[runners.docker]`  
```shell
  network_mode = "<MON_RESEAU_DOCKER>"
```

Merci la source :ocean:  
Source : https://gitlab.com/gitlab-org/gitlab-runner/-/issues/1846