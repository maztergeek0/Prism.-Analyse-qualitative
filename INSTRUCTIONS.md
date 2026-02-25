# INSTRUCTIONS — Guide Interactif Courses Updates Tracker 2.0

## 🎯 Description du projet

Ce projet est un **guide de formation interactif en HTML** qui reproduit
fidèlement l'interface Airtable du Courses Updates Tracker 2.0.
L'objectif est qu'un utilisateur puisse cliquer sur chaque élément de
l'interface et voir une bulle d'aide expliquant quoi faire et pourquoi.

---

## 🏗️ Priorité absolue : La carcasse avant tout

Ce qui est **CRITIQUE** à reproduire parfaitement :

- La **disposition exacte** de chaque vue (tableau, colonnes, lignes)
- Le **panneau latéral droit** qui s'ouvre au clic sur un billet — c'est
  l'élément le plus important du guide
- Les **menus déroulants** et leur comportement au clic
- La **navigation latérale gauche** avec toutes les étapes
- Les **boutons, cases à cocher, champs de date** — position et apparence
- Les **couleurs de statut** (vert, rouge, orange) exactement comme dans Airtable

Ce qui est **SECONDAIRE** :

- Le texte exact dans les cellules — utilise des données fictives réalistes

> 💡 Imagine que tu construis une **maquette interactive d'un cockpit
> d'avion** — tous les boutons doivent être au bon endroit et réagir au
> clic, même si les chiffres sont fictifs. L'utilisateur doit avoir
> l'impression d'être dans le vrai Airtable.

---

## 📸 Captures d'écran — Instruction critique

> ⛔ **Ne jamais commencer une page d'interface sans avoir la capture
> d'écran correspondante.** Si le dossier est vide, demander à
> l'utilisateur de la fournir avant de continuer.

Les captures d'écran se trouvent dans :
```
Captures d'écran/Step 1: Create a Ticket/
Captures d'écran/Step 1.1: Edit a Ticket/
Captures d'écran/Step 2: Manager's Decision/
Captures d'écran/Step 3: To Do – Designers & GTs/
Captures d'écran/Step 4: Final Decision/
Captures d'écran/Step 5: Archives/
```

Chaque dossier peut contenir **plusieurs captures** :
- Vue générale du tableau
- Vue avec le panneau latéral droit ouvert
- Zoom sur des sections spécifiques

Utilise **toutes les captures disponibles** pour le dossier concerné
avant de générer le HTML.

---

## 📐 Rôle des captures d'écran

Les captures d'écran fournies sont des **références visuelles de
l'interface réelle Airtable**. Ton travail est de :

1. **Reproduire fidèlement la mise en page** — disposition des colonnes,
   tableaux, boutons, champs, menus tels qu'ils apparaissent
2. **Identifier chaque élément cliquable** — chaque champ, bouton, menu
   déroulant, case à cocher doit devenir une zone interactive
3. **Créer une bulle d'aide pour chaque élément** — au clic, une bulle
   s'affiche avec l'explication du champ
4. **Ne pas copier les données** — les noms de cours, dates et valeurs
   sont des exemples. Ce qui compte c'est la structure.

> La capture d'écran = le plan d'architecte. Tu construis l'interface
> HTML à partir de ce plan.

---

## 🎨 Style visuel — À respecter sur toutes les pages

> ⭐ **Référence officielle de style** : Lire et analyser le fichier
> `Code HTML/Step 1: Create a Ticket/step1-v2.html` avant de créer
> toute nouvelle page. Ce fichier est le modèle de référence — toutes
> les autres pages doivent être visuellement cohérentes avec lui.

```css
--violet:       #7B2FFF
--violet-dark:  #5B1FCC
--sidebar-bg:   #6B21D9
--white:        #ffffff
--gray-50:      #F8F9FA
--gray-800:     #343A40
--tooltip-bg:   #1A1A2E
--tooltip-accent: #7B2FFF
```

- Police : **DM Sans** (Google Fonts)
- Bulles d'aide : fond foncé `#1A1A2E`, accent violet
- Sidebar : fond violet `#6B21D9`
- Bannière de formation en haut de chaque page

---

## 📁 Structure du projet

```
courses-updates-tracker-guide/
├── README.md
├── INSTRUCTIONS.md                     ← ce fichier
├── MENU_PRINCIPAL_GRILLE.md            ← grille complète du repo
│
├── Captures d'écran/                   ← déposer les captures d'écran ici
│   ├── Step 1: Create a Ticket/
│   ├── Step 1.1: Edit a Ticket/
│   ├── Step 2: Manager's Decision/
│   ├── Step 3: To Do – Designers & GTs/
│   ├── Step 4: Final Decision/
│   └── Step 5: Archives/
│
├── Code HTML/                          ← déposer les fichiers HTML ici
│   ├── Step 1: Create a Ticket/        ✅ Terminée
│   ├── Step 1.1: Edit a Ticket/        ✅ Terminée
│   ├── Step 2: Manager's Decision/     🔄 En cours
│   ├── Step 3: To Do – Designers & GTs/ ⏳ À faire
│   ├── Step 4: Final Decision/         ⏳ À faire
│   └── Step 5: Archives/               ⏳ À faire
│
└── Guide/                              ← source de vérité pour les bulles d'aide
    └── README.md
```

