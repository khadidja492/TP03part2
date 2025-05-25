# TP3 – Tests d’Intégration avec Spring Boot, JUnit et Docker

## Objectifs

Ce projet vise à :

- Intégrer une base de données MySQL dans un environnement de test isolé avec Docker.
- Réaliser des **tests d'intégration** avec **JUnit 5**.
- Utiliser **Testcontainers** pour automatiser la gestion des dépendances (MySQL).
- Comparer les tests unitaires classiques avec des tests réels contre des services externes.

---

## Environnement technique

- **Langage** : Java 17+
- **Framework** : Spring Boot 3.x
- **Tests** : JUnit 5, Testcontainers
- **Base de données** : MySQL 8.0 (conteneurisé)
- **Build tool** : Maven
- **IDE recommandé** : IntelliJ IDEA
- **Docker requis** : Oui (Docker Desktop)

---
## Fonctionnalités testées

-  Création d'une entité `Task`
-  Sauvegarde en base MySQL réelle
-  Récupération et mise à jour
-  Suppression et vérification
-----
## Scénarios testés

| Scénario         | Méthode cible       | Résultat attendu              |
|------------------|----------------------|-------------------------------|
| Créer tâche      | `createTask()`       | ID généré, contenu correct    |
| Lire tâche       | `getTaskById()`      | Titre et description exacts   |
| Modifier tâche   | `updateTask()`       | Champs mis à jour             |
| Supprimer tâche  | `deleteTask()`       | Accès levée (exception)       |
-----
## Comparaison avec tests classiques

| Critère           | Tests classiques     | Testcontainers         |
|-------------------|----------------------|------------------------|
| Rapidité          | ⚡️⚡️⚡️               | ⚡️⚡️                   |
| Réalisme          | ❌                   | ✅                      |
| Maintenance       | ✅                   | ⚠️ Nécessite Docker     |
| Proche production | ❌                   | ✅                      |

                     |

 **Testcontainers simule un environnement réel**, ce qui renforce la robustesse des tests.
