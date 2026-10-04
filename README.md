# 🇫🇷 Monitor — Notes de frais des élus

[![Licence Ouverte](https://img.shields.io/badge/Licence-Ouverte%202.0-blue)](https://www.etalab.gouv.fr/licence-ouverte-open-licence)
[![Source](https://img.shields.io/badge/Source-Ma%20Dada-0066cc)](https://madada.fr)
[![Plateforme](https://img.shields.io/badge/Plateforme-data.gouv.fr-000091)](https://www.data.gouv.fr)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/fr/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/fr/docs/Web/JavaScript)
[![Chart.js](https://img.shields.io/badge/Chart.js-FF6384?logo=chart.js&logoColor=white)](https://www.chartjs.org/)
[![Leaflet](https://img.shields.io/badge/Leaflet-199900?logo=leaflet&logoColor=white)](https://leafletjs.com/)
[![PapaParse](https://img.shields.io/badge/PapaParse-5.4.1-ff6b6b)](https://www.papaparse.com/)
[![Backend](https://img.shields.io/badge/backend-aucun-success)]()
[![Open Data](https://img.shields.io/badge/Open%20Data-%E2%9C%93-00a95f)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](http://makeapullrequest.com)
[![Made in France](https://img.shields.io/badge/Made%20in-France-000091?logo=flag&logoColor=white)]()
[![Statut](https://img.shields.io/badge/statut-actif-brightgreen)]()

> **Dashboard interactif de visualisation des notes de frais des élus municipaux**, basé sur la *Base de données des notes de frais publiées sur Ma Dada*, publiée sur **data.gouv.fr**.

---

## 🎯 Présentation

Monitor **HTML/CSS/JS tout-en-un** pour explorer, filtrer et visualiser les notes de frais des élus municipaux français.

Données issues de **[Ma Dada](https://madada.fr)** (équivalent français de *WhatDoTheyKnow*) et publiées sur **[data.gouv.fr](https://www.data.gouv.fr/datasets/base-de-donnees-des-notes-de-frais-publiees-sur-ma-dada)**.

**Ce que ça permet :**

- 🔍 Explorer **1 100+ lignes** de dépenses (2020–2023)
- 📊 Analyser montants, catégories, fournisseurs
- 🗺️ Cartographier les dépenses par commune
- 🏆 Classer communes, fournisseurs, postes de dépense
- 📥 Exporter en JSON / CSV

---

## ✨ Fonctionnalités

| Domaine | Détails |
|---|---|
| **Exploration** | Tableau paginé, tri multi-critères, recherche full-text, filtres croisés |
| **Analyses** | Barres, doughnut, courbe temporelle, heatmap custom, Top 10 |
| **Carte** | Leaflet + OpenStreetMap, cercles proportionnels, popups détaillés |
| **Interface** | Sidebar filtres, KPI strip, panneau intelligence, modal, pagination |
| **Export** | JSON (données filtrées) · CSV (BOM UTF-8, compatible Excel) |
| **Design** | Inspiré du Système de Design de l'État, responsive mobile / tablette / desktop |

---

## 🏗️ Architecture

| Chemin | Rôle |
|---|---|
| `frais.html` | Fichier unique tout-en-un (HTML + CSS + JS) |
| `README.md` | Documentation |
| `LICENSE` | Licence Ouverte 2.0 |
| `data/PUBLIC.csv` | Source de données (1177 lignes) |

**Avantages du tout-en-un :** aucun build, aucun bundler, aucune installation npm, portable (un seul fichier), hébergeable partout (GitHub Pages, Netlify, serveur statique).

---

## 🚀 Installation

**Prérequis :** navigateur moderne + Python 3 (ou tout serveur HTTP).

| Étape | Action | Commande |
|---|---|---|
| 1 | Cloner le dépôt | `git clone https://github.com/votre-user/monitor-frais-elus.git` |
| 2 | Entrer dans le dossier | `cd monitor-frais-elus` |
| 3 | Créer le dossier data | `mkdir -p data` |
| 4 | Copier le CSV | `cp /chemin/vers/PUBLIC.csv data/` |
| 5 | Lancer le serveur | `python3 -m http.server 8000` |
| 6 | Ouvrir dans le navigateur | http://localhost:8000/frais.html |

> ⚠️ **Obligatoire :** serveur local (sinon CORS bloque le chargement du CSV).

**Alternative VS Code :** extension *Live Server* → clic droit sur `frais.html` → *Open with Live Server*.

---

## 🎮 Utilisation

| Action | Résultat |
|---|---|
| Barre de recherche | Filtre fournisseur, objet, commune, activité |
| Onglet (Restauration, Vêtements…) | Filtre par catégorie |
| Commune dans la sidebar | Filtre par commune |
| Tri | Réordonne (date, montant, commune) |
| Clic sur une carte | Ouvre le détail en modal |

**Onglets d'analyse :** 📋 Dépenses · 🗺️ Carte · 📊 Graphiques · 🏛️ Communes · 📄 JSON brut

---

## 📊 Structure des données

| Colonne | Exemple |
|---|---|
| `Date` | `2/27/2023` |
| `Collectivité concernée` | `Aix-en-Provence` |
| `Nom du fournisseur` | `VALOUCILS` |
| `SIRET` | `83132818200033` |
| `Activité principale` | `Soins de beauté` |
| `Objet de la dépense` | `Volume russe - pose complète` |
| `Justificatif` | `image.png (https://…)` |
| `Montant` | `€150.00` |
| `Catégorie` | `Beauté et soins` |
| `Remarques` | — |

**Catégories principales :** 🍽️ Restauration · 👔 Vêtements · 🚆 Transport · 🏨 Hôtel · 💅 Beauté · 🧺 Blanchisserie · 🎫 Congrès · 🌸 Décoration · 🏦 Banque

---

## 🛠️ Technologies

| Techno | Usage | Version |
|---|---|---|
| HTML5 | Structure | — |
| CSS3 | Design (grid, variables, animations) | — |
| JavaScript | Logique applicative | ES2020+ |
| Chart.js | Graphiques | 4.4.0 |
| Leaflet | Carte interactive | 1.9.4 |
| PapaParse | Parsing CSV | 5.4.1 |
| OpenStreetMap | Tuiles carte | — |

**Aucun backend. Aucune base de données. Aucun framework JS.**

---

## 🗺️ Feuille de route

- [x] Chargement CSV via PapaParse
- [x] Filtres multi-critères
- [x] Graphiques Chart.js
- [x] Carte Leaflet
- [x] Heatmap custom
- [x] Export JSON / CSV
- [x] Design responsive
- [ ] Filtre par plage de dates
- [ ] Filtre par plage de montants
- [ ] Comparaison de communes
- [ ] Mode sombre
- [ ] Recherche floue (Levenshtein)
- [ ] Détection d'anomalies
- [ ] Export PDF
- [ ] Tests unitaires (Vitest)

---

## 🤝 Contribuer

| Étape | Action |
|---|---|
| 1 | Fork le projet |
| 2 | Créer une branche : `git checkout -b feature/ma-super-feature` |
| 3 | Commit : `git commit -m "feat: ajoute le filtre par plage de dates"` |
| 4 | Push : `git push origin feature/ma-super-feature` |
| 5 | Ouvrir une Pull Request |

**Conventions de commit :** [Conventional Commits](https://www.conventionalcommits.org/) — `feat:`, `fix:`, `docs:`, `style:`, `refactor:`, `test:`, `chore:`.

---

## 📄 Licence

Ce projet est distribué sous **[Licence Ouverte 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence)** (Etalab), compatible avec la **CC-BY 4.0**.

| Droit | Condition |
|---|---|
| ✓ Partager — copier, distribuer, communiquer | ⓘ Attribution — mentionner la source (data.gouv.fr, Ma Dada) |
| ✓ Adapter — remixer, transformer, créer | ⓘ Pas de restriction supplémentaire |
| ✓ Utiliser à des fins commerciales | — |

Voir le fichier [LICENSE](LICENSE) pour le texte complet.

---

## 🙏 Sources & crédits

| Élément | Lien |
|---|---|
| **Données originales** | [Base de données des notes de frais publiées sur Ma Dada](https://www.data.gouv.fr/datasets/base-de-donnees-des-notes-de-frais-publiees-sur-ma-dada) |
| **Collecte** | [Ma Dada](https://madada.fr) |
| **Plateforme** | [data.gouv.fr](https://www.data.gouv.fr) |
| **Inspiration design** | [Système de Design de l'État](https://www.systeme-de-design.gouv.fr/) |
| **Bibliothèques** | Chart.js (MIT) · Leaflet (BSD-2-Clause) · PapaParse (MIT) |

---

## 📬 Contact

| Canal | Lien |
|---|---|
| **Issues** | [Ouvrir une issue](../../issues) |
| **Discussions** | [Ouvrir une discussion](../../discussions) |

---

<div align="center">

**Fait avec ❤️ pour la transparence démocratique**

[⬆ Retour en haut](#-monitor--notes-de-frais-des-élus)

</div>
