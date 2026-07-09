# Plan de suivi - TP ArgoCD DevHub Campus

> Fichier de pilotage du TP.  
> Cocher les cases `- [x]` au fur et à mesure de l'avancement.

**Dernière mise à jour** : 2026-07-09

---

## Progression globale

| Étape | Sujet | Statut |
|---|---|---|
| 0 | Outillage et prérequis | ✅ |
| 1 | Comprendre GitOps | ⬜ |
| 2 | Vocabulaire ArgoCD | ⬜ |
| 3 | Containeriser un service | ⬜ |
| 4 | Écrire un chart Helm | ⬜ |
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

- [ ] Lire la partie GitOps du polycopié.
- [ ] Expliquer la différence push vs pull.
- [ ] Expliquer pourquoi Git devient la source de vérité.
- [ ] Identifier ce qu'ArgoCD ne fait pas.
- [ ] Préparer une section "GitOps en 1 page" pour le rapport.

## Étape 2 - Vocabulaire ArgoCD

- [ ] Définir `Application`.
- [ ] Définir `AppProject`.
- [ ] Définir `Sync`.
- [ ] Définir `Health`.
- [ ] Définir `OutOfSync`.
- [ ] Définir `Self Heal`.
- [ ] Définir `Prune`.
- [ ] Définir `ApplicationSet`.
- [ ] Ajouter un exemple concret du projet pour chaque terme.

## Étape 3 - Containeriser un service

- [ ] Choisir le service de départ.
- [ ] Vérifier le Dockerfile.
- [ ] Construire l'image localement.
- [ ] Tagger l'image avec le SHA Git court.
- [ ] Tester `/healthz` avec `docker run`.
- [ ] Préparer la publication GHCR.
- [ ] Documenter la validation.

## Étape 4 - Écrire un chart Helm

- [ ] Lire le chart existant du service.
- [ ] Compléter `Chart.yaml`.
- [ ] Compléter `values.yaml`.
- [ ] Compléter `values-dev.yaml`.
- [ ] Compléter les templates Kubernetes.
- [ ] Lancer `helm lint`.
- [ ] Lancer `helm template`.
- [ ] Valider avec `kubectl apply --dry-run=client`.

## Étape 5 - Installer ArgoCD et déclarer une première Application

- [ ] Créer le cluster kind avec `make cluster-up`.
- [ ] Installer ingress-nginx et ArgoCD avec `make argocd-install`.
- [ ] Ajouter les entrées hosts.
- [ ] Récupérer le mot de passe admin ArgoCD.
- [ ] Ouvrir l'UI ArgoCD.
- [ ] Déclarer une première Application.
- [ ] Vérifier la synchronisation dans ArgoCD.

## Étape 6 - Pattern App of Apps

- [ ] Comprendre le rôle de la root Application.
- [ ] Compléter `platform/bootstrap/root-app.yaml`.
- [ ] Compléter les Applications dans `platform/apps/dev/`.
- [ ] Vérifier que la root Application pilote les applications enfants.
- [ ] Tester un changement Git et la détection par ArgoCD.

## Étape 7 - ApplicationSet et previews par branche

- [ ] Lire le fonctionnement d'ApplicationSet.
- [ ] Comprendre la génération par branche.
- [ ] Compléter les manifests preview.
- [ ] Créer ou utiliser une branche de test.
- [ ] Vérifier la création d'un environnement de preview.
- [ ] Vérifier la suppression propre après suppression de branche.

## Étape 8 - Drift, rollback, hooks, sync waves

- [ ] Provoquer un drift.
- [ ] Observer `OutOfSync`.
- [ ] Tester ou documenter `selfHeal`.
- [ ] Tester un rollback via Git.
- [ ] Comprendre les hooks.
- [ ] Comprendre les sync waves.
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
