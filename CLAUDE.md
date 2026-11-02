# ArtisTextile — règles du projet

## Le projet
Application web bilingue (français / anglais) : lexique des métiers du textile et du cuir, d'environ 1 900 fiches, avec définitions, équivalences FR/EN et anecdotes historiques.

- Technologie : Astro, site statique.
- Hébergement : GitHub Pages sert uniquement pour démarrer. Le site sera hébergé plus tard chez OVH, avec un nom de domaine, et le dépôt GitHub passera alors en privé (voir « Hébergement : étapes prévues »).
- Ne jamais modifier le projet voisin « echos-du-temps ».
- Chris n'est pas développeur : expliquer simplement chaque étape, présenter un plan et attendre son accord avant de construire.
- Les vraies fiches du lexique ne sont jamais dans ce dépôt (voir « Dépôt public et données » ci-dessous).

## Dépôt public et données (règle impérative)
Le dépôt GitHub est public, pour pouvoir utiliser GitHub Pages gratuitement. Tout ce qu'il contient est donc lisible par tout le monde, historique git compris.

- Le dépôt ne doit contenir AUCUNE fiche réelle du lexique, même gratuite : ni définition, ni équivalence FR/EN, ni anecdote réelle, ni export Excel/CSV/JSON des vraies données, ni extrait, ni « copie de test ».
- Seules sont autorisées 3 à 5 fiches d'exemple entièrement inventées, pour tester l'affichage. Elles sont signalées comme fictives (ex. champ `exemple: true`) et stockées dans `src/data/`.
- Les vraies fiches seront dans une base de données privée, qui les fournira une par une (pas d'export complet dans le dépôt). L'architecture exacte sera décidée plus tard, avec l'accord de Chris.
- En cas de doute sur le caractère réel d'une donnée : ne pas l'ajouter, demander à Chris.
- Une donnée poussée sur un dépôt public reste récupérable dans l'historique : en cas d'erreur, prévenir Chris immédiatement.
- Ne jamais ajouter de fichier de vraies données au dépôt, et le garder hors du suivi git (`.gitignore`) s'il doit exister en local.

## Hébergement : étapes prévues
1. Maintenant : dépôt public + GitHub Pages (gratuit), uniquement pour démarrer.
2. Plus tard : hébergement chez OVH avec un nom de domaine ; le dépôt GitHub passe en privé et GitHub Pages est arrêté.
- Le code doit rester facile à déplacer : ne pas dépendre de GitHub Pages au-delà de `site` et `base` dans `astro.config.mjs` (qui changeront lors du passage à OVH, `base` redevenant `/`).
- Tant que GitHub Pages est utilisé, le site est servi sous `/artistextile` (`base`) : tous les liens internes, images et polices doivent tenir compte de ce préfixe (utiliser `import.meta.env.BASE_URL`, jamais de `/chemin` en dur).
- L'hébergement OVH et le nom de domaine sont la seule dépense prévue, décidée par Chris ; la règle « aucun abonnement payant » s'applique à tout le reste.
- Passer le dépôt en privé ne rend pas privé ce qui a déjà été publié : la règle « aucune fiche réelle » reste valable en permanence.

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
- `src/data/` : 3 à 5 fiches d'exemple inventées uniquement (jamais de vraies fiches)
- `src/pages/`, `src/components/`, `src/layouts/` : pages et composants
- `src/i18n/` : traductions de l'interface
- `src/styles/` : styles de la charte
