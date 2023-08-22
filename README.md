# Image Docker avec SSH sur Debian

Cette image Docker contient une installation Debian avec un serveur SSH configuré pour un accès simplifié. Elle est destinée à des fins de démonstration et de développement.

## Prérequis

- Docker installé sur votre machine.

## Construction de l'image

 Dans le répertoire contenant le `Dockerfile`, exécutez :
   
```bash
docker build -t debian-ssh .
```
## Exécution du conteneur
Lancez un conteneur basé sur l'image :

```bash
docker run -d -p 2222:22 debian-ssh
```

## Connexion via SSH

Une fois le conteneur en cours d'exécution, connectez-vous via SSH en utilisant le port 2222 :

```bash
ssh root@localhost -p 2222
```

Mot de passe: rootpassword
