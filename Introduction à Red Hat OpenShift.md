# Introduction à Red Hat OpenShift

Bienvenue dans ce dépôt d'introduction à **Red Hat OpenShift**, une plateforme Kubernetes entreprise conçue pour le cloud hybride, développée et supportée par Red Hat.

## 🚀 Qu’est-ce qu’OpenShift ?

OpenShift est une **plateforme d'orchestration de conteneurs** basée sur Kubernetes, qui fournit un environnement complet pour le développement, le déploiement et la gestion des applications cloud-native.

OpenShift s'appuie sur :
- **Linux**
- **Conteneurs (OCI)**
- **Automatisation (CI/CD, provisioning)**
- **Sécurité d'entreprise**

## ⚙️ Fonctionnalités clés

- Interface CLI (`oc`) plus riche que `kubectl`
- Console Web conviviale pour les débutants
- CI/CD intégré avec Jenkins
- Sécurité renforcée (RBAC, scan de vulnérabilités, gestion des politiques)
- Monitoring, logs, détection des menaces, profilage de risque
- Support du stockage persistant (état/sans état)
- Scalabilité horizontale (multi-noeuds, multi-clusters)
- Services pour développeurs (IDE, FROM, builds, image streams, routes)

## 🏗️ Architecture

- S’exécute sur un **cluster Kubernetes**
- Données stockées dans **etcd**
- Basé sur **Red Hat Enterprise Linux CoreOS**
- Architecture en microservices avec APIs REST
- CLI : `oc` (OpenShift CLI), compatible avec `kubectl`
- CI/CD via Jenkins, FROM et UO (User Operations)

## 📊 OpenShift vs Kubernetes

| Fonctionnalité               | Kubernetes                       | OpenShift                                 |
|-----------------------------|----------------------------------|-------------------------------------------|
| Nature                      | Projet open source               | Produit entreprise (Red Hat)              |
| Interface web               | Moins intuitive                  | Conviviale et simple                      |
| CI/CD                       | Nécessite intégration            | Jenkins intégré                           |
| Flexibilité d'installation  | Très flexible                    | Moins de flexibilité après installation   |
| CLI                         | `kubectl`                        | `oc` (plus de commandes, auth intégrée)   |
| Sécurité                    | Moins stricte                    | Très stricte par défaut                   |
| Mise à jour                 | Manuelle                         | OTA (Over The Air) supportée              |
| Réseau                      | Plugins                          | Solutions prêtes à l'emploi               |

## 🧰 Prérequis pour utilisation

