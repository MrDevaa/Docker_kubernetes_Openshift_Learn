# 📘 Glossaire : Bases de Kubernetes

Ce glossaire rassemble les termes essentiels pour comprendre les concepts fondamentaux de Kubernetes.

| Terme                           | Définition |
|--------------------------------|------------|
| **Automatisation du bin packing** | Augmente l'utilisation des ressources et permet des économies en mélangeant les charges critiques et les charges en mode "best-effort". |
| **Exécution par lots (Batch)**  | Gère les charges de travail par lots et d'intégration continue ; remplace automatiquement les conteneurs en échec si configuré. |
| **Cloud Controller Manager**    | Composant du plan de contrôle qui contient la logique spécifique au cloud. Permet de connecter un cluster à l'API d’un fournisseur cloud. |
| **Cluster**                     | Ensemble de machines (nœuds) exécutant des applications conteneurisées. Chaque cluster comporte au moins un nœud de travail. |
| **Orchestration de conteneurs** | Processus qui automatise le cycle de vie des applications conteneurisées. |
| **Runtime de conteneurs**       | Logiciel responsable de l'exécution des conteneurs. |
| **Boucle de contrôle**          | Boucle sans fin régulant l'état d’un système (exemple : thermostat). |
| **Plan de contrôle**            | Couche d’orchestration exposant l’API et les interfaces pour définir, déployer et gérer les conteneurs. |
| **Contrôleur**                  | Boucles de contrôle observant l'état du cluster et le corrigeant pour correspondre à l’état souhaité. |
| **Plan de données (Worker)**    | Fournit les ressources (CPU, mémoire, stockage, réseau) pour exécuter les conteneurs. |
| **DaemonSet**                   | Garantit l'exécution d'une copie d’un Pod sur un ensemble de nœuds. |
| **Gestion déclarative**         | Décrit un état souhaité (ex : nombre de réplicas) que Kubernetes s’efforce de maintenir. |
| **Déploiement (Deployment)**    | Objet qui gère les mises à jour des Pods et ReplicaSets. Recommandé pour les applications sans état. |
| **Conçu pour l’extensibilité**  | Permet d'ajouter des fonctionnalités sans modifier le code source. |
| **Docker Swarm**                | Outil d’orchestration de conteneurs conçu spécifiquement pour l’écosystème Docker. |
| **Écosystème**                  | Ensemble de services, outils et supports disponibles autour de Kubernetes. |
| **etcd**                        | Stockage clé-valeur distribué contenant l’état du cluster (source de vérité). |
| **Éviction**                    | Processus de suppression d’un ou plusieurs Pods sur un nœud. |
| **Commandes impératives**       | Créent, mettent à jour ou suppriment directement des objets en production. |
| **Gestion impérative**          | Définit les étapes pour atteindre un état souhaité. |
| **Ingress**                     | Objet API gérant l’accès externe (HTTP/HTTPS) aux services d’un cluster. |
| **Pile double IPv4/IPv6**       | Attribue des adresses IPv4 et IPv6 aux Pods et services. |
| **Job**                         | Tâche ponctuelle ou par lot exécutée jusqu’à sa complétion. |
| **Kubectl**                     | Outil en ligne de commande pour interagir avec l’API de Kubernetes. |
| **Kubelet**                     | Agent sur chaque nœud, exécutant et surveillant les conteneurs définis par PodSpecs. |
| **Kubernetes**                  | Plateforme open-source d’orchestration de conteneurs. Automatisation du déploiement, mise à l’échelle, stockage, découverte, etc. |
| **API Kubernetes**              | Interface RESTful pour interagir avec les objets et l’état du cluster. |
| **API Server**                  | Valide, configure les objets API et sert de point d’entrée pour l’état du cluster. |
| **Controller Manager**          | Exécute les contrôleurs du cluster (réplication, services, comptes, etc.). |
| **Cloud Controller Manager**    | Spécifique au cloud, sépare la logique cloud des composants internes du cluster. |
| **Kube Proxy**                  | Proxy réseau sur chaque nœud, gère les règles réseau pour accéder aux Pods. |
| **kube-scheduler**              | Assigne un nœud aux nouveaux Pods non planifiés. |
| **Sélecteur de labels**         | Filtre les ressources à l’aide d’étiquettes. |
| **Labels (Étiquettes)**         | Attributs associés aux objets pour l’identification. |
| **Répartition de charge**       | Répartit le trafic entre Pods pour de meilleures performances et disponibilité. |
| **Marathon**                    | Framework Mesos pour la gestion et le scaling de conteneurs. |
| **Namespace**                   | Abstraction pour isoler des groupes de ressources dans un même cluster. |
| **Nœud (Node)**                 | Machine (physique ou virtuelle) exécutant les Pods. |
| **Nomad**                       | Outil open-source de Hashicorp pour planifier/manager des workloads sur tout type d’infrastructure. |
| **Objet Kubernetes**            | Entité représentant l’état d’un cluster (Pods, Services, etc.). |
| **Persistance**                 | Assure qu’un objet existe jusqu’à modification ou suppression explicite. |
| **Préemption**                  | Kubernetes peut libérer un nœud en supprimant des Pods de faible priorité. |
| **Auto-réparation**             | Redémarre, remplace ou replanifie des conteneurs en échec. |
| **Service**                     | Abstraction exposant un ensemble de Pods via une interface réseau stable. |
| **Découverte de service**       | Découvre des Pods via leur IP ou un nom DNS unique. |
| **StatefulSet**                 | Gère des Pods avec persistance, nommage et ordonnancement garantis. |
| **Stockage (Storage)**          | Fournit un espace de stockage temporaire ou persistant pour les Pods. |
| **Orchestration du stockage**   | Monte automatiquement le système de stockage sélectionné. |
| **Pod**                         | Plus petite unité déployable de Kubernetes, représentant un ou plusieurs conteneurs liés. |
| **Proxy (réseau)**              | Serveur intermédiaire servant de relais pour les requêtes à distance. |
| **ReplicaSet**                  | Maintient un nombre défini de réplicas d’un Pod en exécution. |
| **Workload (Charge de travail)**| Application s'exécutant sur Kubernetes. |

---

> 🔗 Pour aller plus loin, consulte la documentation officielle : [https://kubernetes.io/fr/docs](https://kubernetes.io/fr/docs)
