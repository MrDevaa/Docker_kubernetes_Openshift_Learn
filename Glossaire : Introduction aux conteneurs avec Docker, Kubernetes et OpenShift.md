# Glossaire : Introduction aux conteneurs avec Docker, Kubernetes et OpenShift

Bienvenue !  
Ce glossaire, classé par ordre alphabétique, regroupe de nombreux termes utilisés dans ce cours. Il inclut également des termes reconnus dans l'industrie, même s’ils ne sont pas abordés directement dans les vidéos. Ces termes sont importants à connaître lorsque vous travaillez dans le secteur, participez à des communautés d’utilisateurs ou suivez d’autres programmes de certification.

---

## 📦 Notions de base sur les conteneurs

| Terme                          | Définition |
|-------------------------------|------------|
| **Agile**                     | Approche itérative de la gestion de projet et du développement logiciel, permettant de livrer de la valeur plus rapidement et avec moins de problèmes. |
| **Architecture client-serveur** | Structure applicative répartie qui sépare les tâches entre les serveurs (fournisseurs de services) et les clients (utilisateurs). |
| **Conteneur**                 | Unité logicielle standard qui regroupe le code, le runtime, les bibliothèques et les paramètres nécessaires à l’exécution d’une application. |
| **Registre de conteneurs**    | Système permettant de stocker et distribuer des images de conteneurs. |
| **Pipelines CI/CD**           | Étapes automatisées visant à améliorer l’efficacité et la qualité de la livraison logicielle continue. |
| **Cloud native**              | Applications conçues spécifiquement pour une exécution dans le cloud et exploitant les modèles de livraison cloud. |
| **Sans démon (Daemon-less)**  | Moteur de conteneurisation fonctionnant sans processus d’arrière-plan dédié à la gestion des objets Docker. |
| **DevOps**                    | Ensemble de pratiques, outils et culture visant à automatiser et intégrer les processus entre le développement logiciel et les opérations informatiques. |
| **Docker**                    | Plateforme open source permettant de créer, déployer et exécuter des applications dans des conteneurs. |
| **Dockerfile**                | Fichier de configuration contenant les instructions pour créer une image Docker. |
| **Client Docker**             | Interface principale permettant d’envoyer des commandes au démon Docker. |
| **Interface CLI Docker**      | Interface en ligne de commande pour interagir avec Docker (construction, exécution, arrêt des conteneurs, etc.). |
| **Démon Docker (dockerd)**    | Moteur central chargé de la création et de la gestion des conteneurs, images, volumes, etc. |
| **Docker Hub**                | Registre cloud pour stocker, partager et déployer des images Docker. |
| **Docker localhost**          | Mode réseau où `localhost` dans un conteneur fait référence à l’hôte physique. |
| **Hôte Docker distant**       | Moteur Docker accessible à distance via API, sur un réseau local ou externe. |
| **Réseaux Docker**            | Permettent d’isoler la communication entre groupes de conteneurs pour plus de sécurité. |
| **Plugins Docker**            | Extensions ajoutant des fonctionnalités à Docker (stockage, sécurité, logs, etc.). |
| **Stockage Docker**           | Méthodes permettant de conserver les données après la suppression d’un conteneur (volumes, montages liés). |
| **IBM Cloud Container Registry** | Registre privé et géré pour le stockage et la distribution d’images de conteneurs. |
| **Image**                     | Fichier statique contenant tout ce qui est nécessaire pour exécuter une application (code, dépendances, etc.). |
| **Immuabilité**               | Une image Docker est en lecture seule ; toute modification nécessite la création d’une nouvelle image. |
| **LXC**                       | Technologie de virtualisation de niveau OS permettant la création d’environnements Linux isolés. |
| **Microservices**             | Approche architecturale cloud-native divisant une application en services indépendants et déployables séparément. |
| **Espace de noms (Namespace)**| Fonction du noyau Linux isolant les ressources pour chaque conteneur (réseau, processus, etc.). |
| **Virtualisation au niveau OS** | Technologie permettant d’exécuter plusieurs espaces utilisateurs isolés à l’aide du même noyau système. |
| **Registre privé**            | Registre d’images restreint aux utilisateurs autorisés, renforçant la sécurité des applications. |
| **API REST**                  | Interface de communication conforme aux principes REST pour interagir avec des services web. |
| **Registre**                  | Service hébergé permettant de stocker et partager des images Docker. |
| **Référentiel (Repository)**  | Ensemble d’images Docker versionnées, hébergé dans un registre. |
| **Virtualisation de serveur** | Division d’un serveur physique en serveurs virtuels isolés, chacun avec son propre système d’exploitation. |
| **Serverless (sans serveur)** | Méthodologie de développement cloud-native sans gestion directe d’infrastructure. |
| **Tag (étiquette)**           | Libellé utilisé pour différencier les versions d’images Docker dans un même référentiel. |

