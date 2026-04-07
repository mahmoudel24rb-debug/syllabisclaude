# Prompt — Refonte contenu site Syllabis (demande client)

## Contexte

Le client a envoyé un document PDF (`Contenu_Site_internet.pdf` dans le dossier racine) avec le nouveau contenu qu'il veut sur le site. Lis ce PDF en priorité. Le positionnement du site change complètement.

**AVANT** : positionnement technique/outil ("Du référentiel à la formation e-learning en quelques minutes")
**APRÈS** : positionnement business/conformité ("Le copilote IA des organismes de formation, pour une conformité absolue et une productivité décuplée")

Le site déployé est sur https://syllabis.vercel.app. Le code source du front est dans le dossier qui contient `src/app/`. Tout le contenu est statique (codé en dur dans le JSX), pas besoin de Sanity pour ces changements.

---

## CHANGEMENTS À APPLIQUER

### 1. HERO SECTION (page d'accueil)

**Remplacer le contenu actuel du hero par :**

- **Titre** : "Le copilote IA des organismes de formation"
- **Sous-titre** : "Pour une conformité absolue et une productivité décuplée."
- **Texte d'accroche sous le sous-titre** : "Créé par un organisme de formation, pour les organismes de formation."
- **CTA principal** : "Demander une démo" (garder)
- **CTA secondaire** : "Découvrir Syllabis" → scroll vers la section 2

Le badge "Nouveau — Génération vidéo & podcast par IA" peut rester ou être remplacé par un badge plus orienté conformité, au choix.

Le screenshot dans le BrowserMockup reste, mais privilégier une image qui montre l'arborescence pédagogique ou le mindmap si disponible.

---

### 2. SECTION 2 — "Ce que fait Syllabis" (NOUVELLE SECTION)

Cette section remplace ou complète la section "Comment ça marche". C'est une section de présentation du concept.

**Contenu :**

> À partir d'une fiche RNCP, Syllabis vous assiste dans la création de vos formations — de l'arborescence pédagogique jusqu'à la création de contenu — et vous assure une conformité absolue entre les attentes des certificateurs et la validation des compétences des apprenants.

**Design :**
- Texte centré, grande typographie (text-display-sm ou md)
- En dessous : un visuel/screenshot montrant l'arborescence (utiliser `formation-creation.png` qui montre les blocs de compétences, ou `creer-formation.png`)
- Le client mentionne un "GIF avec l'arborescence du mindmap" — pour l'instant mettre un screenshot statique dans un BrowserMockup, on pourra ajouter un GIF plus tard

---

### 3. SECTION 3 — "Qui sommes-nous" (REFONTE COMPLÈTE)

C'est la section la plus importante pour le client. Elle remplace la section "À propos" actuelle. Elle doit être directement sur la homepage, pas sur une page séparée.

**Partie 1 — Le constat du secteur :**

Titre : "Organisme de formation depuis 25 ans"
Sous-titre : "Nous assistons aux premières loges à la mutation de notre secteur."

4 problèmes à lister avec icônes :
1. "Réduction des niveaux de prise en charge (NPEC)" 
2. "Exigences des certificateurs de plus en plus fortes"
3. "Développement des formations ouvertes à distance (FOAD)"
4. "Dépendance aux formateurs externes"

Texte de transition : "Ces bouleversements ont un impact direct sur nos marges et la rentabilité de nos structures. Ainsi nous avons lancé la création de Syllabis en 2025."

**Partie 2 — Ce que permet Syllabis (3 points) :**

1. "Créer des programmes pédagogiques complets, assistés par l'IA, pour répondre plus rapidement aux appels d'offres."
2. "Générer l'ensemble de nos contenus, pour permettre aux formateurs indépendants de se concentrer sur l'animation des formations."
3. "Prouver en un export l'alignement parfait entre les validations des compétences et les objectifs pédagogiques, pour réduire la lourdeur administrative."

**Partie 3 — Les résultats concrets :**

Titre : "Résultats"

4 chiffres clés à afficher en grand :
- "+20% de FOAD en moyenne dans nos formations"
- "100% de maîtrise du contenu dispensé aux élèves"
- "×3 appels d'offres traités, avec un taux de conversion de 20 à 30%"
- "÷7 le temps de création d'un titre professionnel"

**Partie 4 — Tableau comparatif RÉEL (pas générique) :**

Titre : "Divisé par 7 le temps de création"
Sous-titre : "Exemple avec le titre : Formateur pour adultes"

| Étape | Sans Syllabis | Avec Syllabis |
|-------|---------------|---------------|
| Création de l'arborescence pédagogique, du bloc à la séance | 80h | 8h |
| Création du contenu + validation des compétences | 1600h | 80h |
| Contrôle qualité | 40h | 40h |
| **TOTAL** | **1720h** | **128h** |

Ce tableau remplace le tableau "Avant/Après" actuel (qui avait des valeurs génériques comme "2-3 jours", "3 secondes").

---

### 4. SECTION 4 — Fonctionnalités (SIMPLIFIER)

Le client veut seulement **3 fonctionnalités principales**, pas 6 piliers.

**Les 3 blocs :**

1. **Arborescence pédagogique**
   - Icône : arbre/structure
   - "À partir d'une fiche RNCP, Syllabis vous permet de créer vos blocs, modules, séquences et séances pédagogiques."

2. **Création de contenu**
   - Icône : édition/contenu
   - "Création du contenu des formations pour les séances en FOAD et en présentiel. Génération d'images, vidéos, quiz..."

3. **Export SCORM**
   - Icône : export/download
   - "Export en format SCORM pour utilisation dans un LMS tiers."

