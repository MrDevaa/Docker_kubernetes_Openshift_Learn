# 🧠 Feuille de triche : Comprendre l'architecture de Kubernetes

Cette feuille de triche regroupe les principales commandes `kubectl` utilisées pour manipuler des ressources dans un cluster Kubernetes, accompagnées de leur description.

## 📋 Commandes de base

| Commande                               | Description                                                                 |
|----------------------------------------|-----------------------------------------------------------------------------|
| `for … do … done`                      | Exécute une commande en boucle un nombre défini de fois.                   |
| `kubectl apply`                        | Applique une configuration à une ressource de façon déclarative.           |
| `kubectl config get-clusters`          | Affiche les clusters définis dans le fichier kubeconfig.                   |
| `kubectl config get-contexts`          | Affiche les contextes d’accès configurés et indique le contexte actif.     |
| `kubectl create`                       | Crée une ou plusieurs ressources à partir d’un fichier de configuration.   |
| `kubectl delete`                       | Supprime une ou plusieurs ressources.                                      |
| `kubectl describe`                     | Affiche des détails complets sur une ressource spécifique.                 |
| `kubectl expose`                       | Expose une ressource (comme un Pod ou un Déploiement) via un Service.      |
| `kubectl get`                          | Liste les ressources d’un type donné.                                      |
| `kubectl get pods`                     | Liste tous les Pods du namespace actuel.                                   |
| `kubectl get pods -o wide`             | Liste tous les Pods avec plus de détails (IP, node, etc.).                |
| `kubectl get deployments`              | Liste les déploiements créés.                                              |
| `kubectl get services`                 | Liste les services existants dans le cluster.                              |
| `kubectl proxy`                        | Lance un proxy entre localhost et le serveur API Kubernetes.               |
| `kubectl run`                          | Crée et exécute un Pod à partir d’une image.                               |
| `kubectl version`                      | Affiche les versions du client et du serveur Kubernetes.                   |

---

> ✅ Astuce : Pour approfondir, n’hésite pas à consulter la documentation officielle : [https://kubernetes.io/fr/docs](https://kubernetes.io/fr/docs)
