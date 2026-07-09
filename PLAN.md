# Plan de suivi - TP ArgoCD DevHub Campus

> Fichier de pilotage du TP.
> Cocher les cases `- [x]` au fur et à mesure de l'avancement.

**Dernière mise à jour** : 2026-07-09

---

## Progression globale

| Étape | Sujet | Statut |
|---|---|---|
| 0 | Outillage et prérequis | ✅ |
| 1 | Comprendre GitOps | ✅ |
| 2 | Vocabulaire ArgoCD | ✅ |
| 3 | Containeriser un service | 🟡 local validé, push GHCR à faire |
| 4 | Écrire un chart Helm | ✅ |
| 5 | Installer ArgoCD et déclarer une première Application | ⬜ |
| 6 | Pattern App of Apps | ⬜ |
| 7 | ApplicationSet et previews par branche | ⬜ |
| 8 | Drift, rollback, hooks, sync waves | ⬜ |
| 9 | Sécuriser et observer ArgoCD | ⬜ |
| 10 | Comparer les outils GitOps (bonus) | ⬜ |
| 11 | Synthèse obligatoire : ArgoCD et la production | ⬜ |
| Rapport | Rapport final | ⬜ |

---

## Étape 0 - Outillage et prérequis

- [x] Vérifier que Docker est installé et lancé.
- [x] Vérifier `kubectl >= 1.30`.
- [x] Vérifier `kind >= 0.22`.
- [x] Vérifier `helm >= 3.14`.
- [x] Vérifier `argocd CLI >= 2.11`.
- [x] Vérifier `git >= 2.40`.
- [x] Vérifier `yq >= 4.40`.
- [x] Vérifier `stern` si disponible.
- [x] Noter les versions exactes dans l'historique.
- [x] Préparer la future section Outillage du rapport.

## Étape 1 - Comprendre GitOps

- [x] Lire la partie GitOps du polycopié.
- [x] Expliquer la différence push vs pull.
- [x] Expliquer pourquoi Git devient la source de vérité.
- [x] Identifier ce qu'ArgoCD ne fait pas.
- [x] Préparer une section "GitOps en 1 page" pour le rapport.

## Étape 2 - Vocabulaire ArgoCD

- [x] Définir `Application`.
- [x] Définir `AppProject`.
- [x] Définir `Sync`.
- [x] Définir `Health`.
- [x] Définir `OutOfSync`.
- [x] Définir `Self Heal`.
- [x] Définir `Prune`.
- [x] Définir `ApplicationSet`.
- [x] Ajouter un exemple concret du projet pour chaque terme.

## Étape 3 - Containeriser un service

- [x] Choisir le service de départ.
- [x] Vérifier le Dockerfile.
- [x] Construire l'image localement.
- [x] Tagger l'image avec le SHA Git court.
- [x] Tester `/healthz` avec `docker run`.
- [x] Publier l'image sur GHCR avec un token `write:packages`.
- [x] Documenter la validation.

## Étape 4 - Écrire un chart Helm

- [x] Lire le chart existant du service.
- [x] Compléter `Chart.yaml`.
- [x] Compléter `values.yaml`.
- [x] Compléter `values-dev.yaml`.
- [x] Compléter les templates Kubernetes.
- [x] Lancer `helm lint`.
- [x] Lancer `helm template`.
- [x] Valider avec `kubectl create --dry-run=client` sans cluster, puis refaire `apply --dry-run=client` après `cluster-up`.

## Étape 5 - Installer ArgoCD et déclarer une première Application

- [x] Créer le cluster kind avec `make cluster-up`.
- [x] Installer ingress-nginx et ArgoCD avec `make argocd-install`.
- [x] Ajouter les entrées hosts.
- [x] Récupérer le mot de passe admin ArgoCD.
- [x] Ouvrir l'UI ArgoCD.
- [x] Déclarer une première Application.
- [x] Vérifier la synchronisation dans ArgoCD.

## Étape 6 - Pattern App of Apps

- [x] Comprendre le rôle de la root Application.
- [x] Compléter `platform/bootstrap/root-app.yaml`.
- [x] Compléter les Applications dans `platform/apps/dev/`.
- [x] Vérifier que la root Application pilote les applications enfants.
- [x] Tester un changement Git et la détection par ArgoCD.

## Étape 7 - ApplicationSet et previews par branche

- [x] Lire le fonctionnement d'ApplicationSet.
- [x] Comprendre la génération par branche.
- [x] Compléter les manifests preview.
- [x] Créer ou utiliser une branche de test.
- [x] Vérifier la création d'un environnement de preview.
- [x] Vérifier la suppression propre après suppression de branche.

## Étape 8 - Drift, rollback, hooks, sync waves

- [x] Provoquer un drift.
- [x] Observer le drift et la correction automatique.
- [x] Tester ou documenter `selfHeal`.
- [x] Tester un rollback via Git.
- [x] Comprendre les hooks.
- [x] Comprendre les sync waves.
- [ ] Documenter les scénarios dans le rapport.

## Étape 9 - Sécuriser et observer ArgoCD

- [ ] Compléter ou vérifier l'AppProject.
- [ ] Comprendre les droits autorisés/interdits.
- [ ] Vérifier les namespaces autorisés.
- [ ] Lire les logs ArgoCD utiles.
- [ ] Vérifier l'état des composants ArgoCD.
- [ ] Documenter les limites de sécurité restantes.

## Étape 10 - Comparer les outils GitOps (bonus)

- [ ] Comparer ArgoCD et Flux.
- [ ] Comparer selon l'UI, la maturité, la sécurité, la CI, les previews.
- [ ] Donner une note argumentée par critère.

## Étape 11 - Synthèse obligatoire

- [ ] Reprendre le tableau TP1 vs TP2.
- [ ] Commenter chaque opération.
- [ ] Expliquer ce qu'ArgoCD améliore.
- [ ] Expliquer ce qu'ArgoCD rend plus contraignant.
- [ ] Lister les briques nécessaires en production.
- [ ] Donner une position personnelle argumentée.

## Rapport final

- [ ] Générer `RAPPORT.md`.
- [ ] Ajouter les captures utiles.
- [ ] Relire le style pour éviter un rendu trop artificiel.
- [ ] Exporter en PDF.
- [ ] Vérifier que le rapport couvre les livrables demandés.
