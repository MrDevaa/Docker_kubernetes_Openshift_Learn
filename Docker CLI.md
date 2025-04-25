# Fiche de Référence Docker CLI

## Commandes Docker

- `docker build` : Construit une image à partir d'un Dockerfile.
- `docker build . -t <image:tag>` : Construit l'image et tague l'identifiant de l'image.
- `docker images` : Liste les images présentes localement.
- `docker ps` : Liste les conteneurs en cours d'exécution.
- `docker ps -a` : Liste tous les conteneurs, y compris ceux arrêtés.
- `docker run <image>` : Exécute une commande dans un nouveau conteneur.
- `docker run -p <host_port>:<container_port> <image>` : Exécute le conteneur en publiant les ports.
- `docker stop <container>` : Arrête un ou plusieurs conteneurs en cours d'exécution.
- `docker stop $(docker ps -q)` : Arrête tous les conteneurs en cours d'exécution.
- `docker container rm <container>` : Supprime un ou plusieurs conteneurs.
- `docker pull <image>` : Télécharge une image depuis un registre.
- `docker push <image>` : Envoie une image vers un registre.
- `docker tag <image> <repo/image:tag>` : Crée une étiquette pour une image cible.
- `docker --version` : Affiche la version de Docker CLI.

## Commandes complémentaires

- `curl localhost` : Pingue l'application.
- `exit` : Ferme la session du terminal.
- `ls` : Liste le contenu du répertoire courant.
- `export MY_NAMESPACE=xxx` : Définit une variable d'environnement.
- `git clone <repo>` : Clone un dépôt git.

## IBM Cloud Container Registry

- `ibmcloud cr login` : Connecte Docker local au registre IBM Cloud.
- `ibmcloud cr images` : Liste les images dans le registre IBM Cloud.
- `ibmcloud cr namespaces` : Affiche les espaces de noms accessibles.
- `ibmcloud cr region-set <region>` : Définit la région cible.
- `ibmcloud target` : Affiche les informations du compte ciblé.
- `ibmcloud version` : Affiche la version de l'IBM Cloud CLI.
