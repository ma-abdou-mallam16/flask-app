# Application Flask avec Kubernetes

Ce projet est une application Flask déployée sur Kubernetes. Il comprend les configurations nécessaires pour le déploiement, les services et les pods.

## Structure du Projet

```
.
├── application/          # Code source de l'application Flask
├── deployment.yaml      # Configuration du déploiement Kubernetes
├── service.yaml         # Configuration du service Kubernetes
└── pods.yaml           # Configuration des pods Kubernetes
```

## Prérequis

- Kubernetes
- kubectl
- Docker

## Déploiement

1. Construire l'image Docker :
```bash
docker build -t votre-image:tag ./application
```

2. Appliquer les configurations Kubernetes :
```bash
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
kubectl apply -f pods.yaml
```

## Configuration

Les fichiers YAML contiennent les configurations suivantes :

- `deployment.yaml` : Configuration du déploiement de l'application
- `service.yaml` : Configuration du service pour exposer l'application
- `pods.yaml` : Configuration des pods Kubernetes

## Accès à l'Application

Une fois déployée, l'application sera accessible via le service Kubernetes configuré dans `service.yaml`.

## Maintenance

Pour mettre à jour l'application :
1. Reconstruire l'image Docker
2. Mettre à jour la référence de l'image dans `deployment.yaml`
3. Appliquer la nouvelle configuration :
```bash
kubectl apply -f deployment.yaml
```

## Support

Pour toute question ou problème, veuillez ouvrir une issue dans le dépôt. 