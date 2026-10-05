# Recommandations SEO et GEO pour les pages intérieures

Ces règles prolongent celles appliquées à la page d'accueil. Elles s'appliquent aux trois gabarits à décliner : fiches produits, pages univers, pages domaines cliniques. Un quatrième bloc couvre les règles transverses au site.

## 1. Fiches produits

Objectif : être la page de référence française sur chaque simulateur, citée par Google et par les IA quand un formateur demande « quel mannequin pour... ».

Structure recommandée
- URL : `/produits/[marque]-[nom-produit]-[type]`, par exemple `/produits/gaumard-hal-s3201-mannequin-haute-fidelite`.
- Title (55 à 60 caractères) : `[Nom produit], [type de simulateur] [marque] | Medicalem`.
- Meta description : bénéfice pédagogique, public visé, mention « devis » ou « leasing ».
- H1 : nom du produit suivi du type, par exemple « HAL S3201, mannequin haute fidélité adulte ».
- Premier paragraphe « réponse d'abord » (2 à 3 phrases) : ce qu'est le produit, pour qui, quels gestes il permet d'enseigner. Ce paragraphe doit pouvoir être cité seul.
- H2 dans cet ordre : Pour quelles formations, Compétences travaillées, Caractéristiques, Contenu de la livraison et options, Maintenance et SAV, Financement (leasing, Resah), Produits complémentaires, FAQ produit (3 à 5 questions).
- Tableau de caractéristiques en HTML (`<table>`), pas en image : les IA extraient très bien les tableaux.
- Bouton « Ajouter à ma cotation » visible sans défilement, rappel sticky sur mobile.
- Fil d'Ariane : Accueil > Gamme > Produit, avec balisage BreadcrumbList.

Données structurées
- `Product` : name, image (photos officielles, plusieurs angles), brand, sku ou mpn si disponible, description, category, offers (availability, priceCurrency, seller) ; ajouter `additionalProperty` pour les caractéristiques clés.
- `FAQPage` sur la FAQ produit.
- `BreadcrumbList`.

Contenu et maillage
- Nommer explicitement la marque, le type (haute fidélité, procédural, échogène), les domaines cliniques et les univers concernés, en liens internes.
- Lier vers la page SAV, la page leasing et la page Resah depuis la fiche : ces trois liens répondent aux objections d'achat.
- Vidéos de démonstration hébergées sur Vimeo intégrées avec `VideoObject` et transcription texte.
- Alt des images : « [Nom produit], [type], vue [angle ou geste] ».

## 2. Pages univers

Objectif : capter les requêtes « matériel de simulation pour [public] » et servir de page d'entrée pour les décideurs du secteur.

Structure recommandée
- URL : `/univers/[nom-univers]`.
- Title : `Simulateurs et mannequins pour [univers] | Medicalem`.
- H1 orientée besoin : « Simulation médicale pour les IFSI et instituts de formation ».
- Paragraphe d'ouverture citable : qui est concerné, quels gestes et compétences, quelle part de ce public Medicalem équipe déjà (uniquement les chiffres validés, par exemple 75 % des IFSI).
- H2 : Les compétences à former, Les simulateurs recommandés (par niveau de formation), Exemples de configurations de salle, Financement et achat public, Témoignages ou cas d'usage (uniquement avec accord écrit), FAQ univers.
- Sélection de produits dynamique par univers avec filtres par type et budget.

Données structurées
- `CollectionPage` + `ItemList` des produits présentés.
- `FAQPage`.
- `BreadcrumbList`.

Contenu et maillage
- Chaque page univers lie vers les 3 à 5 domaines cliniques les plus pertinents et inversement.
- Intégrer un guide téléchargeable ou une checklist par univers (par exemple « Équiper une salle de simulation en IFSI ») : contenu long, citable, générateur de liens entrants.
- Signaler les cadres réglementaires ou référentiels de formation réellement applicables, avec sources.

## 3. Pages domaines cliniques

Objectif : répondre aux requêtes d'intention précise (« simulateur échographie », « simulateur accouchement ») et aux questions posées aux IA par spécialité.

Structure recommandée
- URL : `/domaines/[domaine]`.
- Title : `Simulateurs de [domaine] pour la formation | Medicalem`.
- H1 : « Simulateurs et mannequins de [domaine] ».
- Paragraphe d'ouverture : quels gestes de la spécialité se simulent, avec quels types de simulateurs, pour quels publics.
- H2 : Gestes et procédures couverts (une sous-section H3 par geste, chacune reliée aux produits correspondants), Mannequins haute fidélité pour ce domaine, Simulateurs procéduraux pour ce domaine, Choisir selon le niveau de formation, FAQ domaine.
- Glossaire court des termes de la spécialité : utile aux apprenants, très bien repris par les IA.

Données structurées
- `CollectionPage` + `ItemList`.
- `FAQPage`.
- `DefinedTermSet` pour le glossaire si présent.

## 4. Règles transverses au site

Technique
- Une seule H1 par page, hiérarchie Hn sans saut, balises sémantiques (header, nav, main, article, aside, footer).
- Canonical sur chaque page, hreflang inutile tant que le site est monolingue.
- Sitemap XML segmenté (produits, univers, domaines, actualités) et déclaré dans robots.txt.
- Images : WebP ou AVIF, dimensions déclarées, lazy loading hors zone visible, CDN.
- Objectifs Core Web Vitals : LCP < 2,5 s, INP < 200 ms, CLS < 0,1. Compiler Tailwind en production plutôt que le CDN.
- Pagination des listes produits avec liens `rel` explicites et URLs propres ; filtres en paramètres non indexés (noindex ou canonical vers la page de base).

GEO (visibilité dans les IA génératives)
- Publier le fichier `llms.txt` à la racine et le maintenir à jour à chaque nouvelle gamme.
- Chaque page commence par une réponse autonome de 2 à 3 phrases, nommant Medicalem, le sujet et le public.
- Chiffres toujours contextualisés et datés (« en 2026, Medicalem équipe... ») ; mettre à jour annuellement.
- Pages « auteur » pour l'équipe conseil et SAV (nom, fonction, formation chez Gaumard, années d'expérience) et attribution des articles de blog à ces auteurs, avec balisage `Person`.
- Page « À propos » détaillée : histoire, statut d'entreprise à mission, engagements RSE, partenariats officiels avec liens sortants vers les sites des fabricants (signal de confiance réciproque).
- Autoriser explicitement les robots des IA dans robots.txt (GPTBot, ClaudeBot, PerplexityBot, Google-Extended) si la stratégie est d'être cité.
- FAQ sur chaque gabarit, questions formulées en langage naturel, réponses de 40 à 80 mots, balisage FAQPage strictement identique au texte affiché.
- Comparatifs et guides d'achat (« mannequin haute fidélité ou simulateur procédural : lequel choisir ») : formats les plus cités par les IA.

Conversion et données
- « Ma cotation » persistante (localStorage puis compte client), export PDF de la cotation, envoi en un clic.
- Formulaires courts, champ « établissement » et « univers » pour qualifier les leads.
- Suivi des conversions (devis, appels, ajouts cotation) dans l'outil analytics, avec consentement conforme CNIL.
