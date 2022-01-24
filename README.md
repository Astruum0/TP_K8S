# TP Kubernetes

_Arthur VELLA, Matteo CHRISTOPHE_

## Namespaces

**2 Namespaces sont mis en place :**

### Devops303

2 Pods `devops33`, 1 pod `redis`

Quota de 3 cpu max et 2G de memoire max, sert à limiter les ressources

### Hello

3 Pods `hello-world`

Quota de 3 cpu max et 800M de memoire max, sert à limiter son impact sur les ressources du Cluster

## Les Pods

2 pods `devops303` sont mis en place pour un service redondant.
Le pod `Redis` est lié aux pods Devops303 grâce aux variables d'environnement (cf. `configmap.yml`)
3 pods `Hello-World` sont setup

Les pods sont joiniables grace aux hosts `devops303.tp_k8s` et `hello.tp_k8s` (cf. `devops303/ingress.yml` et `hello/ingress.yml`)

## RBAC

3 rôles:

- admin-cluster : tous les droits
- dev : pas de droit de delete
- client : read-only

On a aussi mis en place un label criticity:danger sur les ressources du cluster Devops303 pour que les ressources du namespace ne soient pas modifiées par toutes les personnes.

## Monitoring

marche pô :(
