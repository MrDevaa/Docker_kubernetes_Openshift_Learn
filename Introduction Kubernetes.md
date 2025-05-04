## ☁️ Introduction à Kubernetes

**Kubernetes (aussi appelé K8s)** est une plateforme open source qui :
- Automatise le déploiement, la mise à l’échelle et la gestion des applications conteneurisées
- Supporte des workloads variés (avec état, sans état, batch…)
- S’intègre à tout type d’infrastructure (cloud, sur site, hybride)

🔧 Kubernetes ne remplace pas Docker, il **orchestre des conteneurs** (généralement Docker ou containerd).

## 🧭 Orchestration des Conteneurs

Avec l’émergence des conteneurs (via Docker, Podman, etc.), les applications sont devenues plus **portables** et **légères**. Cependant, en production, il devient difficile de :
- Gérer **des dizaines voire des centaines de conteneurs**
- Assurer leur **redémarrage automatique**
- Mettre à l’échelle dynamiquement
- Surveiller et exposer les services

➡️ C’est là qu’intervient **l’orchestration de conteneurs**.  
Elle permet de gérer le **cycle de vie complet** des conteneurs : déploiement, mise à l’échelle, mise à jour, tolérance aux pannes, etc.

Le leader des outils d’orchestration est **Kubernetes**, développé par Google et aujourd’hui open source.

## 🏗️ Architecture de Kubernetes

L’architecture de Kubernetes repose sur **deux grandes parties** :

### 🧠 1. **Control Plane**
Le **cerveau** de Kubernetes. Il décide **quoi faire** et supervise l’ensemble du cluster.
- `kube-apiserver` : point d’entrée principal, reçoit toutes les requêtes (via `kubectl`)
- `etcd` : base de données clé/valeur qui stocke l’état du cluster
- `controller-manager` : s’assure que l’état réel correspond à l’état désiré (self-healing)
- `scheduler` : décide sur quel nœud exécuter un nouveau Pod

-----------------------
|    Control Plane     |
|----------------------|
| kube-apiserver       |
| etcd                 |
| kube-scheduler       |
| kube-controller-mgr  |
-----------------------

Composant	                                                                               -  Rôle
- kube-apiserver = 	Point d’entrée principal du cluster. Toutes les commandes (kubectl, etc.) passent par lui. Il communique avec les autres composants via une API REST.
- etcd	 = Base de données clé-valeur distribuée qui stocke l’état complet du cluster (configurations, états des pods, secrets…).
- kube-scheduler = Décide où les nouveaux pods doivent être déployés (sur quel nœud), en fonction des ressources disponibles et des contraintes.
- kube-controller-manager	= Supervise et applique l’état désiré. Exemple : si un pod plante, il le recrée. Il gère plusieurs "contrôleurs" (replica controller, job controller, etc.).
- cloud-controller-manager (optionnel)	= Permet l’intégration avec les fournisseurs cloud (GCP, AWS…). Il gère le provisioning de ressources cloud (load balancers, volumes…).

---
### ⚙️ 2. **Nœuds de Travail (Worker Nodes)**
Ce sont les **serveurs qui exécutent réellement les applications**.
- `kubelet` : agent sur chaque nœud, communique avec le control plane
- `kube-proxy` : gère la connectivité réseau entre Pods
- **Runtime de conteneur** (ex : Docker, containerd) : exécute les conteneurs

-----------------------
|    Worker Nodes      |
|----------------------|
| kubelet              |
| kube-proxy           |
| Container Runtime    |
| (pods & containers)  |
------------------------

Composant	                                            - Rôle
- kubelet	= C’est l’agent principal qui fonctionne sur chaque nœud. Il s’assure que les pods sont en cours d'exécution et en bon état. Il communique avec le kube-apiserver pour recevoir les instructions et appliquer l'état souhaité.
- kube-proxy	= Il assure le réseau sur le nœud. Il gère les services Kubernetes et permet la communication réseau entre les pods et en dehors du cluster. Il s'occupe aussi de la répartition du trafic sur les différents pods d'un même service.
- Container Runtime	= C’est le moteur qui exécute les conteneurs dans les pods. Le runtime le plus connu est Docker, mais Kubernetes peut aussi utiliser d’autres runtimes comme containerd ou CRI-O.

---
## 📦 Les Objets Kubernetes

Les objets Kubernetes permettent de **définir l’état souhaité** du cluster (via des fichiers YAML ou des commandes).

| Objet             | Rôle                                                                 |
|------------------|----------------------------------------------------------------------|
| **Pod**          | Plus petite unité. Contient un ou plusieurs conteneurs.              |
| **Deployment**   | Gère les Pods (mise à l’échelle, mises à jour, auto-recovery).       |
| **ReplicaSet**   | Assure un nombre stable de Pods. Souvent géré par un Deployment.     |
| **Service**      | Fournit une IP stable et du load balancing pour des Pods.            |
| **Ingress**      | Routage HTTP/HTTPS vers différents services.                         |
| **ConfigMap**    | Stocke des configurations non sensibles.                             |
| **Secret**       | Stocke des données sensibles (ex : clés API).                        |
| **PVC / PV**     | Gère le stockage persistant.                                         |
| **Job / CronJob**| Exécution ponctuelle ou planifiée de tâches.                         |

---
