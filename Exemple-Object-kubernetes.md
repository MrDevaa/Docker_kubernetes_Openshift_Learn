## Une expérience pratique avec Kubernetes, en mettant l’accent sur la création de services, l’utilisation de diverses commandes kubectl, et le déploiement de StatefulSets et DaemonSets.

# Objectifs
- Créer un Service Kubernetes
- Utiliser diverses commandes kubectl
- Déployer un StatefulSet pour gérer des applications avec état
- Mettre en œuvre un DaemonSet pour exécuter un seul pod sur tous les nœuds
  
---

- Dans le terminal verifier la version de kebectl ;
```bash
kubectl version
```
## Taches n°1 : Créer un Service Kubernetes en utilisant l'image nginx

- Un serveur web open-source populaire, nginx est connu pour sa haute performance, sa stabilité et sa faible consommation de ressources. Il peut également fonctionner comme un proxy inverse, un équilibreur de charge et un cache HTTP.

- Créer un Service Kubernetes en utilisant une image nginx implique de mettre en place une couche réseau qui permet à d’autres composants au sein du cluster Kubernetes ou à des utilisateurs externes d’accéder à l’application nginx s’exécutant dans des pods. Pour exécuter nginx en tant que service dans Kubernetes, vous pouvez suivre ces étapes :

1.Créer un Déploiement nommé my-deployment1 en utilisant l’image nginx
```bash
    kubectl create deployment < my-deployment1 > --image=nginx
```
2. Exposer le déploiement en tant que service
```bash
   kubectl expose deployment my-deployment1 --port=80 --type=NodePort --name=my-service1
```
3. Liste tous les services dans l’espace de noms par défaut. Les services fournissent une adresse IP stable et un nom DNS pour accéder à un ensemble de pods.
```bash
    kubectl get services
```
## Taches n°2 :  Gérer les Pods et Services Kubernetes

1. Obtenez la liste des pods
```bash
   kubectl get pods
```
2. Afficher les étiquettes
```bash
    kubectl get pod <pod-name> --show-labels
```
3. Étiquetez le pod
```bash
     kubectl label pods <pod-name> environment=deployment
```
4. Afficher les étiquettes
 ```bash
    kubectl get pod <pod-name> --show-labels
 ```
6. Exécutez un pod de test en utilisant l’image nginx
```bash
     kubectl run my-test-pod --image=nginx --restart=Never
```
8. Afficher les journaux
 ```bash
   kubectl logs <pod-name>
 ```

## Taches n°3: Déploiement d'un StatefulSet

- Un StatefulSet gère le déploiement et la mise à l’échelle d’un ensemble de pods, et maintient une identité persistante pour chacun de leurs Pods, garantissant que chaque Pod a une identité et un stockage persistants.

1.Créez et ouvrez un fichier nommé statefulset.yaml en mode édition.
```bash
    touch statefulset.yaml
 ```
2. Ouvrez statefulset.yaml, ajoutez le code suivant, puis enregistrez le fichier :
```bash
   apiVersion: apps/v1
   kind: StatefulSet
   metadata:
     name: my-statefulset
   spec:
     serviceName: "nginx"
     replicas: 3
     selector:
       matchLabels:
         app: nginx
     template:
       metadata:
         labels:
           app: nginx
       spec:
         containers:
         - name: nginx
           image: nginx
           ports:
           - containerPort: 80
             name: web
     volumeClaimTemplates:
     - metadata:
         name: www
       spec:
         accessModes: [ "ReadWriteOnce" ]
         resources:
           requests:
             storage: 1Gi
```
3. Appliquez la configuration du StatefulSet.
 ```bash
      kubectl apply -f statefulset.yaml
 ```
4. Vérifiez que le StatefulSet est créé.
  ```bash
      kubectl get statefulsets
  ```
## Taches n°4: Mise en œuvre d'un DaemonSet

- Un DaemonSet garantit qu’une copie d’un Pod spécifique s’exécute sur tous (ou certains) nœuds du cluster. Il est particulièrement utile pour déployer des applications au niveau système qui fournissent des services essentiels à travers les nœuds d’un cluster, tels que la collecte de journaux, la surveillance ou les services réseau.

1. Créez un fichier nommé daemonset.yaml et ouvrez-le en mode édition :
```bash
     touch daemonset.yaml
```
2. Créez et ouvrez un fichier nommé daemonset.yaml en mode édition.
 ```bash
     apiVersion: apps/v1
  kind: DaemonSet
  metadata:
    name: my-daemonset
  spec:
    selector:
      matchLabels:
        name: my-daemonset
    template:
      metadata:
        labels:
          name: my-daemonset
      spec:
        containers:
        - name: my-daemonset
          image: nginx
  ```
3. Appliquez le DaemonSet
   ```bash
    kubectl apply -f daemonset.yaml
    ```
4. Vérifiez que le DaemonSet a été créé
  ```bash
      kubectl get daemonsets
  ```
