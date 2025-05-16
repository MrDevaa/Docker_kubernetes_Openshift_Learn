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

