# 🚀 DevOps CI/CD Project - 2026

![Build Status](https://github.com/Madow78/tp-docker/actions/workflows/main.yml/badge.svg)

## 📖 Description
Ce projet est une implémentation complète d'un pipeline CI/CD (DevOps) pour une architecture microservices comprenant un Backend (Java/Spring Boot), une Base de données (PostgreSQL) et un Serveur Web/Reverse Proxy (Apache/Nginx).

L'objectif est d'automatiser les tests, l'analyse de qualité du code et le déploiement des images sur Docker Hub à l'aide de **GitHub Actions**.

## 🏗️ Architecture du Projet

Le dépôt est structuré de la manière suivante :

* **`.github/workflows/`** : Contient le pipeline CI/CD (`main.yml`).
* **`backend/`** : API Java Spring Boot avec configuration Maven.
* **`database/`** : Scripts SQL d'initialisation et Dockerfile pour la base de données.
* **`http-server/`** : Configuration du serveur web et Dockerfile.

## ⚙️ Pipeline CI/CD (GitHub Actions)

Le pipeline s'exécute automatiquement lors d'un `push` ou d'une `pull request` sur la branche principale (`main`). Il comprend les étapes suivantes :

1. **Test Backend** : Compilation et exécution des tests unitaires et d'intégration via Maven.
2. **Analyse de Qualité** : Envoi des rapports de test et de couverture à **SonarCloud**.
3. **Build & Push Docker** : *(Uniquement sur la branche principale)* Construction des images Docker et publication automatique sur **Docker Hub**.

## 🐳 Déploiement Local

Pour lancer l'infrastructure sur votre machine locale, assurez-vous d'avoir [Docker](https://www.docker.com/) installé, puis exécutez à la racine du projet :

```bash
docker-compose up -d --build
```
