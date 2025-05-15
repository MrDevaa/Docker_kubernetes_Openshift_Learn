# 📘 Fiche de Référence : Gestion des Applications avec Kubernetes

Voici une fiche pratique des commandes essentielles pour gérer les applications Kubernetes :

| Commande                            | Description                                                         |
|-------------------------------------|----------------------------------------------------------------------|
| `kubectl autoscale deployment`      | Ajuste automatiquement un déploiement Kubernetes (HPA).             |
| `kubectl create configmap`          | Crée une ressource ConfigMap.                                       |
| `kubectl get deployments -o wide`   | Liste les déploiements avec des détails supplémentaires (ex: IPs, nœuds). |
| `kubectl get hpa`                   | Liste les Horizontal Pod Autoscalers (HPA).                         |
| `kubectl scale deployment`          | Élargit manuellement un déploiement en ajustant le nombre de pods. |
| `kubectl set image deployment`      | Met à jour l’image d’un conteneur dans un déploiement.              |
| `kubectl rollout`                   | Gère le déploiement d'une ressource (vérification, historique, etc.). |
| `kubectl rollout restart`           | Redémarre une ressource (recrée les pods avec les mêmes définitions). |
| `kubectl rollout undo`              | Rétablit la ressource à une version précédente du déploiement.      |

---

🛠️ **Astuce :** Combine ces commandes avec `--help` pour explorer toutes les options disponibles.  
Exemple : `kubectl rollout --help`

