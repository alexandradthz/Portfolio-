# 📸 Guide — Ajouter tes photos et vidéos dans le portfolio

> Ce guide est fait pour toi, Alexandra. Pas besoin d'être développeuse —
> chaque étape est expliquée simplement avec les lignes exactes à modifier.

---

## 1. 🖼️ Photo de profil (section Hero)

### Où chercher dans le code

Ouvre `index.html` et cherche le commentaire suivant (autour de la **ligne 1177**) :

```
REMPLACE CE BLOC PAR TA VRAIE PHOTO
```

Tu verras ce bloc juste en dessous :

```html
<div class="hero-photo-placeholder">
  ...
  Ta photo ici
  ...
</div>
```

### Comment remplacer

1. **Supprime** toute la `<div class="hero-photo-placeholder">...</div>`
2. **Remplace-la** par cette ligne :

```html
<img src="photo-profil.jpg" alt="Alexandra Danthez"
     style="width:100%;height:100%;object-fit:cover;border-radius:var(--rayon);" />
```

3. Change `photo-profil.jpg` par le nom exact de ton fichier image.

### Formats acceptés
- ✅ `.jpg` / `.jpeg`
- ✅ `.png`
- ✅ `.webp`

### Conseil
- Photo carrée, **minimum 400×400 px** (idéalement 600×600 px)
- Fond neutre ou professionnel recommandé

---

## 2. 🗂️ Images des projets

Chaque carte projet contient un emplacement réservé à une image.
Voici comment remplacer chacun.

### Étape générale (valable pour tous les projets)

Dans chaque projet, cherche le commentaire indiqué ci-dessous,
puis **remplace le bloc `<div class="project-img-inner">...</div>`**
par une simple balise `<img>`.

**Avant (placeholder) :**
```html
<div class="project-img-inner">
  <svg ...></svg>
  Image du projet
</div>
```

**Après (ta vraie image) :**
```html
<img src="nom-de-ton-image.jpg" alt="Description du projet"
     style="width:100%;height:100%;object-fit:cover;" />
```

---

### 🖼️ Projet 1 — Affiches & Flyers

Cherche le commentaire **(ligne ~1500)** :
```
PROJET 1 — Affiches & Flyers
```

Remplace le placeholder par :
```html
<img src="affiches-flyers.jpg" alt="Affiches & Flyers"
     style="width:100%;height:100%;object-fit:cover;" />
```

---

### 🎬 Projet 2 — Vidéos publicitaires

Cherche le commentaire **(ligne ~1535)** :
```
PROJET 2 — Vidéos publicitaires
```

Pour ce projet, tu peux mettre une image de couverture **ou** intégrer
directement une vidéo → voir la **section 3** de ce guide.

---

### 💻 Projet 3 — Écosystème digital Back Market

Cherche le commentaire **(ligne ~1568)** :
```
PROJET 3 — Écosystème digital Back Market
```

Remplace le placeholder par :
```html
<img src="back-market.jpg" alt="Écosystème digital Back Market"
     style="width:100%;height:100%;object-fit:cover;" />
```

---

### 📱 Projet 4 — Stories, publications & Reels

Cherche le commentaire **(ligne ~1600)** :
```
PROJET 4 — Stories, publications & Reels
```

Remplace le placeholder par :
```html
<img src="stories-reels.jpg" alt="Stories, publications & Reels"
     style="width:100%;height:100%;object-fit:cover;" />
```

---

### Formats acceptés pour les images projets
- ✅ `.jpg` / `.jpeg`
- ✅ `.png`
- ✅ `.webp`

