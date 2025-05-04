# Objets Ingress vs. Contrôleur Ingress

Dans Kubernetes, l’accès externe aux services du cluster est supervisé par Ingress, qui se compose de deux composants principaux : l’objet API Ingress et le contrôleur Ingress. Comprenons ces éléments et leur fonctionnalité collaborative.

## Objets Ingress

L’Ingress agit comme un superviseur pour l’accès externe, exposant des routes de l’extérieur du cluster vers des services internes, en se concentrant principalement sur le trafic HTTP et HTTPS. Il respecte les règles définies sur la ressource Ingress pour réguler le routage du trafic.

Il ne gère pas des ports ou protocoles arbitraires. Au lieu de cela, il peut fournir des services avec des URL accessibles de l’extérieur, équilibrer le trafic, gérer la terminaison SSL/TLS et permettre l’hébergement virtuel basé sur des noms. Pour les services non-HTTP et non-HTTPS, des types de services spécifiques tels que Service.Type=NodePort ou Service.Type=LoadBalancer sont généralement utilisés.

## Contrôleurs Ingress

Sur le plan opérationnel, le contrôleur Ingress est la ressource de cluster déployée responsable de l’implémentation des règles spécifiées par l’objet API Ingress. Contrairement à certains contrôleurs qui s’exécutent automatiquement dans le cadre du binaire kube-controller-manager, le contrôleur Ingress nécessite une activation explicite pour que la ressource Ingress fonctionne. Son rôle principal est d’exécuter les directives décrites dans l’Ingress, utilisant généralement un équilibreur de charge ou en configurant des frontaux supplémentaires pour gérer le trafic entrant.

## Objets Ingress vs Contrôleurs Ingress

| Caractéristique          | Objets Ingress                                                 | Contrôleurs Ingress                                                     |
|--------------------------|----------------------------------------------------------------|-------------------------------------------------------------------------|
| Définition               | Objet API gérant l’accès externe aux services                  | Ressource de cluster mettant en œuvre les règles spécifiées par Ingress |
| Fonction principale      | Régule le routage de l’accès externe                           | Met en œuvre les règles, remplissant l’Ingress                         |
| Source de configuration  | Règles définies sur la ressource Ingress                      | Lit et traite les informations de l’objet Ingress                      |
| Gestion du trafic        | Gère les routes HTTP et HTTPS                                 | Utilise un équilibreur de charge, configure les frontaux pour le trafic |
| Activation               | Actif lors de la configuration avec la ressource Ingress       | Doit être explicitement en cours d’exécution pour que l’Ingress fonctionne |
| Gestion des protocoles   | Axé sur HTTP et HTTPS                                         | Met en œuvre des règles pour divers protocoles et ports                |
| Démarrage automatique    | Activé avec la configuration                                  | Nécessite une activation explicite dans le cluster                    |
| Analogie                 | Ensemble de règles de circulation pour le cluster             | Exécuteur, similaire à une instance Nginx gérant les règles           |

## Conclusion

Dans Kubernetes, la gestion de l’accès externe inclut l’Ingress, qui se compose d’objets Ingress et de contrôleurs Ingress. L’Ingress gère le routage du trafic HTTP et HTTPS, et les contrôleurs Ingress mettent en œuvre ces règles dans le cluster. Comprendre cette interaction est essentiel pour une gestion efficace de l’accès externe dans Kubernetes.
