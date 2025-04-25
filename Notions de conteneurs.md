# Glossaire : Notions de Conteneur

Ce glossaire regroupe les principaux termes et concepts liés à la conteneurisation et à l'écosystème Docker.

| Terme                                   | Définition |
|------------------------------------------|------------|
| **Agile**                               | Approche itérative de la gestion de projet et du développement logiciel qui aide les équipes à livrer de la valeur à leurs clients plus rapidement et avec moins de problèmes. |
| **Architecture client-serveur**          | Structure d'application distribuée qui partitionne les tâches ou les charges de travail entre les fournisseurs d'une ressource ou d'un service (serveurs) et les demandeurs de services (clients). |
| **Conteneur**                           | Unité standard de logiciel alimentée par un moteur de conteneurisation, encapsulant code, environnement d'exécution, outils système, bibliothèques et paramètres nécessaires pour construire, expédier et exécuter des applications efficacement. |
| **Container Registry**                   | Stocke et distribue des images de conteneurs nommées. Les fonctions de base sont de stocker des images et de les récupérer. |
| **CI/CD pipelines**                      | Série d'étapes pour livrer une nouvelle version d'un logiciel, visant à améliorer la livraison via l'automatisation tout au long du cycle de vie du développement logiciel. |
| **Cloud native**                         | Application conçue pour une architecture de cloud computing, hébergée et exécutée dans le cloud pour tirer parti des caractéristiques du cloud. |
| **Sans démon**                           | Environnement d'exécution de conteneur qui ne lance aucun programme spécifique (démon) pour créer des objets tels que images, conteneurs, réseaux et volumes. |
| **DevOps**                               | Ensemble de pratiques, d'outils et de philosophie culturelle qui automatisent et intègrent les processus entre le développement logiciel et les équipes informatiques. |
| **Docker**                               | Plateforme de conteneurs ouverte pour développer, expédier et exécuter des applications dans des conteneurs. |
| **Dockerfile**                           | Document texte contenant toutes les commandes nécessaires pour construire une image Docker. Docker lit ces instructions pour construire automatiquement les images. |
| **Client Docker**                        | Principal moyen d'interagir avec Docker. Les commandes (ex : `docker run`) sont envoyées au démon Docker (dockerd) via l'API Docker. Peut communiquer avec plusieurs démons. |
| **Interface de ligne de commande Docker (CLI)** | Permet d'émettre des commandes de construction, d'exécution et d'arrêt d'applications à un démon Docker. |
| **Démon Docker (dockerd)**               | Crée et gère des objets Docker tels que images, conteneurs, réseaux et volumes. |
| **Docker Hub**                           | Service de création, gestion et livraison d'applications de conteneurs pour les équipes. |
| **Docker localhost**                     | Réseau hôte permettant aux conteneurs de partager la pile réseau de l'hôte physique. Un localhost dans un conteneur se résout donc sur l'hôte physique. |
| **Hôte Docker distant**                  | Machine exécutant un moteur Docker accessible à distance via des ports exposés pour interroger l'API Docker. |
| **Réseaux Docker**                       | Permettent d'isoler les communications des conteneurs. |
| **Plugins Docker**                       | Extensions (ex : stockage) permettant de connecter des plateformes externes. |
| **Stockage Docker**                      | Utilise des volumes et des montages de liaison pour persister les données après l'arrêt d'un conteneur. |
| **LXC (LinuX Containers)**               | Technologie de virtualisation au niveau du système d'exploitation permettant la création de plusieurs environnements Linux isolés sur un même hôte. |
| **IBM Cloud Container Registry**         | Registre privé entièrement géré pour stocker et distribuer des images de conteneurs. |
| **Image**                                | Fichier immuable contenant code source, bibliothèques et dépendances nécessaires au fonctionnement d'une application. Sert de modèle pour un conteneur. |
| **Immutabilité**                         | Les images sont en lecture seule ; toute modification crée une nouvelle image. |
| **Microservices**                        | Approche architecturale cloud-native où une application est composée de nombreux services indépendants, faiblement couplés et déployables séparément. |
| **Namespace**                            | Fonctionnalité du noyau Linux isolant et virtualisant les ressources système. Essentiel à l'isolation des conteneurs Docker. |
| **Virtualisation du système d'exploitation** | Permet au noyau de gérer plusieurs instances isolées d'espace utilisateur, appelées conteneurs, sur un même OS. |
| **Registre privé**                       | Restreint l'accès aux images aux seuls utilisateurs autorisés. |
| **REST API**                             | Interface de programmation respectant les contraintes REST pour interagir avec des services web RESTful. |
| **Registre**                             | Service hébergé contenant des dépôts d'images répondant à l'API du registre. |
| **Dépôt**                                | Ensemble d'images Docker pouvant être partagé via un serveur de registre. Les images sont distinguées par des tags. |
| **Virtualisation des serveurs**          | Division d'un serveur physique en plusieurs serveurs virtuels isolés, chacun pouvant exécuter ses propres systèmes d'exploitation. |
| **Sans serveur**                         | Modèle cloud-native permettant de créer et d'exécuter des applications sans gérer de serveurs. |
| **Tag**                                  | Étiquette appliquée à une image Docker dans un dépôt, permettant de distinguer les différentes images. |

---
