# ArtisTextile — règles du projet

## Le projet
Application web bilingue (français / anglais) : lexique des métiers du textile et du cuir, d'environ 1 900 fiches, avec définitions, équivalences FR/EN et anecdotes historiques.

- Technologie : Astro, site statique. Hébergement gratuit sur GitHub Pages.
- Ne jamais modifier le projet voisin « echos-du-temps ».
- Chris n'est pas développeur : expliquer simplement chaque étape, présenter un plan et attendre son accord avant de construire.
- Les données du lexique viennent d'Excel : elles sont placées dans `src/data/`.

## Couleurs (charte)
| Couleur | Code | Usage |
|---|---|---|
| Marron chocolat | `#4A2E1A` | Textes et titres |
| Turquoise | `#31B7D7` | Accents, boutons, bordures, icônes |
| Rose historique | `#D87093` | Tags et petites touches décoratives |
| Écru | `#F9F6F0` | Fonds |
| Beige | `#CFC6BC` | Contours |

## Contrastes (WCAG AA)
- Autorisé : texte chocolat sur écru ; texte écru ou turquoise sur chocolat.
- Interdit : texte turquoise ou rose sur écru ; texte blanc sur turquoise.
- Les boutons turquoise ont toujours un texte chocolat.

## Polices
- Titres : Spectral SemiBold — H1 32 px, H2 28 px, H3 24 px.
- Texte : Spectral Regular 20 px ; légendes : Spectral Regular 16 px.
- Style Script : touches décoratives uniquement, 24 px minimum.
- Polices installées sur le site (dans `public/fonts/`), jamais chargées depuis Google.

## Boutons
Hauteur 56 px, coins arrondis 12 px, texte Spectral SemiBold 18 px.
- Principal : fond turquoise, texte chocolat ; au survol, fond chocolat, texte écru.
- Secondaire : fond écru, contour et texte chocolat ; au survol, fond turquoise.

## Tags (filtres par métier)
Forme de pilule, contour rose, texte chocolat. Sélectionné : fond chocolat, texte écru.

## Icônes
Bibliothèque Lucide (gratuite), style contour, trait chocolat.

## Langue
- Sélecteur écrit « FR | EN », sans drapeaux.
- Toute l'interface est traduite (fichiers dans `src/i18n/`).
- La recherche fonctionne dans les deux langues.

## Qualité du site
- Coins arrondis partout.
- Accessible : contrastes, textes alternatifs, navigation au clavier.
- Responsive : ordinateur, tablette, téléphone.
- Conforme aux standards W3C (HTML valide).
- Le parcours vers un terme tient en 2 clics maximum.

## Contraintes
- Aucun abonnement payant : uniquement des outils gratuits.
- Ne jamais publier d'informations personnelles concernant Chris (nom, e-mail, adresse…), y compris dans `package.json`, les métadonnées, le code ou les commits.

## Structure des dossiers
- `public/images/` : logo, favicon
- `public/fonts/` : polices Spectral et Style Script
- `src/data/` : données du lexique (exports Excel)
- `src/pages/`, `src/components/`, `src/layouts/` : pages et composants
- `src/i18n/` : traductions de l'interface
- `src/styles/` : styles de la charte
