# 📘 Glossaire : Gestion des Applications avec Kubernetes

Un glossaire des principaux termes liés à la gestion des applications dans Kubernetes :

| **Terme**                             | **Définition** |
|--------------------------------------|----------------|
| **Cluster Autoscaler (CA)**          | Ressource de l’API qui ajuste automatiquement la taille du cluster en augmentant ou en diminuant le nombre de nœuds disponibles pour l’exécution des pods. |
| **ConfigMap**                        | Objet de l’API utilisé pour stocker des données non sensibles sous forme de paires clé-valeur. Les pods peuvent consommer des ConfigMaps comme variables d’environnement, arguments en ligne de commande ou fichiers de configuration montés dans un volume. |
| **Horizontal Pod Autoscaler (HPA)**  | Ressource de l’API qui ajuste automatiquement le nombre de réplicas de pods en fonction de l’utilisation du CPU ou d’autres métriques personnalisées. |
| **Analyse linguistique**             | Détecte le ton émotionnel dans un texte donné. |
| **Catalogue IBM Cloud**              | Propose divers services allant de la reconnaissance visuelle à l’analyse du langage naturel et à la création de chatbots. |
| **Volume Persistant (PV)**           | Objet de l’API représentant un espace de stockage dans le cluster. Il s’agit d’une ressource générale et modulable qui persiste au-delà du cycle de vie des pods. |
| **Revendication de Volume Persistant (PVC)** | Permet de demander des ressources de stockage définies dans un Volume Persistant afin qu’elles puissent être montées dans un conteneur. |
| **Mises à jour progressives (Rolling Updates)** | Permettent de déployer des modifications d’application de manière contrôlée et automatisée sur les pods. Elles fonctionnent avec des modèles de pods comme les déploiements et permettent un retour en arrière en cas de problème. |
| **Secrets**                          | Stockent des informations sensibles comme des mots de passe, des tokens OAuth ou des clés SSH. |
| **Liaison de service (Service Binding)** | Processus permettant de connecter une application à des services externes (API REST, bases de données, etc.) en fournissant automatiquement les informations de configuration nécessaires. |
| **Service Tone Analyzer**            | Service d’IBM Cloud utilisant l’analyse linguistique pour détecter les émotions dans un texte, souvent utilisé pour illustrer la liaison de service. |
| **Vertical Pod Autoscaler (VPA)**    | Ressource de l’API qui ajuste automatiquement les ressources (CPU, mémoire) d’un pod existant, permettant une mise à l’échelle verticale. |
| **Volume**                           | Répertoire contenant des données, accessible par plusieurs conteneurs dans un même pod. |
| **Montage de Volume (Volume Mount)** | Action de monter un volume déclaré dans un conteneur appartenant au même pod. |
| **Plugin de Volume**                 | Permet l’intégration du stockage dans un pod via des plugins spécifiques au type de volume. |

---

🛠️ **Astuce :** Comprendre ces termes est essentiel pour concevoir des applications évolutives, fiables et sécurisées dans Kubernetes.