---

## 🌐 Langue

**Interface (navigation, titres, données)** : Bilingue FR/EN — exactement comme l'outil Airtable original. Les captures d'écran reflètent cela.

**Bulles d'aide** : Français seulement pour l'instant.

> 🔮 Fonctionnalité future : ajouter un toggle FR/EN pour les bulles d'aide. Ne pas l'implémenter maintenant, mais structurer le code pour que ce soit facile à ajouter plus tard (ex: attributs `data-fr` et `data-en` sur chaque bulle).

---

## 💬 Comportement des bulles d'aide

Les bulles d'aide doivent respecter ces règles de comportement :

- **Une seule bulle ouverte à la fois** — si une bulle est déjà ouverte et que l'utilisateur clique sur un autre élément, la première se ferme automatiquement avant que la nouvelle s'ouvre
- **Se ferme quand le curseur quitte la bulle** — dès que la souris sort de la zone de la bulle, elle se ferme
- **Animation à l'ouverture** — apparition avec un effet fluide (ex: fade-in + légère montée)

---

## 📚 Structure du cours interactif

Le guide est un **cours interactif complet** qui reproduit la logique de
la présentation PowerPoint existante (`Guide/`), mais qui prend vie dans
le navigateur. L'utilisateur progresse page par page, exactement comme
dans une présentation, jusqu'à ce que l'interface Airtable devienne
interactive.

### Parcours complet de l'utilisateur

```
┌─────────────────────────────────────────────────────┐
│  INTRODUCTION (slides de présentation → HTML)       │
├─────────────────────────────────────────────────────┤
│  00-accueil.html         → Page titre du cours      │
│  01-objectif.html        → But du système           │
│  02-processus.html       → Les 5 étapes visuelles   │
│  03-roles.html           → Rôles et responsabilités │
├─────────────────────────────────────────────────────┤
│  STEP 1 — Create a Ticket                           │
├─────────────────────────────────────────────────────┤
│  step1-intro.html        → Explication de l'étape   │
│  step1-interface.html    → 🖥️ Interface interactive  │
├─────────────────────────────────────────────────────┤
│  STEP 1.1 — Edit a Ticket                           │
├─────────────────────────────────────────────────────┤
│  step1-1-intro.html      → "La Tour de Contrôle"    │
│  step1-1-interface.html  → 🖥️ Interface interactive  │
├─────────────────────────────────────────────────────┤
│  STEP 2 — Manager's Decision                        │
│  STEP 3 — To Do – Designers & GTs                   │
│  STEP 4 — Final Decision                            │
│  STEP 5 — Archives                                  │
│  (même structure intro + interface pour chaque)     │
├─────────────────────────────────────────────────────┤
│  conclusion.html         → Récapitulatif + lien     │
│                            vers Airtable            │
└─────────────────────────────────────────────────────┘
```

### Deux types de pages

**Pages d'introduction (style présentation)**
- Fond blanc, typographie claire, style identique à la présentation PowerPoint
- Contenu tiré directement des slides du fichier `Guide/`
- Pas de bulles d'aide — juste de l'information claire et visuelle

**Pages d'interface interactive (style Airtable)**
- Reproduction fidèle de l'interface Airtable
- Chaque élément est cliquable → bulle d'aide en français
- L'utilisateur a l'impression d'être dans le vrai outil

### Expérience utilisateur cible

> L'utilisateur suit le cours comme une présentation. Quand il arrive
> sur une page "interface", l'outil Airtable s'ouvre devant lui et
> devient interactif. C'est le moment "aha" du cours.

---

## 🧭 Navigation entre les pages

- Chaque page est un **fichier HTML séparé** avec des liens directs
- La **sidebar gauche** est identique sur toutes les pages (intro + steps)
- La page active est **mise en évidence** dans la sidebar
- Boutons **"Page précédente"** et **"Page suivante"** en bas de chaque page

---

## 📋 Règles techniques

- **Un seul fichier HTML par étape** — CSS et JS inclus dedans, pas de
  fichiers séparés
- **Compatible Google Canvas** — pas de dépendances externes
  problématiques
- **Bulles d'aide en français** par défaut
- **Chaque page est autonome** — elle fonctionne seule ET avec la
  navigation

---

## 🎨 Couleurs des statuts — À reproduire exactement

### Work Progress / État d'avancement
```
Not Started / Non commencée     → rouge     #DC3545
In Progress / En cours          → bleu      #007BFF
Completed / Terminée            → vert      #28A745
On Hold / En pause              → orange    #FD7E14
With CSPS other team            → mauve     #6F42C1
Cancelled                       → gris      #6C757D
Not Approved – Changes Required → rouge     #DC3545
```

