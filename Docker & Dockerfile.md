# Lecture : Revue des concepts Docker et compréhension d'un Dockerfile
Temps estimé nécessaire : 30 minutes

Cette lecture est conçue pour améliorer votre compréhension des concepts de Docker et vous guider à travers le processus de compréhension d'un Dockerfile.

## Aperçu de la lecture :
- Concepts Docker
- Comprendre un Dockerfile

## Concepts Docker
### Aperçu
Docker simplifie le processus de création, de déploiement et de gestion des applications en utilisant des conteneurs. Les conteneurs vous permettent d'emballer une application avec ses dépendances dans une unité standardisée pour le développement logiciel. Docker fournit des outils et une plateforme pour construire, expédier et exécuter des conteneurs dans divers environnements.

### Dockerfile
Un fichier texte qui contient des instructions pour construire une image Docker. Il spécifie l'image de base, définit le répertoire de travail, installe les dépendances, copie le code de l'application, expose des ports et définit les commandes à exécuter pour l'application.

### Conteneur
Une instance d'une image Docker qui s'exécute comme un processus sur la machine hôte. Les conteneurs sont légers, portables et isolés, ce qui les rend idéaux pour déployer et mettre à l'échelle des applications.

### Stockage des images Docker
Les images Docker sont stockées dans des registres, qui peuvent être publics ou privés. Les registres publics comme Docker Hub hébergent des millions d'images, tandis que les organisations utilisent souvent des registres privés pour des raisons de sécurité et de contrôle.

### Où se trouvent les images Docker
Machine locale : Lorsque vous construisez une image Docker, elle est initialement stockée localement sur votre machine. Vous pouvez lister les images Docker locales en utilisant la commande docker images.

Registre : Après avoir construit, vous pouvez pousser des images Docker vers un registre, les rendant accessibles de n'importe où ayant accès à ce registre.

### Dockerfile
Voici un exemple de Dockerfile pour référence. L'explication qui suit détaille les commandes utilisées, offrant une compréhension complète de la manière d'écrire un Dockerfile.

## Dockerfile
### Comprendre le Dockerfile
#### 1: Spécifiez l'image de base
Pour commencer, spécifiez l'image de base en utilisant l'instruction FROM. Dans ce cas, l'image officielle de Node.js version 14 est utilisée.

```
FROM node:14
```


FROM: Spécifie l'image de base pour le conteneur Docker.
node:14: Récupère l'image officielle de Node.js avec la version 14 depuis le registre Docker.

#### 2 : Définir les variables d'environnement
Ensuite, définissez les variables d'environnement nécessaires avec l'instruction ENV. Ici, NODE_ENV est défini sur production et PORT est défini sur 3000.

```
ENV NODE_ENV=production
ENV PORT=3000
```


ENV: Définit les variables d'environnement à l'intérieur du conteneur Docker.
NODE_ENV=production: Définit l'environnement Node.js sur production.
PORT=3000: Définit le port sur lequel l'application Node.js écoutera.

#### 3 : Définir le Répertoire de Travail
Ensuite, spécifiez le répertoire de travail à l'intérieur du conteneur en utilisant l'instruction WORKDIR. Cela définit /app comme répertoire de travail.

```
WORKDIR /usr/src/app
```


WORKDIR: Définit le répertoire de travail pour les instructions suivantes, simplifiant les références de chemin de fichier.
/usr/src/app: Le répertoire à l'intérieur du conteneur pour stocker le code de votre application, le gardant organisé et facilement accessible.

#### 4 : Copier les fichiers du package
Après avoir défini le répertoire de travail, utilisez l'instruction COPY pour copier les fichiers package.json et package-lock.json dans le conteneur. Ces fichiers sont essentiels pour installer les dépendances de l'application.

```
COPY package*.json ./
```


COPY: Copie des fichiers de votre machine locale vers le conteneur.
package*.json ./: Copie à la fois les fichiers package.json et package-lock.json.

#### 5: Installer les dépendances
Avec les fichiers de package copiés, exécutez l'instruction RUN pour installer les dépendances de production listées dans package.json.

```
RUN npm install --production
```


RUN : Exécute des commandes dans le conteneur pendant le processus de construction.
npm install –production : Installe les dépendances listées dans package.json sans les devDependencies.

#### 6 : Copier le code de l'application
Une fois les dépendances installées, copiez le reste du code de l'application dans le conteneur en utilisant l'instruction COPY.

```
COPY . .
```


COPY . .: Copie tous les fichiers et répertoires du répertoire actuel sur l'hôte local vers le répertoire actuel dans le conteneur Docker.

