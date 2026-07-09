# Prérequis - TP ArgoCD DevHub Campus

> Ce fichier liste ce qu'il faut installer ou avoir avant de lancer le TP.

## Outils obligatoires

| Outil | Version minimale | Version vérifiée |
|---|---:|---:|
| Docker | Docker Desktop / Docker Engine fonctionnel | 29.5.2 |
| kubectl | 1.30 | 1.34.1 |
| Kustomize | inclus avec kubectl | 5.7.1 |
| kind | 0.22 | 0.22.0 |
| Helm | 3.14 | 3.20.2 |
| ArgoCD CLI | 2.11 | 3.4.4 |
| Git | 2.40 | 2.43.0 |
| yq | 4.40 | 4.53.3 |

## Outil optionnel

| Outil | Rôle | Version vérifiée |
|---|---|---:|
| stern | Lire les logs de plusieurs pods en même temps | 1.33.1 |

## Prérequis système

- Docker doit être démarré et accessible par l'utilisateur courant.
- Les ports locaux `80` et `443` doivent être disponibles pour l'ingress du cluster kind.
- Un accès internet est nécessaire pour télécharger les images, charts Helm et dépendances.
- Le fichier `hosts` doit pouvoir être modifié.

## Entrées hosts prévues

Ces entrées seront utilisées plus tard dans le TP :

```text
127.0.0.1  argocd.devhub.local
127.0.0.1  annuaire.devhub.local
127.0.0.1  planning.devhub.local
127.0.0.1  notif.devhub.local
```

## Notes Windows

- Les commandes du Makefile doivent être exécutées dans WSL2.
- Docker Desktop doit utiliser le backend WSL2.
- La distribution Ubuntu doit être activée dans Docker Desktop > Resources > WSL Integration.
- Le fichier hosts à modifier est celui de Windows : `C:\Windows\System32\drivers\etc\hosts`.

## Vérification

Depuis `devhub-campus/` :

```bash
make tools-check
yq --version
git --version
stern --version
```
