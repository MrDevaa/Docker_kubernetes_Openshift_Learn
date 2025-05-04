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