#### 7 : Ajouter des fichiers supplémentaires
De plus, utilisez l'instruction ADD pour inclure tout fichier supplémentaire. Ici, le fichier index.html est ajouté au répertoire public.

```
# ADD <source_path> <destination_path>
ADD public/index.html /app/public/index.html
```


public/index.html: Chemin vers le fichier ou le répertoire sur la machine hôte.
/app/public/index.html: Chemin où vous souhaitez ajouter le fichier ou le répertoire à l'intérieur de l'image Docker.

#### 8 : Exposer le port de l'application
Ensuite, informez Docker que le conteneur écoute sur le port spécifié avec l'instruction EXPOSE. Ici, il expose le port défini par la variable d'environnement PORT.

```
EXPOSE $PORT
```


EXPOSE: Informe Docker que le conteneur écoutera sur le port spécifié à l'exécution.
$PORT: La variable d'environnement représentant le numéro de port défini précédemment.

#### 9 : Spécifier la Commande par Défaut
Définissez la commande par défaut à exécuter lorsque le conteneur démarre en utilisant l'instruction CMD. Ici, elle exécute node app.js.

```
CMD ["node", "app.js"]
```


CMD: Cette instruction spécifie la commande par défaut et/ou les paramètres à exécuter au point d'entrée du conteneur.
["node", "app.js"]: Ce tableau spécifie la commande à exécuter et tout argument pour cette commande. Dans ce cas, il indique à Docker d'exécuter la commande node avec app.js comme argument.

Note : Le nom de fichier app.js est couramment utilisé comme fichier principal pour les applications Node.js. Cependant, en fonction de la structure de votre projet ou des conventions de nommage, le fichier principal pourrait avoir un nom différent.

#### 10 : Étiqueter l'image
Ensuite, ajoutez des métadonnées à l'image avec l'instruction LABEL, y compris la version, la description et les informations sur le mainteneur.

```
LABEL version="1.0"
LABEL description="Node.js application Docker image"
LABEL maintainer="Your Name"
```


LABEL: Ajoute des métadonnées à l'image Docker.
version="1.0": Spécifie la version de l'image Docker.
description="Node.js application Docker image" : Fournit une description de l'image Docker.
maintainer="Your Name": Spécifie le mainteneur de l'image Docker.

#### 11 : Ajouter un Healthcheck
Pour s'assurer que le conteneur fonctionne correctement, définissez un health check en utilisant l'instruction HEALTHCHECK. Cette commande vérifie la santé de l'application en envoyant une requête au port spécifié.

```
HEALTHCHECK --interval=30s --timeout=10s --start-period=5s --retries=3 CMD curl -fs http://localhost:$PORT || exit 1
```


HEALTHCHECK: Configure une vérification de l'état pour s'assurer que le conteneur fonctionne correctement.
--interval=30s: Spécifie l'intervalle entre les vérifications de l'état.
--timeout=10s: Définit le délai d'attente pour chaque vérification de l'état.
--start-period=5s: Définit la période de démarrage pendant laquelle le conteneur doit s'initialiser avant que les vérifications de l'état ne commencent.
--retries=3: Définit le nombre de tentatives avant de considérer le conteneur comme non sain.
CMD curl -fs http://localhost:$PORT || exit 1: Spécifie la commande à exécuter pour les vérifications de l'état. Elle vérifie si une requête à http://localhost:$PORT réussit ; sinon, elle quitte avec le code 1, indiquant un échec.

#### 12 : Définir un utilisateur non-root
Enfin, pour des raisons de sécurité, définissez un utilisateur non-root avec l'instruction USER. Ici, l'utilisateur est défini sur node.

```
USER node
```


USER: Définit l'utilisateur qui exécutera les instructions suivantes dans le Dockerfile.
node: Spécifie l'utilisateur nommé node pour exécuter les commandes pour des raisons de sécurité.

Cette explication étape par étape montre le flux de création d'un Dockerfile, mettant en évidence comment chaque instruction s'appuie sur la précédente pour créer une image Docker entièrement fonctionnelle.

## Résumé
Dans cette lecture, vous avez appris les concepts de Docker et le processus de création d'un Dockerfile. Le Dockerfile fourni et les étapes décrites démontrent comment construire une image Docker pour une application Node.js. Il commence par l'image de base officielle de Node.js, configure les variables d'environnement, définit un répertoire de travail et installe les dépendances nécessaires. Le code de l'application est ensuite copié dans le conteneur, et un contrôle de santé est inclus pour s'assurer que le conteneur fonctionne correctement. Enfin, un utilisateur non-root est défini pour une sécurité accrue.
