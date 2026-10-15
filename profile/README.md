<p align="center">
  <h1 align="center">AssioCorp</h1>
  <p align="center">
    <b>Plateforme logicielle modulaire de gestion associative</b>
    <br />
    Adhésions &bull; Événements &bull; Ressources &bull; Trésorerie &bull; Communication
  </p>
  <p align="center">
    <a href="https://github.com/AssioCorp/assio-frontend"><img src="https://img.shields.io/badge/frontend-React_19-0284c7?style=flat&labelColor=18181b&logo=react&logoColor=38bdf8" height="20" alt="Frontend" /></a>
    <a href="https://github.com/AssioCorp/assio-backend"><img src="https://img.shields.io/badge/backend-Spring_Boot-16a34a?style=flat&labelColor=18181b&logo=springboot&logoColor=4ade80" height="20" alt="Backend" /></a>
    <a href="https://github.com/AssioCorp/assio-devops"><img src="https://img.shields.io/badge/orchestration-Docker_Compose-2563eb?style=flat&labelColor=18181b&logo=docker&logoColor=60a5fa" height="20" alt="DevOps" /></a>
    <a href="https://developercertificate.org/"><img src="https://img.shields.io/badge/dco-enforced-ea580c?style=flat&labelColor=18181b&logo=git&logoColor=fb923c" height="20" alt="DCO" /></a>
    <a href="https://www.conventionalcommits.org/"><img src="https://img.shields.io/badge/commits-conventional-db2777?style=flat&labelColor=18181b&logo=conventionalcommits&logoColor=f472b6" height="20" alt="Conventional Commits" /></a>
  </p>
  <h4 align="center">
    <a href="#aperçu">Aperçu</a> &bull;
    <a href="#fonctionnalités">Fonctionnalités</a> &bull;
    <a href="#dépôts">Dépôts</a> &bull;
    <a href="#démarrage-rapide">Démarrage Rapide</a> &bull;
    <a href="#standards">Standards</a>
  </h4>
</p>

---

<h2 align="center">Aperçu</h2>

**ASSIO** est un système intégré développé pour simplifier et fiabiliser la gestion quotidienne des associations. La plateforme remplace la dispersion des outils tiers et des tableurs en unifiant le cycle de vie des adhérents, les inscriptions aux événements, la réservation d'équipements partagés et le suivi budgétaire en temps réel au sein d'une interface unique.

---

<h2 align="center">Fonctionnalités</h2>

- **Adhésions & Membres** : Formulaires d'adhésion en ligne, validation des dossiers, annuaire centralisé et gestion fine des habilitations par rôles.
- **Planning & Événements** : Calendrier des activités, billetterie, gestion des jauges, listes d'attente et émargement numérique.
- **Ressources partagées** : Réservation de salles et de matériel avec détection automatisée des conflits d'horaires.
- **Trésorerie & Cotisations** : Émission et suivi des cotisations, encaissements, ventilation comptable et exports financiers.
- **Communication** : Diffusion d'annonces par groupes, notifications automatisées et coffre-fort documentaire.

---

<h2 align="center">Dépôts</h2>

L'architecture est découpée en dépôts indépendants et spécialisés :

| Dépôt | Description | Stack Technique | Statut CI |
| :--- | :--- | :--- | :--- |
| **[`assio-frontend`](https://github.com/AssioCorp/assio-frontend)** | Application web client réactive et modulaire | React 19, Vite, TanStack, Tailwind CSS v4, Biome | <a href="https://github.com/AssioCorp/assio-frontend/actions"><img src="https://img.shields.io/github/actions/workflow/status/AssioCorp/assio-frontend/ci.yml?branch=main&style=flat&labelColor=18181b&color=16a34a&logo=github&label=ci" height="20" alt="Frontend CI" /></a> |
| **[`assio-backend`](https://github.com/AssioCorp/assio-backend)** | API REST, logique métier centrale et persistance | Java 25, Spring Boot 4, PostgreSQL, OpenAPI | <a href="https://github.com/AssioCorp/assio-backend/actions"><img src="https://img.shields.io/github/actions/workflow/status/AssioCorp/assio-backend/ci.yml?branch=main&style=flat&labelColor=18181b&color=16a34a&logo=github&label=ci" height="20" alt="Backend CI" /></a> |
| **[`assio-devops`](https://github.com/AssioCorp/assio-devops)** | Orchestration multi-services et décisions d'architecture | Docker Compose v2, GitHub Actions, ADRs | <a href="https://github.com/AssioCorp/assio-devops"><img src="https://img.shields.io/badge/status-active-16a34a?style=flat&labelColor=18181b" height="20" alt="DevOps" /></a> |
| **[`demo-repository`](https://github.com/AssioCorp/demo-repository)** | Dépôt bac à sable pour validation de la gouvernance | HTML5, GitHub Actions, DCO | <a href="https://github.com/AssioCorp/demo-repository"><img src="https://img.shields.io/badge/dco-active-16a34a?style=flat&labelColor=18181b" height="20" alt="DCO" /></a> |

---

<h2 align="center">Démarrage Rapide</h2>

Pour lancer l'ensemble des services en local via [`assio-devops`](https://github.com/AssioCorp/assio-devops) :

```bash
# 1. Cloner les dépôts frères
git clone https://github.com/AssioCorp/assio-frontend.git
git clone https://github.com/AssioCorp/assio-backend.git
git clone https://github.com/AssioCorp/assio-devops.git

# 2. Démarrer la stack complète
cd assio-devops
docker compose --profile full up -d --build
```

Endpoints locaux une fois la stack démarrée :
- **Frontend** : [http://localhost:5173](http://localhost:5173)
- **API Swagger** : [http://localhost:8080/swagger-ui.html](http://localhost:8080/swagger-ui.html)
- **PostgreSQL** : `localhost:5432` (`assio_db` / `assio_user`)

---

<h2 align="center">Standards</h2>

Tout travail soumis à l'organisation doit respecter les règles de contribution suivantes :

- **Signoff DCO obligatoire** : Chaque commit doit comporter la mention légale d'origine via `git commit -s`. Le workflow de validation bloque automatiquement toute PR non conforme.
- **Conventional Commits** : Messages de commit formatés selon la spécification (`feat:`, `fix:`, `refactor:`, etc.), validés localement par Lefthook et Commitlint.
- **Signature SSH** : Les contributeurs sont tenus d'activer la signature cryptographique (`git config --global commit.gpgsign true`) pour obtenir le statut vérifié sur GitHub.

---

<p align="center">
  <sub>AssioCorp &copy; 2026 &bull; Plateforme ASSIO</sub>
</p>
