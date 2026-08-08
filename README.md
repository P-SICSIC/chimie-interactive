# Chimie Interactive

Application web (PWA) regroupant des exercices interactifs de chimie générale, à destination d'étudiants de bac+1 à bac+5.

## 🧪 Programmes disponibles

| Programme | Description |
|---|---|
| **Tableau périodique** | Retrouvez chaque élément à sa place. Mode étendu incluant le bloc f (lanthanides/actinides) et la période 7. |
| **Diffusion & mouvement brownien** | Simulation de particules en collision, avec histogramme de distribution des vitesses et visualisation de la diffusion. |
| **Nomenclature** | Quiz formule ↔ nom : ions, sels, acides, composés moléculaires covalents. |
| **Équilibrage rédox** | 20 réactions d'oxydoréduction à équilibrer, en milieu acide ou basique. |

## 📱 Utilisation (pour les étudiants)

1. Ouvrir le lien de l'app dans un navigateur (Chrome sur Android, Safari sur iPhone).
2. Pour l'installer comme une application :
   - **Android (Chrome)** : menu ⋮ → "Ajouter à l'écran d'accueil".
   - **iPhone (Safari)** : bouton Partager (□↑) → "Sur l'écran d'accueil".
3. Une fois installée, l'app fonctionne aussi hors connexion (après une première ouverture avec internet).

## 🚀 Hébergement (pour les mainteneurs)

Le site est 100% statique (HTML/CSS/JS, aucun serveur nécessaire) et peut être hébergé gratuitement.

### Via GitHub Pages
1. Le dépôt doit être **public** (Settings → General → Change visibility).
2. Tous les fichiers (`index.html`, les 4 programmes, `manifest.json`, `sw.js`, `icons/`) doivent être **à la racine** du dépôt.
3. Settings → Pages → Source : "Deploy from a branch" → Branch `main`, dossier `/ (root)` → Save.
4. L'adresse du site apparaît ensuite dans Settings → Pages (format `https://<utilisateur>.github.io/<depot>/`).

### Via Netlify (alternative, dépôt privé possible)
1. Glisser-déposer le dossier du site sur [app.netlify.com/drop](https://app.netlify.com/drop).

## 🗂️ Structure du projet

```
├── index.html                 → page d'accueil
├── tableau-periodique.html
├── simulation-gaz.html
├── nomenclature.html
├── equilibre-redox.html
├── manifest.json               → configuration PWA (nom, icônes, couleurs)
├── sw.js                       → service worker (fonctionnement hors-ligne)
├── icons/
│   ├── icon-192.png
│   └── icon-512.png
└── changelogs/                 → historique détaillé des modifications par programme
    ├── CHANGELOG_tableau_periodique.md
    ├── CHANGELOG_simulation_gaz.md
    ├── CHANGELOG_nomenclature.md
    └── CHANGELOG_equilibre_redox.md
```

## ➕ Ajouter un nouveau programme

1. Créer le fichier HTML du programme (autonome, sans dépendance externe si possible).
2. Ajouter une carte le pointant dans `index.html` (section `.grid`).
3. Ajouter son nom dans la liste `APP_SHELL` de `sw.js`, pour qu'il soit disponible hors-ligne.
4. Créer un `CHANGELOG_<nom>.md` dans `changelogs/` pour suivre ses évolutions.

## 📄 Licence / usage

Usage pédagogique. Aucune donnée personnelle n'est collectée ; des statistiques anonymes de chaque exercice sont collectées pour améliorer l'app.
