# Fiche de Référence : Introduction aux Conteneurs avec Docker, Kubernetes et OpenShift
---

## Docker CLI

| Commande                                 | Description                                                                                  |
|-------------------------------------------|----------------------------------------------------------------------------------------------|
| `curl localhost`                         | Pinge l'application.                                                                         |
| `docker build`                           | Construit une image Docker à partir d'un Dockerfile spécifié.                                |
| `docker build . -t`                      | Construit l'image et tague l'id de l'image.                                                  |
| `docker CLI`                             | Démarre l'interface de ligne de commande Docker (CLI).                                       |
| `docker container rm`                    | Supprime un conteneur.                                                                       |
| `docker images`                          | Affiche une liste de toutes les images Docker disponibles.                                   |
| `docker ps`                              | Liste les conteneurs.                                                                        |
| `docker ps -a`                           | Liste les conteneurs qui ont été exécutés et ont quitté avec succès.                         |
| `docker pull`                            | Télécharge la dernière image ou le dépôt depuis un registre.                                 |
| `docker push`                            | Pousse une image ou un dépôt vers un registre.                                               |
| `docker run`                             | Exécute une commande dans un nouveau conteneur.                                              |
| `docker run -p`                          | Exécute le conteneur en publiant les ports.                                                  |
| `docker stop`                            | Arrête un ou plusieurs conteneurs en cours d'exécution.                                      |
| `docker stop $(docker ps -q)`            | Arrête tous les conteneurs actuellement en cours d'exécution.                                |
| `docker tag`                             | Crée une balise pour une image cible qui fait référence à une image source.                  |
| `docker --version`                       | Affiche la version de la CLI Docker.                                                         |
| `exit`                                   | Ferme la session du terminal.                                                                |
| `export MY_NAMESPACE`                    | Exporte un espace de noms en tant que variable d'environnement.                              |
| `git clone`                              | Clone le dépôt git contenant les artefacts nécessaires.                                      |
| `ibmcloud cr images`                     | Liste les images dans le registre de conteneurs IBM Cloud.                                   |
| `ibmcloud cr login`                      | Connecte votre démon Docker local au registre de conteneurs IBM Cloud.                       |
| `ibmcloud cr namespaces`                 | Affiche les espaces de noms disponibles pour l'utilisateur actuel dans le registre IBM Cloud.|
| `ibmcloud cr region-set`                 | Assure que vous ciblez la région appropriée pour votre compte cloud.                         |
| `ibmcloud target`                        | Fournit des informations sur le compte que vous ciblez.                                      |
| `ibmcloud version`                       | Affiche la version actuelle de la CLI IBM Cloud.                                             |
| `ls`                                     | Liste les fichiers et répertoires dans le répertoire courant.                                |

---

## Comprendre l’Architecture Kubernetes

| Commande                      | Description                                                                                   |
|-------------------------------|-----------------------------------------------------------------------------------------------|
| `for …do`                     | Exécute une séquence de commandes plusieurs fois comme spécifié.                              |
| `kubectl apply`               | Applique une configuration spécifiée à une ressource.                                         |
| `kubectl config get-clusters` | Affiche tous les clusters définis dans le kubeconfig.                                         |
| `kubectl config get-contexts` | Affiche le contexte actuel.                                                                   |
| `kubectl create`              | Crée une nouvelle ressource Kubernetes basée sur une spécification donnée.                    |
| `kubectl delete`              | Supprime des ressources.                                                                      |
| `kubectl describe`            | Fournit des détails sur une ressource ou un groupe de ressources.                             |
| `kubectl expose`              | Expose une ressource à Internet en tant que service Kubernetes.                               |
| `kubectl get`                 | Affiche les ressources.                                                                       |
| `kubectl get pods`            | Liste tous les Pods.                                                                          |
| `kubectl get pods -o wide`    | Liste tous les Pods avec des détails.                                                         |
| `kubectl get deployments`     | Affiche tous les déploiements créés.                                                          |
| `kubectl get services`        | Liste les services créés.                                                                     |
| `kubectl proxy`               | Crée un serveur proxy entre un localhost et le serveur API Kubernetes.                        |
| `kubectl run`                 | Crée et exécute une image particulière dans un pod.                                           |
| `kubectl version`             | Affiche les informations de version du client et du serveur.                                  |

---

## Gestion des Applications avec Kubernetes

| Commande                           | Description                                                     |
|------------------------------------|-----------------------------------------------------------------|
| `kubectl autoscale deployment`     | Auto-redimensionne un déploiement Kubernetes.                   |
| `kubectl create configmap`         | Crée une ressource ConfigMap.                                   |
| `kubectl get deployments -o wide`  | Liste les déploiements avec des détails.                        |
| `kubectl get hpa`                  | Liste les Autoscalers de Pods Horizontaux (hpa).                |
| `kubectl scale deployment`         | Redimensionne un déploiement.                                   |
| `kubectl set image deployment`     | Met à jour le déploiement actuel.                               |
| `kubectl rollout`                  | Gère le déploiement d'une ressource.                            |
| `kubectl rollout restart`          | Redémarre la ressource afin que les conteneurs redémarrent.     |
| `kubectl rollout undo`             | Rétablit la ressource.                                          |

---

## OpenShift CLI

| Commande         | Description                        |
|------------------|------------------------------------|
| `oc get`         | Affiche une ressource.             |
| `oc project`     | Change de projet.                  |
| `oc version`     | Affiche les informations de version.|

