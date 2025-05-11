# Stratégies de Déploiement Kubernetes


Une **stratégie de déploiement Kubernetes** définit le cycle de vie d'une application pour atteindre et maintenir un état configuré de manière automatisée. Des stratégies efficaces minimisent les risques lors des mises à jour.

Les stratégies de déploiement sont utilisées pour :

- Déployer, mettre à jour ou revenir en arrière sur des ReplicaSets, Pods, Services et Applications.
- Mettre en pause / reprendre les déploiements.
- Mettre à l'échelle les déploiements manuellement ou automatiquement.

---

## Types de Stratégies de Déploiement

Voici six types de stratégies :

1. **Recreate** (Recréer)
2. **Rolling Update** (Roulant)
3. **Blue/Green** (Bleu/Vert)
4. **Canary**
5. **A/B Testing**
6. **Shadow** (Ombre)

Vous pouvez utiliser une ou plusieurs stratégies combinées selon le contexte.

---

## 1. Stratégie de Recréation

### Description
Tous les Pods de la version actuelle sont arrêtés avant de lancer les nouveaux Pods avec la nouvelle version.

### Avantages
- Mise en œuvre simple.
- Remplacement complet de l'application.

### Inconvénients
- Temps d'arrêt entre les versions.

---

## 2. Stratégie Roulante (Rolling Update)

### Description
Chaque Pod est mis à jour un à un de v1 vers v2 sans interruption majeure du service.

### Avantages
- Pas ou peu de temps d’arrêt.
- Convient aux applications avec état.

### Inconvénients
- Rollout/Rollback plus lent.
- Pas de contrôle sur la distribution du trafic.

---

## 3. Stratégie Bleu/Vert

### Description
Deux environnements (bleu : actuel, vert : nouveau) sont maintenus. Le trafic est basculé après tests.

### Avantages
- Pas de temps d’arrêt.
- Rollback instantané.

### Inconvénients
- Coûteux (double des ressources).
- Tests rigoureux requis.

---

## 4. Stratégie Canary

### Description
Un petit groupe d’utilisateurs teste la nouvelle version avant déploiement global.

### Avantages
- Contrôle progressif.
- Retour rapide possible.

### Inconvénients
- Déploiement plus lent.
- Ressources supplémentaires.

---

## 5. Stratégie de Test A/B

### Description
Deux versions différentes sont testées sur des groupes d’utilisateurs spécifiques.

### Avantages
- Ciblage fin des utilisateurs.
- Contrôle total du trafic.

### Inconvénients
- Besoin d’un équilibreur de charge intelligent.
- Traçage complexe.

---

## 6. Stratégie de l’Ombre

### Description
Une version “fantôme” traite le trafic réel sans répondre aux utilisateurs.

### Avantages
- Test en conditions réelles.
- Aucun impact utilisateur.

### Inconvénients
- Coût élevé.
- Complexité de configuration.

---

## Résumé Comparatif

| Stratégie     | Temps d'arrêt | Trafic réel | Utilisateurs ciblés | Coût | Retour en arrière | Impact utilisateur | Complexité |
|---------------|----------------|--------------|----------------------|------|--------------------|---------------------|-------------|
| Recreate      | ✗              | ✗            | ✗                    | Faible | Rapide            | Faible              | Faible      |
| Rolling       | ✓              | ✗            | ✗                    | Moyen  | Progressif        | Faible              | Moyenne     |
| Blue/Green    | ✓              | ✗            | ✗                    | Élevé | Instantané        | Faible              | Moyenne     |
| Canary        | ✓              | ✓            | ✗                    | Moyen  | Rapide            | Faible              | Moyenne     |
| A/B Testing   | ✓              | ✓            | ✓                    | Moyen  | Moyen             | Potentiel           | Élevée      |
| Shadow        | ✓              | ✓            | ✗                    | Élevé | Instantané        | Aucun               | Élevée      |

---

## Bonnes Pratiques

- Tenez compte du **type d’application** et de votre **public cible**.
- **Canary** et **Shadow** utilisent des requêtes en temps réel.
- **A/B Testing** est adapté aux tests d’interface ou de nouvelles fonctionnalités.
- **Blue/Green** est adapté aux déploiements critiques sans temps d’arrêt.
- **Rolling Update** est un choix sûr avec retour en arrière facile.
- **Recreate** est suffisant si les interruptions sont acceptables.

---