---

# Kubernetes Basics

Ce document présente les principaux termes et concepts de base de Kubernetes, avec des définitions claires pour faciliter la compréhension et la révision.

## Table des termes et définitions

| Terme                        | Définition |
|------------------------------|------------|
| **Automated bin packing**    | Technique qui augmente l’utilisation des ressources et permet des économies en mélangeant des charges critiques et best-effort. |
| **Batch execution**          | Prise en charge des charges batch et d’intégration continue. Remplace automatiquement les conteneurs défaillants si configuré. |
| **Cloud Controller Manager** | Partie du control plane Kubernetes qui gère la logique spécifique au cloud et l’intégration avec les services des fournisseurs cloud. |
| **Cluster**                  | Ensemble de machines (nœuds) qui exécutent et gèrent des applications conteneurisées de façon coordonnée. |
| **Container Orchestration**  | Automatisation du cycle de vie des applications conteneurisées. |
| **Container Runtime**        | Logiciel qui exécute et gère les conteneurs pour garantir leur bon fonctionnement. |
| **Control Loop**             | Boucle continue qui maintient l’état désiré d’un système en surveillant et ajustant selon les besoins. |
| **Control plane**            | Composant central de l’orchestration des conteneurs, fournissant l’API et les interfaces pour gérer le cycle de vie des conteneurs. |
| **Controller**               | Boucles de contrôle qui surveillent l’état du cluster et effectuent ou demandent des modifications si nécessaire. |
| **Data (Worker) Plane**      | Couche fournissant CPU, mémoire, bande passante réseau et stockage nécessaires au fonctionnement des conteneurs. |
| **DaemonSet**                | Objet contrôleur garantissant l’exécution d’un Pod sur un ensemble de nœuds, idéal pour les agents système ou outils de monitoring. |
| **Declarative Management**   | Approche où l’état désiré est défini, Kubernetes s’assurant que l’état courant corresponde à cet état. |
| **Deployment**               | Ressource qui gère la mise à jour et le scaling des Pods et ReplicaSets, facilitant les déploiements et retours arrière automatisés. |
| **Designed for extensibility** | Capacité de Kubernetes à ajouter des fonctionnalités sans modifier le code source. |
| **Docker Swarm**             | Outil d’automatisation du déploiement d’applications conteneurisées, conçu pour Docker. |
| **Ecosystem**                | Ensemble des services, outils et supports compatibles avec Kubernetes. |
| **etcd**                     | Stockage clé-valeur fiable et cohérent pour les systèmes distribués. |
| **Eviction**                 | Processus de terminaison et suppression d’un ou plusieurs Pods d’un nœud. |
| **Imperative commands**      | Commandes qui créent, mettent à jour ou suppriment directement des objets en direct. |
| **Imperative Management**    | Approche définissant les étapes/actions pour atteindre un état désiré. |
| **Ingress**                  | Composant gérant l’accès externe aux services du cluster via un point d’entrée unique. |
| **IPv4/IPv6 dual stack**     | Fonctionnalité attribuant des adresses IPv4 et IPv6 aux Pods et Services pour compatibilité étendue. |
| **Job**                      | Tâche avec début et fin définis, souvent utilisée pour des opérations batch ou finies. |
| **Kubectl**                  | Interface en ligne de commande pour interagir avec le control plane et gérer les ressources du cluster. |
| **Kubelet**                  | Agent principal sur chaque nœud, gérant les conteneurs et la communication avec le control plane. |
| **Kubernetes**               | Plateforme open-source de référence pour l’orchestration de conteneurs. |
| **Kubernetes API**           | Interface RESTful offrant un accès programmatique aux fonctionnalités et à l’état du cluster. |
| **Kubernetes API Server**    | Composant validant et configurant les objets API dans Kubernetes. |
| **Kubernetes Controller Manager** | Composant exécutant les processus de contrôle qui surveillent et régulent le cluster. |
| **Kubernetes Cloud Controller Manager** | Composant embarquant la logique cloud spécifique dans Kubernetes. |
| **Kubernetes Proxy**         | Service proxy réseau gérant les règles de trafic et la communication entre Pods et services. |
| **kube-scheduler**           | Composant responsable de l’affectation des nouveaux Pods aux nœuds appropriés. |
| **Label Selector**           | Mécanisme de filtrage permettant d’identifier des ressources via des labels (paires clé-valeur). |
| **Labels**                   | Métadonnées attachées aux objets Kubernetes pour faciliter leur organisation et gestion. |
| **Load balancing**           | Répartition du trafic réseau entre plusieurs Pods pour optimiser la performance et la disponibilité. |
| **Marathon**                 | Framework Apache Mesos pour le scaling d’infrastructures de conteneurs. |
| **Namespace**                | Fonctionnalité permettant l’isolation des ressources au sein d’un cluster. |
| **Node**                     | Machine de travail exécutant des applications conteneurisées, gérée par le control plane. |
| **Nomad**                    | Outil de gestion et d’ordonnancement de clusters supportant Docker et autres applications. |
| **Object**                   | Entité représentée dans le système Kubernetes. |
| **Persistence**              | Capacité d’un objet à exister jusqu’à modification ou suppression explicite. |
| **Preemption**               | Mécanisme d’éviction de Pods à faible priorité pour permettre le placement rapide de Pods prioritaires. |
| **Pod**                      | Unité fondamentale d’exécution, regroupant un ou plusieurs conteneurs partageant un environnement commun. |
| **Proxy**                    | Serveur intermédiaire pour des services distants. |
| **ReplicaSet**               | Ressource assurant qu’un nombre défini de Pods identiques soient toujours en cours d’exécution. |
| **Self-healing**             | Capacité de Kubernetes à redémarrer, remplacer, reprogrammer ou tuer automatiquement les conteneurs défaillants. |
| **Service**                  | Abstraction réseau exposant un groupe de Pods via une IP stable et des capacités de load-balancing. |
| **Service Discovery**        | Découverte et connexion aux Pods via leurs adresses IP ou un nom DNS unique. |
| **StatefulSet**              | Composant gérant le déploiement et le scaling de Pods avec ordre et unicité, adapté aux applications avec état. |
| **Storage**                  | Mécanismes fournissant du stockage persistant ou temporaire aux Pods (ex: Persistent Volumes, StorageClasses). |
| **Storage Orchestration**    | Mécanisme de montage automatique des systèmes de stockage pour Pods, facilitant la gestion des applications avec état. |
| **Workload**                 | Application exécutée sur Kubernetes. |

