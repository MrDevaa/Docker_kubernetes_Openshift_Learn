# Introduction à Kubernetes - Laboratoire

## Objectifs
Dans ce laboratoire, vous allez :
- Utiliser l’interface en ligne de commande `kubectl`.
- Créer un Pod Kubernetes.
- Créer un Déploiement Kubernetes.
- Créer un ReplicaSet qui maintient un nombre fixe de réplicas.
- Observer l’équilibrage de charge de Kubernetes en action.

## Tâche N°1 : Vérifier l'environnement et les outils de ligne de commande

1. Dans le terminal, vérifiez votre version de `kubectl` :
    ```bash
    kubectl version
    ```

2. Clonez le projet template de codage de IBM :
    ```bash
    [ ! -d 'CC201' ] && git clone https://github.com/ibm-developer-skills-network/CC201.git
    ```

3. Changez de répertoire pour ce laboratoire :
    ```bash
    cd CC201/labs/2_IntroKubernetes/
    ```

4. Listez le contenu de ce répertoire pour voir les artefacts du laboratoire :
    ```bash
    ls
    ```

## Tâche N°2 : Utiliser le CLI kubectl

1. `kubectl` nécessite une configuration pour cibler le cluster approprié. Obtenez des informations sur le cluster avec la commande suivante :
    ```bash
    kubectl config get-clusters
    ```

2. Un contexte `kubectl` est un groupe de paramètres d’accès, incluant un cluster, un utilisateur et un espace de noms. Affichez votre contexte actuel avec la commande suivante :
    ```bash
    kubectl config get-contexts
    ```

3. Listez tous les Pods dans votre espace de noms. Si c’est une nouvelle session pour vous, vous ne verrez aucun Pod :
    ```bash
    kubectl get pods
    ```

## Tâche N°3 : Créer un Pod avec une commande impérative

1. Exporte votre espace de noms en tant que variable d’environnement afin de l’utiliser dans les commandes suivantes :
    ```bash
    export MY_NAMESPACE=sn-labs-$USERNAME
    ```

2. Utilisez l'Explorateur pour naviguer jusqu’au fichier Dockerfile dans le répertoire pour ce laboratoire. C'est le fichier utilisé pour construire l’image.

3. Construisez et poussez à nouveau l’image (car elle peut avoir été supprimée) :
    ```bash
    docker build -t us.icr.io/$MY_NAMESPACE/hello-world:1 . && docker push us.icr.io/$MY_NAMESPACE/hello-world:1
    ```

4. Exécutez l’image `hello-world` en tant que conteneur dans Kubernetes :
    ```bash
    kubectl run hello-world --image us.icr.io/$MY_NAMESPACE/hello-world:1 --overrides='{"spec":{"template":{"spec":{"imagePullSecrets":[{"name":"icr"}]}}}}'
    ```

5. Listez les Pods dans votre espace de noms :
    ```bash
    kubectl get pods
    ```

6. Décrivez le Pod pour obtenir plus de détails :
    ```bash
    kubectl describe pod hello-world
    ```

7. Supprimez le Pod :
    ```bash
    kubectl delete pod hello-world
    ```

## Tâche N°4 : Créer un Pod avec une configuration d'objet impérative

1. Utilisez l’Explorateur pour visualiser et modifier le fichier de configuration `hello-world-create.yaml`. Changez `<my_namespace>` par votre espace de noms.

2. Créez un Pod à partir de ce fichier de configuration :
    ```bash
    kubectl create -f hello-world-create.yaml
    ```

3. Listez puis supprimez le Pod. Vérifiez qu’il n’y a plus de ressources ni de Namespace :
    ```bash
    kubectl get pods
    kubectl delete pod hello-world
    ```

## Tâche N°5 : Créer un Pod avec une commande déclarative

1. Utilisez l’Explorateur pour ouvrir le fichier `hello-world-apply.yaml`. Ce fichier crée un Déploiement avec trois réplicas du Pod `hello-world`.

2. Modifiez le fichier pour insérer votre `namespace` dans `<my_namespace>` et sauvegardez-le.

3. Appliquez la configuration déclarative à Kubernetes :
    ```bash
    kubectl apply -f hello-world-apply.yaml
    ```

4. Vérifiez que le Déploiement a été créé :
    ```bash
    kubectl get deployments
    ```

5. Listez les Pods pour vérifier que trois réplicas existent :
    ```bash
    kubectl get pods
    ```

6. Remarquez le nom d'un Pod, puis supprimez-le et vérifiez les Pods :
    ```bash
    kubectl delete pod <pod_name> && kubectl get pods
    ```

## Tâche N°6 : Équilibrage de charge de l'application (Load Balancer)

1. Pour exposer l’application à Internet, créez un service Kubernetes :
    ```bash
    kubectl expose deployment/hello-world
    ```

2. Listez les services pour vérifier que le service a bien été créé :
    ```bash
    kubectl get services
    ```

3. Ouvrez une nouvelle fenêtre de terminal et exécutez un proxy pour accéder à l’application :
    ```bash
    kubectl proxy
    ```

4. Dans la fenêtre de terminal d’origine, pinguez l’application pour obtenir une réponse :
    ```bash
    curl -L localhost:8001/api/v1/namespaces/sn-labs-$USERNAME/services/hello-world/proxy
    ```

5. Exécutez la commande suivante pour envoyer 10 requêtes consécutives au service et observer l'équilibrage de charge :
    ```bash
    for i in `seq 10`; do curl -L localhost:8001/api/v1/namespaces/sn-labs-$USERNAME/services/hello-world/proxy; done
    ```

6. Supprimez le Déploiement et le Service :
    ```bash
    kubectl delete deployment/hello-world service/hello-world
    ```

7. Retournez à la fenêtre du terminal exécutant la commande proxy et terminez-la en utilisant `Ctrl+C`.
