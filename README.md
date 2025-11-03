# Lettres Antarctique

Projet de lettres interactives pour l'Antarctique, converti de Twine vers HTML standard.

## Structure du projet

```
banquise/
├── index.html                  # Page d'accueil avec la boîte aux lettres
├── boite-aux-lettres.html     # Grille de toutes les lettres disponibles
├── styles.css                 # Tous les styles du projet
├── index-twine-old.html       # Ancienne version Twine (sauvegarde)
│
├── lettres/                   # Dossier contenant toutes les pages de lettres
│   ├── _template.html         # Template pour créer de nouvelles lettres
│   ├── debut.html             # ✅ Lettre terminée (style manuscrit)
│   ├── cuddle.html            # ⏳ Lettre non terminée
│   ├── vert.html              # ✅ Lettre terminée (avec galerie de plantes)
│   ├── tete.html              # ✅ Lettre terminée (avec galerie de têtes)
│   ├── manchot.html           # ✅ Lettre terminée (avec certificat PDF)
│   ├── aurore.html            # ✅ Lettre terminée
│   ├── ennui.html             # ✅ Lettre terminée (avec lecteur audio)
│   └── ... (autres lettres à créer)
│
├── img/                       # Images du projet
│   ├── boite.png             # Image de la boîte aux lettres
│   ├── lettre.png            # Image pour les lettres terminées
│   ├── lettre_soon.png       # Image pour les lettres à venir
│   ├── abeille.png           # Image pour la lettre Cuddle
│   ├── fleurs/               # Dossier des images de plantes (pour Vert)
│   └── tetes/                # Dossier des images de têtes (pour Tête)
│
├── doc/                       # Documents
│   └── certificat.pdf        # Certificat d'adoption de manchot
│
└── son/                       # Fichiers audio (si nécessaire)
```

## Statut des lettres

### Lettres terminées (affichent lettre.png)
- ✅ Début - Lettre d'introduction avec style manuscrit
- ✅ Vert - Galerie de plantes avec JavaScript
- ✅ Tête - Galerie de photos avec JavaScript
- ✅ Manchot - Avec bouton pour ouvrir un certificat PDF
- ✅ Aurore - (contenu à compléter)
- ✅ Ennui - Lecteur audio de podcast avec design moderne type Deezer

### Lettres à venir (affichent lettre_soon.png)
- ⏳ Cuddle - Simple lettre avec image d'abeille (page non terminée)
- ⏳ Anniversaire
- ⏳ Noël
- ⏳ Halloween
- ⏳ Pâques
- ⏳ St Valentin
- ⏳ Amis
- ⏳ Artifice
- ⏳ Solitude
- ⏳ Tempête
- ⏳ Blague
- ⏳ Début
- ⏳ Fin
- ⏳ Bravo
- ⏳ Dispute
- ⏳ Froid
- ⏳ Nian Nian
- ⏳ Smack
- ⏳ Bonus

## Comment ajouter une nouvelle lettre

1. **Copier le template**
   ```bash
   cp lettres/_template.html lettres/nom-de-la-lettre.html
   ```

2. **Modifier le fichier**
   - Changer le titre dans `<title>` et `<h1>`
   - Ajouter le contenu de la lettre
   - Ajouter des images, boutons, ou scripts si nécessaire

3. **Mettre à jour boite-aux-lettres.html**
   - Changer la classe de `coming-soon` à `fini` pour la lettre
   - Vérifier que le lien pointe vers le bon fichier

## Modification du statut d'une lettre

Dans `boite-aux-lettres.html`, changer la classe CSS :

```html
<!-- Lettre à venir (image lettre_soon.png) -->
<div class="lettre_bouton coming-soon">

<!-- Lettre terminée (image lettre.png) -->
<div class="lettre_bouton fini">
```

## Styles CSS

Tous les styles sont dans `styles.css` et sont organisés par sections :
- Styles globaux
- Page d'accueil
- Page boîte aux lettres
- Bouton retour
- Pages de lettres
- Galerie d'images
- Certificat

## JavaScript

Les pages qui utilisent JavaScript (Vert, Tête) ont leur code directement dans la page HTML.
Le JavaScript est utilisé pour :
- Afficher aléatoirement des images dans les galeries
- Gérer les boutons de navigation
- Ouvrir des fichiers PDF

## Notes

- L'ancien fichier Twine est sauvegardé dans `index-twine-old.html`
- Plus besoin de SugarCube ou de macros Twine
- Tout le code est maintenant en HTML/CSS/JavaScript standard
- Les chemins des images et fichiers sont relatifs au fichier HTML
