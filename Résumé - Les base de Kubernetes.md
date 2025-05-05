# Les Bases de Kubernetes

## Statut
L'orchestration de conteneurs avec Kubernetes permet d'automatiser le cycle de vie des conteneurs, améliorant ainsi les déploiements, la disponibilité, la sécurité et réduisant les erreurs. Kubernetes est un système open-source hautement portable et évolutif qui simplifie la gestion des applications conteneurisées à grande échelle.

## Architecture de Kubernetes
Kubernetes se compose de deux éléments principaux : le **plan de contrôle** et les **plans de travail**.

### Plan de contrôle
Le plan de contrôle gère l'état global du cluster et prend des décisions importantes concernant les déploiements des conteneurs :
- **Serveur API** : Point d'entrée principal pour interagir avec Kubernetes.
- **Contrôleurs** : Assurent que l'état du cluster correspond à l'état désiré.
- **Planificateur (Scheduler)** : Gère l'attribution des Pods sur les nœuds.
- **etcd** : Base de données clé-valeur distribuée, utilisée pour stocker l'état du cluster.

### Plan de travail
Le plan de travail gère les ressources où les conteneurs sont exécutés :
- **Nœuds** : Machines (physiques ou virtuelles) qui exécutent les Pods.
- **Kubelet** : Agent responsable du fonctionnement des Pods sur chaque nœud.
- **Runtime de conteneur** : Logiciel qui exécute les conteneurs.
- **Kube-proxy** : Maintient les règles réseau pour permettre la communication entre les Pods.

## Objets Kubernetes
### Espaces de noms (Namespaces)
Les espaces de noms permettent d’isoler des groupes de ressources au sein d'un même cluster, facilitant ainsi la gestion et la sécurité.

### Pods
Les Pods sont les unités de base dans Kubernetes et représentent une ou plusieurs applications en cours d'exécution dans un cluster. Un Pod peut contenir un ou plusieurs conteneurs.

### ReplicaSets
Le **ReplicaSet** assure que le nombre souhaité de répliques d’un Pod soit en cours d'exécution à tout moment. Cela permet de garantir la disponibilité et l'équilibrage de charge.

### Déploiements (Deployments)
Un **Déploiement** est un objet Kubernetes qui fournit des mises à jour des Pods et des ReplicaSets. Il permet également d'effectuer des rollbacks en cas de problème.

### Services
Les **Services** sont des objets REST qui permettent d'exposer des Pods pour l'accès interne ou externe au cluster. Voici les principaux types de services :
- **ClusterIP** : Expose le service uniquement à l'intérieur du cluster.
- **NodePort** : Permet d'exposer le service à l'extérieur du cluster via un port sur chaque nœud.
- **External Name** : Permet d'associer un service à un nom DNS externe.

### Ingress
L’**Ingress** gère l'accès des utilisateurs externes à plusieurs services dans un cluster en définissant des règles de routage basées sur des URL.

### DaemonSet
Le **DaemonSet** garantit qu'une copie d'un Pod est exécutée sur chaque nœud du cluster, idéal pour des tâches comme la collecte de logs ou la surveillance.

### StatefulSet
Le **StatefulSet** est utilisé pour gérer les applications avec état. Il permet de maintenir l'identité stable des Pods et offre un stockage persistant pour chaque Pod.

### Job
Les **Jobs** sont utilisés pour exécuter des tâches qui doivent être terminées. Les Pods sont créés et suivis jusqu'à ce qu'ils aient terminé leur tâche. En cas d'échec, les Jobs peuvent être réessayés.

## Capacités de Kubernetes
Kubernetes offre une variété de fonctionnalités qui permettent d'optimiser la gestion des applications :
- **Déploiements et Rollbacks automatisés** : Pour gérer les versions des applications.
- **Orchestration du stockage** : Permet de gérer le stockage persistant pour les applications.
- **Mise à l'échelle horizontale** : Ajoute ou supprime des Pods en fonction de la charge.
- **Emballage automatisé** : Simplifie le processus d'intégration et de déploiement.
- **Gestion des secrets** : Permet de stocker et de gérer les informations sensibles.
- **Découverte de services et équilibrage de charge** : Assure une communication fluide et optimisée entre les services.
- **Auto-réparation** : Kubernetes répare automatiquement les Pods défaillants.

## Conclusion
Kubernetes est un outil essentiel pour l'orchestration de conteneurs, permettant de déployer, gérer et scaler des applications de manière efficace. Il fournit des capacités puissantes comme l'auto-réparation, la mise à l'échelle automatique et la gestion des configurations, facilitant ainsi la gestion des clusters à grande échelle.
