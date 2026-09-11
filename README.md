# imaalem-iot-app

Manifests Kubernetes de l'application déployée par Argo CD dans la partie 3 du
projet **Inception-of-Things** (école 42).

Ce dépôt est la **source de vérité** : Argo CD le surveille en permanence et
applique automatiquement dans le cluster tout changement qui y est poussé.

| Fichier | Rôle |
|---|---|
| `deployment.yaml` | l'application `wil42/playground`, port 8888 |
| `service.yaml` | Service `NodePort` (30080), porte d'entrée depuis l'hôte |

## Changer de version

Modifier le tag de l'image dans `deployment.yaml` :

```yaml
image: wil42/playground:v1    # -> v2
```

puis `git commit` et `git push`. Argo CD détecte le changement et redéploie
l'application automatiquement, sans aucune commande `kubectl`.

## Infrastructure

Le cluster k3d, les namespaces et Argo CD sont montés par les scripts du dépôt
principal : <https://github.com/nessrinemaalem/inception_of_things> (dossier `p3/`).
