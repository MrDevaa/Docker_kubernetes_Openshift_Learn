# Glossaire : Notions de base d'OpenShift

| Terme                          | Définition |
|-------------------------------|------------|
| **Tests A/B**                 | Stratégie utilisée pour tester deux versions d'une application (A et B) afin de déterminer celle qui performe le mieux dans un environnement contrôlé. |
| **Build**                     | Le processus de transformation des entrées en un objet résultant. |
| **BuildConfig**               | Objet OpenShift définissant le processus qu'un build doit suivre. C’est le plan, tandis que le build est l'instance. |
| **Déploiements Canary**       | Déploiement progressif d’une nouvelle version à un petit nombre d’utilisateurs avant un déploiement global. |
| **Interruption de circuit**   | Méthode pour éviter la propagation d'erreurs entre microservices. |
| **Changement de configuration** | Déclenche l’exécution d’un nouveau build lorsqu’une nouvelle ressource BuildConfig est créée. |
| **Plan de contrôle**          | Programme et met à jour dynamiquement les serveurs proxy en fonction de la configuration souhaitée. |
| **Stratégie de build personnalisée** | Nécessite de créer une image de builder sur mesure. |
| **Images de builder personnalisées** | Images Docker contenant la logique de transformation d’entrées en résultats. |
| **CRDs** (Custom Resource Definitions) | Permettent d’ajouter des ressources personnalisées à l’API Kubernetes. |
| **Contrôleurs personnalisés** | Réconcilient l’état actuel des CRDs avec leur état souhaité. |
| **Plan de données**           | Gère la communication entre services (trafic, source, destination). |
| **Applicabilité (Contrôle)** | Istio applique des politiques de contrôle sur l'ensemble d'une flotte. |
| **Proxy Envoy**               | Proxy réseau utilisé dans un maillage de services pour intercepter et gérer le trafic. |
| **Opérateurs humains**        | Comprennent les systèmes, déploient les services, détectent et corrigent les problèmes. |
| **Changement d'image**        | Déclencheur pour reconstruire une application lorsqu’une nouvelle image est disponible. |
| **ImageStream**               | Abstraction pour référencer des images de conteneurs dans OpenShift. |
| **Tag d'ImageStream**         | Pointe vers une image spécifique dans un ImageStream. |
| **Istio**                     | Plateforme de maillage de services utilisée pour le routage, la sécurité, l’observabilité et la gestion des appels API entre services. |
| **Attaques de l'homme du milieu (MiTM)** | L’attaquant intercepte des messages entre deux parties qui croient communiquer directement. |
| **Observabilité**             | Permet d’observer les flux, tracer les appels et consulter les métriques comme la latence, les erreurs, etc. |
| **OpenShift**                 | Plateforme Kubernetes hybride et d'entreprise. |
| **Processus CI/CD d’OpenShift** | Intègre, teste, approuve et déploie automatiquement du code vers différents environnements. |
| **Opérateurs**                | Automatisent les tâches de cluster en étendant l’API Kubernetes. |
| **Cadre d’Opérateur**         | Outils et méthodes pour créer, tester et maintenir des opérateurs. |
| **OperatorHub**               | Interface pour trouver et installer des opérateurs sur un cluster. |
| **Gestionnaire de cycle de vie des opérateurs (OLM)** | Gère l’installation, la mise à jour et les accès des opérateurs. |
| **Modèle de maturité des opérateurs** | Définit les phases de maturité de l’automatisation (de l’installation à l’auto-pilotage). |
| **Modèle d’Opérateur**        | Connecte un contrôleur à des ressources personnalisées. |
| **Registre des opérateurs**   | Stocke les métadonnées des opérateurs pour les paquets et canaux. |
| **SDK d’Opérateur**           | Fournit des outils (Helm, Go, Ansible) pour construire des opérateurs sans connaître l’API Kubernetes en profondeur. |
| **postCommit**                | Section définissant un hook de build optionnel à exécuter après un commit. |
| **Réessais**                  | Réexécution automatique des requêtes échouées dans les microservices. |
| **runPolicy**                 | Détermine si les builds doivent s’exécuter en série (Serial) ou en parallèle. |
| **Service Broker**            | Processus court pour provisionner un service sans gestion du cycle de vie complet. |
| **Maillage de services**      | Gère la sécurité, le routage et l’observabilité de la communication entre services. |
| **Opérateurs logiciels**      | Automatisent les tâches réalisées par les opérateurs humains. |
| **Source-to-Image (S2i)**     | Outil de construction d’images de conteneur injectant le code source dans une image de base. |
| **Stratégie de source**       | Définit le type de build utilisé (Source, Docker, Personnalisée). |
| **Type de source**            | Source principale : dépôt Git, Dockerfile ou binaire. |
| **Webhook**                   | Déclencheur déclenché par un événement (ex. push GitHub) pour lancer automatiquement un build dans OpenShift. |
