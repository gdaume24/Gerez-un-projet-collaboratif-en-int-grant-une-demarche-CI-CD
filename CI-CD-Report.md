# 📘 CI/CD - Documentation & Analyse

## 🔧 Étapes du Workflow CI/CD

### 🧪 Frontend - Tests (`.github/workflows/front-end-tests.yml`)

- **Installation** des dépendances Node.js (v20)
- **Exécution des tests** via `npm run test:prod`
- **Linting** du code avec `npm run lint`
- **Génération du coverage** et upload via GitHub Actions Artifacts
- **Scan SonarQube** pour analyse qualité et couverture

### 🧪 Backend - Tests (`.github/workflows/back-end-tests.yml`)

- **Installation JDK 11**
- **Build Maven** (`mvn package`)
- **Exécution des tests** avec Maven
- **JaCoCo** pour la couverture de tests, avec upload du rapport
- **Analyse SonarQube** via plugin Maven

### 🐳 Docker CI/CD (`.github/workflows/docker-ci.yml`)

- **Extraction des métadonnées** Docker pour le frontend et backend
- **Login DockerHub** sécurisé avec token
- **Build & Push** des images Docker `frontend` et `backend` sur DockerHub (hors PR)

---

## 📊 KPIs proposés

| KPI                               | Description                                                              | Objectif        |
| --------------------------------- | ------------------------------------------------------------------------ | --------------- |
| ✅ **Code coverage (tests)**      | Pourcentage du code couvert par les tests unitaires (via JaCoCo ou Jest) | **≥ 80%**       |
| ⏱️ **Durée de la pipeline CI/CD** | Temps moyen d'exécution des tests & builds Docker                        | **≤ 5 minutes** |

---

## 📈 Résultats des dernières exécutions (à mettre à jour après 1ère run)

- **Frontend** :
  - Couverture Jest (test:prod) : `83.33%`
  - SonarQube quality gate : ✅ Passed
- **Backend** :
  - Couverture JaCoCo : `32%`
  - SonarQube quality gate : ✅ Passed
- **Temps total d'exécution** : `ex: 4 min 35 s`

---

## 💬 Retours utilisateurs (Notes & Avis)

| Retours utilisateurs                                                      |
| ---------------------------------------------------------------------- |
| Impossible de poster une suggestion de blague ! Le bouton tourne et fait planter mon navigateur |
| Un bug a été remonté sur le post de la vidéo |
| Un utilisateur ne reçoit plus rien, il a envoyé un mail il y a 5 jours qui est resté sans nouvelles |

---

## ✅ Recommandations

- ✅ **Augmenter la couverture frontend** :
  - Ajouter des tests ciblés sur les composants critiques (paiement, login)
- ✅ **Améliorer la qualité SonarQube backend** :
  - Supprimer les duplications et simplifier les méthodes longues
- 🔄 **Automatiser les tests E2E** (Cypress ou Playwright)
- 🕵️‍♂️ **Vérification post-déploiement automatique** à intégrer (ping service, test d’API)

---

## 📦 Artifacts et Rapports disponibles

- `frontend-coverage` : rapport Jest généré dans `front/coverage/bobapp`
- `jacoco-report` : rapport JaCoCo dans `back/target/site/jacoco/`
- SonarQube : intégration active pour le backend (`sonar-maven-plugin`) et le frontend (`sonarqube-scan-action`)

---

> 🎯 **Objectif final** : Obtenir une pipeline CI/CD automatisée, rapide, fiable et accompagnée d’analyses qualité avec couverture test ≥ 80%