### Taille recommandée
- **800×600 px** minimum (ratio 4:3)
- Poids idéal : moins de 500 Ko par image (utilise [Squoosh](https://squoosh.app) pour compresser)

---

## 3. 🎥 Intégrer une vidéo dans une carte projet

Deux options selon où ta vidéo est hébergée.

---

### Option A — Vidéo sur YouTube ou Vimeo (recommandé)

C'est la méthode la plus simple et la plus rapide à charger.

**Pour YouTube :**
1. Ouvre ta vidéo sur YouTube
2. Clique sur **Partager → Intégrer**
3. Copie l'URL du type `https://www.youtube.com/embed/XXXXXXXX`

**Code à copier-coller à la place du placeholder :**
```html
<iframe
  src="https://www.youtube.com/embed/TON_ID_VIDEO"
  style="width:100%;height:100%;border:none;"
  allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
  allowfullscreen>
</iframe>
```

Remplace `TON_ID_VIDEO` par l'identifiant de ta vidéo YouTube
(les caractères après `/embed/`).

**Pour Vimeo :**
```html
<iframe
  src="https://player.vimeo.com/video/TON_ID_VIDEO"
  style="width:100%;height:100%;border:none;"
  allow="autoplay; fullscreen; picture-in-picture"
  allowfullscreen>
</iframe>
```

---

### Option B — Vidéo uploadée dans le dépôt GitHub

Si tu préfères héberger ta vidéo directement dans ton repo.

> ⚠️ GitHub limite les fichiers à **25 Mo maximum** via l'interface web.
> Pour des vidéos plus lourdes, préfère YouTube ou Vimeo.

**Code à utiliser :**
```html
<video
  src="videos/ma-video.mp4"
  style="width:100%;height:100%;object-fit:cover;"
  controls
  muted
  loop>
</video>
```

Place le fichier dans un dossier `videos/` à la racine du repo
(voir section 4 pour savoir comment uploader).

---

## 4. 📁 Où mettre les fichiers images et vidéos

### Uploader via l'interface GitHub (sans ligne de commande)

1. Va sur ton dépôt GitHub : `github.com/alexandradthz/Portfolio-`
2. Clique sur le bouton **"Add file"** → **"Upload files"**
3. Glisse-dépose tes images ou clique pour les sélectionner
4. En bas, écris un message simple (ex : *"Ajout photos projets"*)
5. Clique sur **"Commit changes"**

### Organisation recommandée des fichiers

```
Portfolio-/
├── index.html
├── images/
│   ├── photo-profil.jpg
│   ├── affiches-flyers.jpg
│   ├── back-market.jpg
│   └── stories-reels.jpg
└── videos/
    └── pub-video.mp4
```

### Comment écrire le bon chemin dans le code HTML

Si ton image est dans un dossier `images/` :
```html
<img src="images/photo-profil.jpg" alt="..." />
```

Si elle est à la racine (même niveau que `index.html`) :
```html
<img src="photo-profil.jpg" alt="..." />
```

> 💡 Le chemin dans le code doit correspondre **exactement** à l'emplacement
> du fichier dans le dépôt — respecte les majuscules/minuscules.

---

## 5. 🔗 Remplacer le lien LinkedIn

### Où chercher dans le code

Cherche le commentaire **(ligne ~1679)** :
```
LINKEDIN — REMPLACE PAR TON VRAI LIEN LINKEDIN
```

Tu verras juste en dessous :
```html
<a href="#" class="contact-link" target="_blank" rel="noopener">
```

### Comment modifier

Remplace `href="#"` par ton vrai lien LinkedIn :
```html
<a href="https://linkedin.com/in/alexandra-danthez" class="contact-link" target="_blank" rel="noopener">
```

> 💡 Ton lien LinkedIn se trouve dans l'URL de ton profil quand tu es connectée.
> Il ressemble à : `https://www.linkedin.com/in/ton-prenom-nom/`

---

## ✅ Récapitulatif rapide

| Élément | Commentaire à chercher | Ligne approximative |
|---|---|---|
| Photo de profil | `REMPLACE CE BLOC PAR TA VRAIE PHOTO` | ~1177 |
| Projet 1 — Affiches & Flyers | `PROJET 1 — Affiches & Flyers` | ~1500 |
| Projet 2 — Vidéos publicitaires | `PROJET 2 — Vidéos publicitaires` | ~1535 |
| Projet 3 — Back Market | `PROJET 3 — Écosystème digital Back Market` | ~1568 |
| Projet 4 — Stories & Reels | `PROJET 4 — Stories, publications & Reels` | ~1600 |
| Lien LinkedIn | `LINKEDIN — REMPLACE PAR TON VRAI LIEN LINKEDIN` | ~1679 |

---

> 💬 **Astuce :** Dans ton éditeur de code (ou même sur GitHub en mode édition),
> utilise **Ctrl+F** (ou Cmd+F sur Mac) pour rechercher directement
> les commentaires indiqués dans ce guide.