---

# Managing Applications with Kubernetes

| Terme                     | Définition |
|---------------------------|------------|
| **Cluster Autoscaler**    | Aussi appelé CA. Une ressource API qui ajuste automatiquement la taille du cluster en augmentant ou diminuant le nombre de nœuds disponibles pour exécuter les pods. |
| **Config Map**            | Objet Kubernetes permettant de stocker des données de configuration sous forme de paires clé-valeur. Il facilite la gestion et l’injection des configurations dans les conteneurs, séparant la configuration du code applicatif. |
| **Horizontal Pod Autoscaler** | Ressource API Kubernetes qui ajuste automatiquement le nombre de réplicas de Pods selon des métriques spécifiées comme l’utilisation CPU ou des métriques personnalisées. |
| **IBM Cloud catalog**     | Collection de services proposés par IBM, allant de la reconnaissance visuelle et du traitement du langage naturel à la création de chatbots. |
| **Linguistic Analysis**   | Processus de détection du ton dans un texte donné. |
| **Persistent Volume**     | Dans l’API Kubernetes, un Persistent Volume (PV) est une abstraction de stockage persistant, offrant des options de stockage flexibles et indépendantes du cycle de vie des Pods, garantissant un stockage durable pour les applications du cluster. |
| **Persistent Volume Claim** | Objet API Kubernetes représentant une demande de stockage persistant, indépendante du cycle de vie des Pods, pour fournir un stockage durable aux applications. |
| **Rolling Updates**       | Stratégie permettant de déployer des modifications d’application de manière automatisée et contrôlée sur les Pods. Fonctionne avec des templates de Pods comme les Deployments. Permet également un rollback en cas de problème. |
| **Secrets**               | Objets stockant des informations sensibles comme mots de passe, tokens OAuth, clés SSH. Ils offrent un moyen sécurisé de gérer ces données sensibles, facilitant le déploiement et la gestion. |
| **Service binding**       | Processus d’établissement de connexions entre applications et services externes ou de support, tels que APIs REST, bases de données, ou bus d’événements. |
| **Tone Analyzer Service** | Service IBM Cloud utilisant l’analyse linguistique pour détecter le ton dans un texte donné. |
| **Vertical Pod Autoscaler (VPA)** | Aussi appelé VPA. Ressource API qui ajuste les ressources CPU et mémoire allouées à un Pod existant, permettant un scaling vertical dans un cluster. |
| **Volume**                | Répertoire contenant des données, accessible par plusieurs conteneurs dans un Pod. |
| **Volume Mount**          | Montage d’un volume déclaré dans un conteneur du même Pod. |
| **Volume Plugin**         | Facilite l’intégration du stockage dans un Pod Kubernetes, permettant aux conteneurs d’accéder et d’utiliser des ressources de stockage persistant. |