- Cluster Kubernetes ou OpenShift existant
- OC CLI installé : [Télécharger ici](https://mirror.openshift.com/pub/openshift-v4/clients/oc/)
- Compte développeur sur Red Hat (si utilisation cloud)

## 🔗 Ressources utiles

- [Documentation officielle OpenShift](https://docs.openshift.com/)
- [Playground en ligne](https://learn.openshift.com/)
- [OpenShift sur Azure (ARO)](https://azure.microsoft.com/en-us/services/openshift/)
- [Kubernetes vs OpenShift (blog)](https://www.redhat.com/en/topics/containers/kubernetes-vs-openshift)

---

# 📦 OpenShift Build Process

## 1. 🔧 Qu'est-ce qu'une Build ?
Une **Build** transforme des **sources d'entrée** (ex : code source) en une **image de conteneur exécutable**.

---

## 2. 📁 BuildConfig (Fichier YAML)
Le cœur du processus. Il définit :
- 🔄 **Stratégie de Build** (S2I, Docker, Custom)
- 📥 **Sources d’entrée**
- 🚀 **Triggers (Déclencheurs)**
- 🧱 **Sortie (Image finale)**

---

## 3. 📥 Sources d’entrée (par ordre de priorité)
| Priorité | Source d’entrée                  |
|----------|----------------------------------|
| 1️⃣       | Dockerfile **inline** (dans YAML)|
| 2️⃣       | Contenu d’image existante        |
| 3️⃣       | Git Repository                   |
| 4️⃣       | Fichiers binaires / locaux       |
| 5️⃣       | Secrets                          |
| 6️⃣       | Artefacts externes               |

---

## 4. 🛠️ Stratégies de Build
| Stratégie  | Description |
|------------|-------------|
| **S2I** (Source-to-Image) | Utilise une image builder, pas besoin de Dockerfile |
| **Docker** | Nécessite un Dockerfile, comme une build classique |
| **Custom** | Build personnalisée (exécute un script Docker personnalisé). **⚠️ Réservée aux admins** |

---

## 5. 🧃 ImageStream (Flux d’image)
- Abstraction pour gérer les **images de conteneurs**
- Peut contenir plusieurs **tags** (ex : `latest`, `dev`, `prod`)
- Permet de **référencer** une image sans coder l'URL complète
- ✅ Met à jour automatiquement les déploiements si l’image change

---

## 6. ⏱️ Déclencheurs de Build (Triggers)
| Type                        | Déclencheur                                                       |
|----------------------------|-------------------------------------------------------------------|
| **Webhook**                | Requête envoyée lors d'un `push`, `merge` sur GitHub / GitLab    |
| **Image Change Trigger**   | Nouvelle version d'une image (ex : image Node.js mise à jour)     |
| **Config Change Trigger**  | Nouvelle ressource `BuildConfig`                                  |

---

## 7. 📤 Sortie et Post-Commit
- 🔚 L’image finale est poussée dans le **registre interne** d’OpenShift
- 🪝 Optionnel : un **hook post-commit** peut être exécuté (tests, scripts...)

---

## 8. 🔁 CI/CD avec OpenShift
- Intégration avec des **pipelines CI/CD**
- Automatisation du **build → test → déploiement** dans différents environnements

---

## ✅ Résumé
- Une **Build** = Stratégie + Sources + Triggers + Image de sortie
- Utilisez **ImageStream** pour abstraction des images
- Activez les **triggers** pour automatiser les mises à jour

---

# 📦 Introduction aux Opérateurs Kubernetes

Ce document présente les **opérateurs Kubernetes**, un puissant mécanisme permettant d'automatiser la gestion d'applications complexes dans un cluster.

---

## 🔁 1. Qu’est-ce qu’un opérateur ?

Un **opérateur Kubernetes** est un **contrôleur personnalisé** qui étend l’API de Kubernetes pour automatiser le **déploiement, la gestion, la mise à jour et la surveillance** d’applications complexes.

Il agit comme un **expert humain automatisé**, capable de :

- Déployer une application
- Superviser son état
- Réagir aux incidents (crash, scaling, etc.)
- Mettre à jour, sauvegarder ou restaurer automatiquement

---

## ⚙️ 2. Comment fonctionne un opérateur ?

Un opérateur :

- Fonctionne dans un **pod Kubernetes**
- Interagit avec le **Kubernetes API Server**
- Utilise deux composants principaux :
  - Une **CRD (Custom Resource Definition)** : définit une nouvelle ressource dans Kubernetes
  - Un **contrôleur personnalisé** : surveille l’état et applique les changements nécessaires

> 🛠️ Exemple : créer une ressource `App` via une CRD peut automatiquement créer un `Deployment`, un `Service` et un `Secret`.

---

## 🧠 3. Opérateurs humains vs logiciels

| Opérateur Humain                    | Opérateur Logiciel                        |
|------------------------------------|-------------------------------------------|
| Admin système                      | Code exécutable                           |
| Connaît les procédures manuellement | Automatise ces procédures                 |
| Doit intervenir régulièrement      | S’exécute en continu sans intervention    |

---

## 🌐 4. Différence avec les brokers de services

| Fonction                            | Broker de service       | Opérateur Kubernetes     |
|-------------------------------------|--------------------------|---------------------------|
| Installation                        | Oui                      | Oui                       |
| Tâches du "jour 2" (update, scale…) | ❌ Non                   | ✅ Oui                    |
| Surveillance continue               | ❌ Non                   | ✅ Oui                    |

---

## 📦 5. Qu’est-ce qu’une CRD (Custom Resource Definition) ?

- Permet d’étendre l’API Kubernetes avec des **ressources personnalisées**
- Se manipule comme les ressources natives : `kubectl get <crd-name>`
- Utilisée pour décrire le **"quoi faire"**

---

## 🔄 6. Qu’est-ce qu’un contrôleur personnalisé ?

- C’est la **logique de traitement** d’un opérateur
- Il observe les CRDs créées
- Il agit automatiquement pour **concilier l’état actuel et l’état désiré**

---

## 🔧 7. Le modèle opérateur

Un opérateur est la combinaison de :

- **CRD** : la ressource déclarative
- **Contrôleur** : la logique métier associée

Il permet d’**étendre Kubernetes** avec ses propres API et de gérer des applications de manière déclarative.

---

## 🧰 8. Operator Framework

Outils et services autour des opérateurs :

- **Operator SDK** : création d’opérateurs avec Go, Ansible ou Helm
- **OLM (Operator Lifecycle Manager)** : gestion du cycle de vie des opérateurs
- **Operator Hub** : catalogue public d’opérateurs prêts à installer

---

## 📈 9. Modèle de maturité des opérateurs

| Niveau        | Description                                      |
|---------------|--------------------------------------------------|
| **Basique**   | Déploiement manuel                               |
| **Intermédiaire** | Mise à jour automatique, surveillance partielle |
| **Avancé (Autopilot)** | Ajustements dynamiques en fonction de l’état |

---

## ✅ 10. En résumé

- Les **opérateurs** automatisent les tâches complexes dans Kubernetes.
- Ils sont composés de **CRDs + contrôleurs**.
- Ils peuvent être développés avec des outils comme **Operator SDK**.
- Ils s’installent via **Operator Hub** et sont gérés par **OLM**.
- Leur **maturité** dépend du niveau d’automatisation fourni.

---

      ┌────────────────────────────┐
      │     Operator Hub (UI)     │
      │ (trouver/installer opé.)  │
      └────────────┬──────────────┘
                   │
                   ▼
      ┌────────────────────────────┐
      │  Operator Lifecycle Mgmt   │
      │  (OLM - gère install/màj)  │
      └────────────┬──────────────┘
                   │
                   ▼
        ┌────────────────────┐
        │      OPÉRATEUR     │  ◄─────────────┐
        │ (Pod avec logique) │                │
        └────────┬───────────┘                │
                 │                            │
         Surveille & gère                     │
                 ▼                            │
    ┌────────────────────────────┐            │
    │   Ressource Personnalisée  │ (CR)       │
    │   via CRD (CustomResource) │            │
    └────────┬───────────┬───────┘            │
             │           │                    │
             ▼           ▼                    │
      Déploiement   ConfigMap, etc.           │
             ▲                                │
             │                                │
        ┌────────────┐                        │
        │ Contrôleur │  ◄────────────┐        │
        │ Personnalisé│              │        │
        └────────────┘              ▼        ▼
                             État souhaité vs État réel
                           (Réconciliation automatique)

---

# 📘 Introduction à Istio et le Service Mesh

## 🔍 Qu’est-ce qu’un **Service Mesh** ?

Un **Service Mesh** (maillage de services) est une **couche d'infrastructure** qui gère **la communication entre les microservices** dans une application. Il rend cette communication :

- **Fiable**
- **Sécurisée**
- **Observable**

Sans Service Mesh, chaque microservice doit gérer lui-même les mécanismes de sécurité, de résilience, etc.  
Avec un service mesh, ces responsabilités sont centralisées.

---

## 🧠 Introduction à **Istio**

**Istio** est une implémentation populaire de **service mesh**, principalement utilisée avec **Kubernetes**.

Il permet de :

- **Contrôler le trafic** (ex : déploiement progressif de nouvelles versions)
- **Sécuriser les échanges** entre services (authentification, autorisation, chiffrement)
- **Observer et surveiller** les communications (logs, métriques, traces)
- **Appliquer des politiques** de résilience et de gouvernance

---

## 🧱 Les 4 concepts clés d’**Istio**

1. **Connexion (Traffic Management)**  
   - Déploiements canaris (envoyer 5 % du trafic vers une nouvelle version)  
   - Tests A/B  
   - Répartition de charge

2. **Sécurité (Security)**  
   - Authentification mutuelle (mTLS)  
   - Autorisation des accès  
   - Chiffrement du trafic réseau

3. **Application (Policy Enforcement)**  
   - Contrôle d’accès  
   - Limites de requêtes  
   - Quotas, etc.

4. **Observabilité (Telemetry)**  
   - Latence (temps de réponse)  
   - Trafic (nombre de requêtes)  
   - Erreurs  
   - Saturation (ressources)

---

## 🧩 Architecture Istio : Plan de contrôle vs plan de données

- **Plan de données** :  
  Gère le trafic réseau réel. Il utilise un proxy **Envoy** déployé à côté de chaque microservice (sidecar).

- **Plan de contrôle** :  
  Configure et met à jour dynamiquement les proxies en fonction de l’état du cluster et des règles définies.

---

## 💡 Pourquoi utiliser Istio avec des **microservices** ?

### ✅ Avantages :

- Déploiement indépendant de chaque composant
- Meilleure scalabilité
- Sécurité renforcée
- Routage intelligent (canari, A/B)
- Visibilité complète du trafic

### ❌ Défis :

- Complexité technique
- Surcharge réseau avec les sidecars
- Courbe d'apprentissage importante

---

## 📈 Surveillance : Les **4 métriques fondamentales** d’Istio

1. **Latence** – Temps de réponse d’un service
2. **Trafic** – Volume de requêtes reçues
3. **Erreurs** – Nombre ou taux de réponses incorrectes
4. **Saturation** – Charge du système (CPU, mémoire, etc.)

---

## 🔐 Sécurité avec Istio

Istio chiffre les communications entre services (via **mTLS**) pour se protéger des attaques comme l’**attaque de l’homme du milieu**.  
Il peut aussi empêcher un service d’accéder à un autre s’il n’en a pas l’autorisation.

---

## 🧪 Exemple de cas d’usage

Supposons que tu déploies une **nouvelle version** de ton microservice de commandes :

- Istio peut envoyer **5 %** du trafic à la nouvelle version.
- Ensuite, augmenter progressivement à **50 %**, puis **100 %**.
- Permet de tester sans risquer une panne globale.
- Tu peux également tester différentes versions via un test **A/B**.

---

# 🧭 Architecture simplifiée d'Istio avec Service Mesh

```plaintext
                    +---------------------+
                    |    Istio Control    |
                    |       Plane         |
                    |   (Pilot, Mixer,    |
                    |    Citadel, etc.)   |
                    +----------+----------+
                               |
     -------------------------------------------------------
    |                       Service Mesh                    |
    |                                                       |
    |  +-----------+     +-----------+     +-----------+    |
    |  |  UI Pod   |     | Order Pod |     | Inventory |    |
    |  | +-------+ |     | +-------+ |     |   Pod     |    |
    |  | | Envoy |<------>| Envoy |<------>| +-------+ |    |
    |  | +-------+ |     | +-------+ |     | | Envoy | |    |
    |  +-----------+     +-----------+     | +-------+ |    |
    |                                      +-----------+    |
    |                                             |         |
    |                                       +-----------+   |
    |                                       |  Database  |   |
    |                                       +-----------+   |
    |                                                       |
    -------------------------------------------------------

Fonctionnalités d'Istio :
- 🔁 **Gestion du trafic** : routage fin (canary, A/B testing, retries, failover)
- 🔐 **Sécurité** : mTLS, authentification, autorisation
- 📊 **Observabilité** : latence, trafic, erreurs, saturation (L.T.E.S)
- 📏 **Application de politiques** : quotas, limites de débit, contrôle d’accès

Chaque microservice communique à travers son **proxy Envoy**,
qui intercepte et gère le trafic via les règles configurées par le **Plan de Contrôle Istio**.


