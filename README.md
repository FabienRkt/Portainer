# Portainer Docker Compose

Ce projet configure et déploie **Portainer Community Edition (CE)** en utilisant Docker Compose.

## Description

Portainer est une interface de gestion légère pour Docker qui permet de gérer facilement vos conteneurs, images, volumes et réseaux.

## Installation et démarrage

### Prérequis

- Docker
- Docker Compose

### Démarrer le service

```bash
docker-compose up -d
```

### Arrêter le service

```bash
docker-compose down
```

## Accès à Portainer

Une fois le conteneur démarré, accédez à Portainer via :

```
http://localhost:9000
```

## Configuration

### Services

- **Portainer** : Interface de gestion Docker
  - Image : `portainer/portainer-ce:latest`
  - Port : `9000`
  - Redémarrage automatique sauf arrêt manuel

### Volumes

- `portainer_data` : Volume persistant pour les données de Portainer
- `/var/run/docker.sock` : Socket Docker pour gérer les conteneurs

## Données persistantes

Les données de Portainer sont stockées dans le volume `portainer_data`. Elles persisteront même après l'arrêt du conteneur.

## Gestion

### Logs

```bash
docker-compose logs -f portainer
```

### Redémarrer

```bash
docker-compose restart portainer
```

### Supprimer tout

```bash
docker-compose down -v
```

(L'option `-v` supprime également les volumes)

## Notes

- Le conteneur redémarre automatiquement sauf s'il est arrêté manuellement
- Assurez-vous que le port `9000` est disponible

---

**Portainer Community Edition** - [Documentation officielle](https://www.portainer.io/)