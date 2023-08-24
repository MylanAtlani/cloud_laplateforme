# Utiliser l'Image Docker avec Minikube

Pour lancer l'image générée par le Dockfile dans un cluster, suivre les étapes suivantes :

## Prérequis

- Docker installé sur votre machine.
- minikube installé
```bash
sudo apt install minikube 
```
- kubectl installé
```bash
sudo snap install kubectl --classic 
```
## Lancement du cluster

 Dans le répertoire contenant le `Dockerfile`, exécutez :
   
```bash
minikube start
```
## Configuration de l'environnement docker

```bash
eval $(minikube docker-env)
```

## Build de l'image précédement générée par le Dockfile

```bash
docker build -t debian-ssh .
```
## Lancement de l'image dans minikube
On utilise la commande `kubectl` pour interagir avec le cluster.

L'option `--image` donne le nom de l'image docker build en local.

L'option ` --image-pull-policy=Never` empeche le téléchargement de l'image et force l'utilisation de l'image local (générée par le Dockerfile).

```bash
kubectl run nomDuDeploiement --image=debian-ssh --image-pull-policy=Never
```

## Test que l'image tourne
Cet commande retourne l'etat du container dans le cluster. Il doit etre `running `.
```bash
kubectl get pods
```

## Lancement du Dashboard minikub
```bash
minikube dashboard --url
```