**Design :** 3 cards côte à côte, style simple et professionnel (comme dans le PDF du client — des rectangles arrondis avec du texte).

**IMPORTANT** : Supprimer ou déplacer les 3 autres piliers (Médias IA NotebookLM, Pilotage & Planning, Multi-tenant) vers une section secondaire ou vers les sous-pages de fonctionnalités. Ils ne doivent plus être mis en avant sur la homepage.

---

### 5. SECTIONS À SUPPRIMER OU DÉPLACER DE LA HOMEPAGE

**Supprimer de la homepage :**
- Le bandeau "39+ blocs interactifs · 6 certifications · 4 modèles IA · Export SCORM" — remplacé par les vrais chiffres du client
- La section "Comment ça marche" en 5 étapes — remplacée par la section 2 (concept Syllabis)
- La section chiffres clés (39+, 6, 5, 4, 7, 2) — remplacée par les résultats du client (+20% FOAD, ×3 appels d'offres, ÷7 temps)
- L'ancien tableau "Avant/Après" générique — remplacé par le vrai tableau du client (1720h → 128h)

**Garder sur la homepage :**
- Le hero (modifié)
- Le CTA final "Prêt à transformer..." (adapter le texte)
- Le footer (garder tel quel)

---

### 6. BANDEAU CHIFFRES CLÉS (NOUVEAU)

Remplacer l'ancien bandeau par les vrais chiffres du client :

```
+20% de FOAD | ×3 appels d'offres | ÷7 temps de création | 100% maîtrise du contenu
```

---

### 7. CTA FINAL (ADAPTER)

Remplacer :
"Prêt à transformer vos référentiels en formations ?"

Par quelque chose comme :
"Prêt à décupler la productivité de votre organisme de formation ?"
Sous-titre : "Demandez une démo et découvrez comment Syllabis divise par 7 le temps de création de vos formations."

---

### 8. PAGE "À PROPOS" (METTRE À JOUR)

La page `/a-propos` doit être mise à jour avec le contenu de la section "Qui sommes-nous" du PDF (OF depuis 25 ans, les problèmes du secteur, etc.). Le contenu de la homepage et de la page à propos peuvent se recouper — c'est normal.

---

### 9. PAGES DE FONCTIONNALITÉS (ADAPTER)

Les 6 sous-pages de fonctionnalités restent mais leur contenu doit être adapté au nouveau ton du client :
- Moins technique ("player React moderne", "227+ endpoints API")  
- Plus orienté bénéfices pour un OF ("conformité", "gain de temps", "appels d'offres", "FOAD")

---

### 10. NE PAS TOUCHER

- La structure des pages (routes, layout, navbar, footer)
- La palette de couleurs navy/ambre
- Les screenshots dans `public/screenshots/`
- Les icônes SVG existantes
- Le responsive
- Le SEO (meta titles/descriptions) — sauf adapter les textes au nouveau positionnement

---

## ORDRE DES SECTIONS SUR LA HOMEPAGE (NOUVEAU)

```
1. Navbar (inchangée)
2. Hero — "Le copilote IA des organismes de formation"
3. Section concept — "À partir d'une fiche RNCP..."
4. Section "Qui sommes-nous" — OF 25 ans, constats, résultats
5. Tableau comparatif — Formateur pour adultes (1720h → 128h)
6. Chiffres clés — +20% FOAD, ×3 appels d'offres, ÷7 temps
7. Section fonctionnalités — 3 blocs (arborescence, contenu, SCORM)
8. CTA final — "Prêt à décupler votre productivité ?"
9. Footer (inchangé)
```

---

## TON ET STYLE DU CONTENU

Le client est un **organisme de formation qui parle à d'autres OF**. Le ton doit être :

- **Professionnel et institutionnel** — pas startup/tech
- **Orienté résultats business** — marges, productivité, conformité, appels d'offres
- **Vocabulaire formation pro** — RNCP, NPEC, FOAD, certificateurs, blocs de compétences, séances
- **Crédibilité terrain** — "nous sommes OF depuis 25 ans", "nous avons les mêmes problèmes que vous"
- **PAS de jargon dev** — pas de "React", "API", "endpoints", "pipeline asynchrone", "multi-tenant"

---

## VÉRIFICATIONS APRÈS MODIFICATIONS

- [ ] Le hero affiche le nouveau positionnement
- [ ] La section concept avec la fiche RNCP est présente
- [ ] La section "Qui sommes-nous" avec les 4 problèmes et les 3 solutions est sur la homepage
- [ ] Le tableau comparatif utilise les vrais chiffres du client (1720h → 128h)
- [ ] Les chiffres clés sont ceux du client (+20%, ×3, ÷7, 100%)
- [ ] Les fonctionnalités sont réduites à 3 blocs
- [ ] Aucune mention de "API", "endpoints", "React", "pipeline", "multi-tenant" sur la homepage
- [ ] Le ton est institutionnel/OF, pas startup/tech
- [ ] Le build passe (`npm run build`)
- [ ] Commit + push avec message "refonte contenu homepage — brief client"

---

## ORDRE DE TRAVAIL

1. Lire le PDF `Contenu_Site_internet.pdf` pour le contexte complet
2. Modifier le hero (titre, sous-titre, accroche)
3. Créer la section concept (fiche RNCP → arborescence → contenu → conformité)
4. Créer la section "Qui sommes-nous" (constats + solutions + résultats)
5. Remplacer le tableau avant/après par le vrai tableau du client
6. Remplacer les chiffres clés
7. Simplifier les fonctionnalités à 3 blocs
8. Adapter le CTA final
9. Mettre à jour la page /a-propos
10. Nettoyer le jargon technique sur les autres pages
11. Build + test + commit + push
