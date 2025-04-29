# 📘 CI/CD - Documentation & Analyse

## 🔧 Étapes du Workflow CI/CD

### 🧪 Frontend - Tests (`.github/workflows/front-tests.yml`)

- **Installation** des dépendances Node.js (v18)
- **Exécution des tests** via `npm run test:prod`
- **Linting** du code avec `npm run lint`
- **Génération du coverage** et upload via GitHub Actions Artifacts
- **Scan SonarQube** pour analyse qualité et couverture

### 🧪 Backend - Tests (`.github/workflows/back-tests.yml`)

- **Installation JDK 11**
- **Build Maven** (`mvn package`)
- **Exécution des tests** avec Maven
- **JaCoCo** pour la couverture de tests, avec upload du rapport
- **Analyse SonarQube** via plugin Maven

### 🐳 Docker CI/CD (`.github/workflows/docker-ci.yml`)

- **Extraction des métadonnées** Docker pour le frontend et backend
- **Login DockerHub** sécurisé avec token
- **Build & Push** des images Docker `geoffroydaumer/projet_10_frontend` et `geoffroydaumer/projet_10_backend` sur DockerHub (hors PR)

---

## 📊 KPIs proposés

| KPI                                                   | Description                                                    | Objectif            |
| ----------------------------------------------------- | -------------------------------------------------------------- | ------------------- |
| ✅ **Couverture du code via les tests pour le back**  | Pourcentage du code couvert par les tests unitaires via JaCoCo | **≥ 80%**           |
| ✅ **Couverture du code via les tests pour le front** | Pourcentage du code couvert par les tests unitaires via Jest   | **Aucune exigence** |
| ⏱️ **Durée de la pipeline CI/CD**                     | Temps moyen d'exécution des tests & builds Docker              | **≤ 5 minutes**     |

---

## 📈 Résultats des dernières exécutions (à mettre à jour après 1ère run)

- **Frontend** :
  - Couverture Jest (test:prod) : `83.33%`
  - SonarQube quality gate : ✅ Passed
- **Backend** :
  - Couverture JaCoCo : `32%`
  - SonarQube quality gate : ✅ Passed
- **Temps total d'exécution** : `2 min 40 s`

---

## 💬 Retours utilisateurs (Notes & Avis)

| Retours utilisateurs                                                                                |
| --------------------------------------------------------------------------------------------------- |
| Impossible de poster une suggestion de blague ! Le bouton tourne et fait planter mon navigateur     |
| Un bug a été remonté sur le post de la vidéo                                                        |
| Un utilisateur ne reçoit plus rien, il a envoyé un mail il y a 5 jours qui est resté sans nouvelles |

---

## 📦 Artifacts et Rapports disponibles

- `frontend-coverage` : rapport Jest généré dans `front/coverage/bobapp`
- `jacoco-report` : rapport JaCoCo dans `back/target/site/jacoco/`
- SonarQube : intégration active pour le backend (`sonar-maven-plugin`) et le frontend (`sonarqube-scan-action`)