### Manager Decision / Décision du gestionnaire
```
Pending Assignment              → gris      #6C757D
To Address Now                  → vert      #28A745
To Address Later                → bleu      #007BFF
No Need to Address              → rouge     #DC3545
```

### Task Status / Statut de la tâche
```
On time                         → point vert
Late / En retard                → point rouge
```

---

## 🖥️ Comportement du panneau latéral droit — Élément critique

Le panneau latéral droit est **l'élément le plus important** du guide.
Il doit être reproduit avec une précision maximale.

### Déclenchement
- S'ouvre quand l'utilisateur **clique sur une ligne** du tableau
- Occupe environ **40% de la largeur** de l'écran à droite
- Le tableau principal rétrécit à gauche pour laisser la place

### Structure du panneau (de haut en bas)
```
┌─────────────────────────────────┐
│ [←] Titre du billet / Request ID│  ← bouton fermer + titre
│─────────────────────────────────│
│ Section : Rôle concerné         │  ← encadré gris = section du rôle
│  Champ 1 .............. [valeur]│
│  Champ 2 .............. [valeur]│
│─────────────────────────────────│
│ Section suivante                │
│  Champ 3 .............. [valeur]│
└─────────────────────────────────┘
```

### Règle des encadrés gris
Les sections que **le rôle actif doit remplir** sont entourées d'un
encadré gris visible. C'est un signal visuel important à reproduire.

### Comportement interactif dans le guide
- Clic sur une ligne → panneau s'ouvre avec animation (slide-in)
- Clic sur [←] ou en dehors → panneau se ferme
- Chaque champ du panneau est cliquable → bulle d'aide en français

---

### Convention de nommage des versions

```
v1.0.0  → Version majeure (ex: ajout du bilinguisme complet)
v1.1.0  → Nouvelle fonctionnalité (ex: nouvelle page d'intro)
v1.1.1  → Correction ou ajustement mineur (ex: texte d'une bulle)
```

### Branches Git — quand en créer une

| Situation | Branche à créer | Exemple |
|-----------|----------------|---------|
| Correction mineure | Pas de branche — commit direct sur `main` | Corriger une bulle d'aide |
| Nouvelle page ou fonctionnalité | `feat/nom-de-la-fonctionnalité` | `feat/page-roles` |
| Version bilingue FR/EN des bulles | `feat/bilinguisme-bulles` | |
| Refonte visuelle majeure | `feat/refonte-design` | |
| Test expérimental | `experiment/nom` | `experiment/navigation-tabs` |

### Messages de commit standardisés

```
feat:     nouvelle page ou fonctionnalité
fix:      correction d'un bug ou d'une erreur
content:  modification du contenu des bulles d'aide
style:    ajustement visuel sans changement de fonctionnalité
docs:     mise à jour de la documentation
refactor: restructuration du code sans changement visible
```

### Feuille de route des versions prévues

```
v1.0  → 🔄 En cours — Pages d'intro + Steps 1 à 5 en français
v1.1  → ⏳ Bulles d'aide bilingues FR/EN (toggle)
v1.2  → ⏳ Pages d'intro complètes (rôles, processus, pourquoi Airtable)
v2.0  → ⏳ Version bilingue complète FR/EN
```

### Comment demander des modifications à Claude Code

**Correction mineure :**
> *"Dans `step1-interface.html`, corrige le texte de la bulle du champ 'Course Code'"*

**Nouvelle fonctionnalité :**
> *"Crée une nouvelle branche `feat/bilinguisme-bulles` et ajoute un toggle FR/EN sur les bulles d'aide de toutes les pages"*

**Nouvelle version majeure :**
> *"On commence la v2.0 — crée une branche `feat/v2-bilingue` et adapte toutes les pages pour être entièrement bilingues"*

---

1. Lire ce fichier `INSTRUCTIONS.md` au début de chaque session
2. Lire les fichiers HTML existants dans `Code HTML/` pour comprendre le style
3. Lire les captures d'écran dans `Captures d'écran/[Step X]/` pour reproduire l'interface
4. Lire le contenu des bulles d'aide dans `Guide/`
5. Générer le fichier HTML et le déposer dans `Code HTML/[Step X]/`
6. Commiter sur GitHub avec le message correspondant :
   - `feat: step 1 - create ticket`
   - `feat: step 1.1 - edit ticket`
   - `feat: step 2 - manager decision`
   - `feat: step 3 - to do designers gts`
   - `feat: step 4 - final decision`
   - `feat: step 5 - archives`
7. Ne jamais créer de PR — merger directement sur main

---

## 💬 Contenu des bulles d'aide

Le contenu des bulles d'aide se trouve dans les fichiers de
documentation dans `/Guide` :
https://github.com/maztergeek0/courses-updates-tracker-guide/tree/main/Guide

Utilise ces fichiers comme source de vérité pour toutes les descriptions
et instructions.