---

# OpenShift Basics

| Terme                        | Définition |
|------------------------------|------------|
| **A/B testing**              | Stratégie souvent utilisée pour tester de nouvelles fonctionnalités dans les applications front-end. Elle consiste à comparer deux versions (A et B) pour déterminer laquelle fonctionne le mieux dans un environnement contrôlé. |
| **Build**                    | Processus de transformation des entrées en un objet résultant. |
| **BuildConfig**              | Objet spécifique à OpenShift qui définit les étapes et la stratégie d’exécution d’un build. Sert de plan pour le processus de build, en précisant comment les sources sont utilisées pour générer le résultat attendu. |
| **Canary Deployments**       | Stratégie de déploiement où une nouvelle version d’une application est progressivement déployée à un sous-ensemble d’utilisateurs ou de trafic, permettant des tests en conditions réelles avant un déploiement complet. |
| **Circuit breaking**         | Méthode permettant d’éviter que des erreurs dans un microservice ne se propagent à d’autres microservices. |
| **Configuration Change**     | Déclencheur qui lance un nouveau build lorsqu’une nouvelle ressource BuildConfig est créée. |
| **Control Plane**            | Prend la configuration désirée et sa vision des services pour programmer et mettre à jour dynamiquement les serveurs proxy à mesure que l’environnement évolue. |
| **Custom build strategy**    | Dans OpenShift, stratégie de build permettant aux utilisateurs de définir et d’utiliser leur propre image de builder personnalisée. |
| **Custom builder images**    | Images Docker classiques contenant la logique nécessaire pour transformer les entrées en sortie attendue. |
| **CRDs (Custom Resource Definitions)** | Code personnalisé définissant une ressource à ajouter à l’API server Kubernetes sans avoir à créer un serveur personnalisé complet. |
| **Custom controllers**       | Gèrent les CRDs en conciliant en continu l’état actuel avec l’état désiré défini dans la CRD, assurant la cohérence et l’exécution des actions nécessaires. |
| **Data plane**               | Couche de l’architecture réseau qui gère la communication entre services. Sans service mesh, le réseau ne peut pas identifier le type de trafic, la source, la destination, ni prendre de décisions nécessaires. |
| **Enforceability (Control)** | Istio applique des politiques pour garantir une distribution équitable des ressources entre consommateurs, aidant à gérer et réguler l’utilisation des services. |
| **Envoy proxy**              | Proxy utilisé par Istio pour intercepter et gérer tout le trafic réseau. Fournit des fonctionnalités comme le load balancing, l’observabilité et la sécurité selon sa configuration. |
| **Human operators**          | Personnes qui gèrent les systèmes en déployant des services, identifiant des problèmes et mettant en œuvre des solutions pour assurer le bon fonctionnement. |
| **Image Change**             | Déclencheur pour reconstruire une application conteneurisée lorsqu’une nouvelle version d’une image est disponible (ex : mise à jour de sécurité d’une image Node.js). |
| **ImageStream**              | Abstraction OpenShift pour référencer des images de conteneur. Contient des métadonnées comme des IDs ou des digests d’images, mais ne stocke pas les données d’image elles-mêmes. |
| **ImageStream Tag**          | Identifiant dans un ImageStream pointant vers une image spécifique dans un registre. Représente une référence nommée à une version ou variante particulière d’une image. |
| **Istio**                    | Service mesh populaire et indépendant de la plateforme fonctionnant avec Kubernetes. Contrôle le trafic et les appels API entre services, effectue des tests et simplifie la gestion réseau. |
| **Man-in-the-middle attacks**| Attaque où l’attaquant intercepte et relaie secrètement des messages entre deux parties qui croient communiquer directement. |
| **Observability**            | Capacité à surveiller et comprendre les flux de trafic dans un service mesh, tracer les appels et dépendances, et visualiser des métriques comme la latence et les erreurs. |
| **OpenShift**                | Plateforme Kubernetes hybride d’entreprise permettant aux développeurs de créer, déployer et gérer efficacement des applications conteneurisées. |
| **OpenShift CI/CD process**  | Processus d’intégration et de déploiement continu automatisant la fusion du code, la construction, les tests et le déploiement de nouvelles versions dans différents environnements. |
| **Operators**                | Extensions logicielles de Kubernetes automatisant des tâches complexes et agissant comme contrôleurs personnalisés pour étendre l’API Kubernetes. |
| **Operator Framework**       | Ensemble d’outils et de fonctionnalités pour faciliter le développement, les tests, la livraison et la mise à jour des Operators dans Kubernetes. |
| **OperatorHub**              | Console web OpenShift permettant aux administrateurs de découvrir et d’installer des Operators (certifiés Red Hat, communautaires ou personnalisés). |
| **Operator Lifecycle Manager (OLM)** | Composant gérant le cycle de vie des Operators : installation, mises à jour, gestion des accès (RBAC) dans Kubernetes ou OpenShift. |
| **Operator maturity model**  | Cadre définissant les niveaux de maturité des Operators, de l’installation de base à l’automatisation complète (Auto Pilot). |
| **Operator Pattern**         | Modèle de conception associant un contrôleur à une ou plusieurs ressources personnalisées. |
| **Operator Registry**        | Système stockant les CRDs, Cluster Service Versions (CSV) et métadonnées sur les Operators et canaux. Fournit les données du catalogue Operator à l’OLM. |
| **Operator SDK**             | Boîte à outils aidant à créer, tester et packager des Operators sans nécessiter une connaissance approfondie de l’API Kubernetes. |
| **postCommit**               | Section d’une configuration de build définissant un hook optionnel exécuté après le build. |
| **Retries**                  | Mécanisme permettant à un microservice de retenter automatiquement une requête échouée vers un autre service. |
| **runPolicy**                | Champ dans un objet BuildConfig qui dicte comment les builds sont exécutés (en série par défaut, ou en parallèle). |
| **Service Broker**           | Fournit un processus court qui ne peut pas effectuer des opérations continues comme les mises à jour, la reprise après incident ou le scaling. |
| **Service Mesh**             | Couche dédiée à la sécurité et la fiabilité des communications service-à-service. Gère le trafic, chiffre les communications et offre de l’observabilité pour le dépannage et l’optimisation. |
| **Software operators**       | Tentent de capturer la connaissance des opérateurs humains et d’automatiser ces processus. |
| **Source-to-Image (S2i)**    | Outil pour construire des images de conteneur reproductibles en injectant le code source applicatif dans une image de base. |
| **Source strategy**          | Indique comment les builds sont exécutés : gestion directe du code source (Source), utilisation de conteneurs (Docker) ou configurations personnalisées, chaque approche étant adaptée à des besoins spécifiques. |
| **Source type**              | Type d’entrée principale pour un build (ex : dépôt Git, Dockerfile inline, payload binaire). |
| **Webhook**                  | Déclencheur envoyant une requête à un endpoint de l’API OpenShift pour automatiser les builds lors de nouveaux développements. |

