# Maquette page d'accueil Medicalem

Maquette HTML autonome de la future page d'accueil de Medicalem, optimisée SEO et GEO (visibilité dans les IA génératives).

## Contenu du dépôt

| Fichier | Rôle |
|---|---|
| `index.html` | Maquette complète de la page d'accueil (Tailwind CSS via CDN, Google Fonts, icônes Lucide, JSON-LD). S'ouvre directement dans un navigateur, connexion internet requise pour les CDN et les images Unsplash. |
| `llms.txt` | Proposition de fichier llms.txt à publier à la racine du site. |
| `docs/mots-cles.md` | Tableau des mots-clés ciblés et de leur emplacement (title, H1, H2, alt, FAQ, JSON-LD). |
| `docs/recommandations-seo-geo-pages-interieures.md` | Règles à appliquer aux fiches produits, pages univers et pages domaines cliniques. |
| `docs/ameliorations-vs-site-actuel.md` | Les 5 principales améliorations, formulées pour le client. |

## Éléments à valider ou à remplacer avant mise en ligne

- Palette : déduite du logo (bleu profond et rouge). À ajuster sur les codes couleur exacts de la charte.
- Images : visuels Unsplash d'illustration, à remplacer par les photos produits et les photos d'équipe officielles.
- Mot de la dirigeante : nom, portrait et citation à remplacer par les éléments validés.
- Actualités et agenda : contenus d'exemple, à remplacer par les vrais articles et événements.
- Marques des quatre nouveautés (BT Inc, Nasco, SkillQube, PCS) : à confirmer par Medicalem.
- URLs des réseaux sociaux dans le JSON-LD et le footer : à remplacer par les adresses exactes.
- Tailwind : le CDN convient à la maquette ; en production, compiler Tailwind pour la performance.
