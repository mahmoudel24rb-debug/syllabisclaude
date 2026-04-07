# Arborescence du site Syllabis

## Structure des pages

```
syllabis.fr/
├── / (Homepage)
├── /fonctionnalites
│   ├── /fonctionnalites/generation-ia
│   ├── /fonctionnalites/editeur
│   ├── /fonctionnalites/medias-ia
│   ├── /fonctionnalites/export-scorm
│   ├── /fonctionnalites/pilotage-planning
│   └── /fonctionnalites/multi-tenant
├── /tarifs
├── /cas-usage
│   ├── /cas-usage/organismes-formation
│   ├── /cas-usage/formateurs-independants
│   ├── /cas-usage/entreprises
│   └── /cas-usage/edtech
├── /a-propos
├── /contact
├── /demo
├── /blog (futur)
└── /legal
    ├── /legal/mentions-legales
    ├── /legal/cgu
    └── /legal/politique-confidentialite
```

---

## 1. Homepage — `/`

**Objectif** : Convaincre en 30 secondes, pousser vers la démo ou l'inscription.

### Hero Section
- **Titre** : "Du référentiel à la formation e-learning. En quelques minutes."
- **Sous-titre** : "Syllabis transforme un PDF de certification (RNCP, BTS, CAP, CQP, BPJEPS) en formation complète — structure, contenu interactif, quiz, vidéos — grâce à l'IA."
- **CTA principal** : "Demander une démo"
- **CTA secondaire** : "Voir comment ça marche"
- **Visuel** : Animation/mockup montrant l'upload d'un PDF → génération de la formation

### Bandeau social proof
- Chiffres clés en ligne : "39+ blocs interactifs · 6 certifications supportées · 227+ endpoints API · Export SCORM 1.2 & 2004"
- Ou logos d'OF partenaires si disponibles

### Section "Comment ça marche" (flow en 5 étapes)
1. Upload du référentiel PDF (ou description texte) — "3 secondes"
2. L'IA analyse et propose la structure — "Blocs, modules, heures détectés automatiquement"
3. Génération du contenu complet — "Séances, quiz, exercices en 2-5 minutes"
4. Personnalisation dans l'éditeur 39 blocs — "Quiz, vidéos, podcasts, mind maps..."
5. Export SCORM ou Planning formateurs — "Déployez sur n'importe quel LMS"

### Section "Les 6 piliers" (aperçu des fonctionnalités)
- 6 cards avec icône + titre + description courte + lien "En savoir plus"
  1. Génération IA complète
  2. Éditeur 39+ blocs interactifs
  3. Médias IA (vidéos, podcasts, quiz)
  4. Export SCORM universel
  5. Pilotage & Planning
  6. Multi-tenant & Enterprise

### Section "Avant/Après" ou Comparaison
- Tableau simple : "Créer une formation manuellement : 3 semaines → Avec Syllabis : 3 minutes"
- Ou comparaison visuelle côte à côte

### Section Témoignage / Social proof
- 1-2 témoignages d'OF ou formateurs (quand disponibles)
- En attendant : chiffres clés stylisés (formations générées, blocs disponibles, etc.)

### Section CTA final
- "Prêt à transformer vos référentiels en formations ?"
- CTA : "Demander une démo gratuite"

### Footer
- Liens vers toutes les pages
- Contact, réseaux sociaux
- Mentions légales, CGU, Politique de confidentialité

---

## 2. Page Fonctionnalités (hub) — `/fonctionnalites`

**Objectif** : Vue d'ensemble de toutes les fonctionnalités, avec liens vers les pages détaillées.

### Hero
- **Titre** : "Tout ce dont vous avez besoin pour créer des formations e-learning"
- **Sous-titre** : "6 modules intégrés, de l'analyse du référentiel au déploiement sur votre LMS."

### Grille des 6 fonctionnalités
- Chaque fonctionnalité = card avec icône, titre, description (3-4 lignes), screenshot/mockup, bouton "Découvrir"

### Bandeau chiffres clés
- 39+ blocs · 7 types de médias · 4 modèles IA · 5 rôles · 2 formats SCORM

---

## 2a. Génération IA — `/fonctionnalites/generation-ia`

**Contenu détaillé :**
- Comment l'upload PDF fonctionne (types de fichiers acceptés)
- Certifications supportées : TP, BTS, CAP, CQP, BPJEPS, Custom
- Ce que l'IA détecte automatiquement : type de certification, blocs de compétences, modules, heures, prérequis, RNCP ID
- La hiérarchie générée : Formation → Blocs → Modules → Séquences → Séances → Architecture → Contenu
- Feedback loop : preview avant validation, régénération avec instructions
- Mode "from scratch" : décrire la formation en texte libre
- 4 modèles IA disponibles
- Captures d'écran / vidéo démo de la génération

---

## 2b. Éditeur de contenu — `/fonctionnalites/editeur`

**Contenu détaillé :**
- Éditeur BlockNote style Notion
- Liste complète des 39+ blocs organisés par catégorie :
  - **Quiz interactifs** (7) : QCM, Vrai/Faux, Texte à trou, Drag & Drop, Tri, Scénario branching, Hotspot image
  - **Médias riches** (6) : Vidéo, Audio, Images IA, Code, Embed, Podcast
  - **Blocs pédagogiques** (9) : Objectifs, Définitions, Citations, Callout, Alertes, Timeline, Steps, Accordion, Tabs, Flashcards
  - **Visualisation** (5) : Mind Map, Tableaux, Diagrammes, Infographies, Comparaisons
- Système de thèmes : 10+ presets + custom
- Slash commands (/)
- Autosave temps réel
- Mode preview instantané
- Screenshots de l'éditeur avec différents blocs

---

## 2c. Médias IA (NotebookLM) — `/fonctionnalites/medias-ia`

**Contenu détaillé :**
- Intégration NotebookLM
- 7 types de médias générés automatiquement :
  1. Vidéos explicatives (Explainer / Tutorial)
  2. Podcasts audio (Deep Dive / Briefing)
  3. Quiz IA avec niveaux de difficulté
  4. Flashcards pour révision espacée
  5. Mind Maps visuelles
  6. Infographies
  7. Tableaux de données
- Pipeline asynchrone avec suivi de progression
- Exemples concrets de médias générés

---

## 2d. Export SCORM — `/fonctionnalites/export-scorm`

**Contenu détaillé :**
- Formats : SCORM 1.2 & SCORM 2004
- LMS compatibles : Moodle, Blackboard, Canvas, Docebo, TalentLMS, iSpring...
- Player React moderne (pas du HTML statique)
- Tracking : score, complétion, temps passé, réponses aux quiz
- Navigation par chapitres avec sidebar
- Tokens SCORM avec expiration pour partage direct
- Schéma visuel : Syllabis → Export SCORM → LMS

---

## 2e. Pilotage & Planning — `/fonctionnalites/pilotage-planning`

**Contenu détaillé :**
- Vue calendrier : drag-drop des séances, gestion dates/horaires
- Vue tableau : édition inline (titre, heures, format, semaine, formateur, type)
- Assignment de formateurs par niveau hiérarchique
- Export Excel 7 onglets (détailler chaque onglet)
- Suivi des incohérences d'heures
- Dashboard formation : KPI, progression par bloc, répartition présentiel/distanciel/e-learning/autonomie
- Screenshots des vues calendrier et tableau

---

## 2f. Multi-tenant & Enterprise — `/fonctionnalites/multi-tenant`

**Contenu détaillé :**
- Organisations : branding custom (logo, couleur primaire)
- 5 rôles détaillés : Owner, Admin, Concepteur, Formateur, Lecture seule
- Branch access : accès par branche spécifique
- Cost tracking : suivi des coûts IA par formation, utilisateur, modèle, jour
- Analytics : dashboard global et par formation
- Emails transactionnels : invitations, bienvenue, reset password, partage
- Idéal pour : réseaux d'OF, groupes de formation, franchises

---

## 3. Tarifs — `/tarifs`

**Objectif** : Présenter les plans de manière claire et pousser vers la démo.

### Structure de pricing (à adapter selon le modèle choisi)

**Starter** (Formateur indépendant)
- X formations/mois
- 1 utilisateur
- Blocs éditeur de base
- Export SCORM 1.2
- Support email

**Pro** (Organisme de formation)
- Formations illimitées
- Jusqu'à 10 utilisateurs
- Tous les blocs éditeur
- Export SCORM 1.2 & 2004
- Médias IA (vidéos, podcasts)
- Planning & pilotage
- Support prioritaire

**Enterprise** (Multi-tenant)
- Tout Pro +
- Multi-organisations
- Branding custom
- Branch access
- Cost tracking & analytics avancés
- SSO / API
- Account manager dédié

### FAQ pricing
- Essai gratuit ?
- Engagement minimum ?
- Peut-on changer de plan ?
- Comment fonctionne la facturation IA ?

---

## 4. Cas d'usage (hub) — `/cas-usage`

**Objectif** : Montrer comment Syllabis s'adapte à chaque profil.

### 4a. Organismes de formation — `/cas-usage/organismes-formation`
- Problème : 50-200 formations/an, production manuelle chronophage, conformité RNCP
- Solution Syllabis : industrialiser la production, respecter les référentiels, gagner du temps
- Fonctionnalités mises en avant : Génération IA, Export SCORM, Planning, Multi-tenant
- Chiffre : "De 3 semaines à 3 minutes pour créer une formation"
- CTA : "Demander une démo pour votre OF"

### 4b. Formateurs indépendants — `/cas-usage/formateurs-independants`
- Problème : créer des formations certifiantes seul, sans équipe technique
- Solution Syllabis : upload du référentiel, l'IA fait le reste
- Fonctionnalités mises en avant : Génération IA, Éditeur 39 blocs, Export SCORM
- CTA : "Créez votre première formation gratuitement"

### 4c. Entreprises — `/cas-usage/entreprises`
- Problème : digitaliser la formation interne, former les collaborateurs à distance
- Solution Syllabis : créer du contenu e-learning de qualité sans expertise pédagogique
- Fonctionnalités mises en avant : Éditeur, Médias IA, Export SCORM, Analytics
- CTA : "Découvrir Syllabis pour votre entreprise"

### 4d. EdTech & Startups — `/cas-usage/edtech`
- Problème : proposer du contenu e-learning à leurs clients, multi-tenant
- Solution Syllabis : plateforme white-label, API, organisations multiples
- Fonctionnalités mises en avant : Multi-tenant, API (227+ routes), Branding custom
- CTA : "Discutons de votre intégration"

---

## 5. À propos — `/a-propos`

**Contenu :**
- Vision : démocratiser la création de formations e-learning grâce à l'IA
- Pourquoi Syllabis existe : le constat du marché (création manuelle trop lente, outils fragmentés)
- L'équipe (si pertinent)
- Stack technique (optionnel, pour crédibilité tech) : React, NestJS, PostgreSQL, Gemini
- Valeurs : innovation, qualité pédagogique, accessibilité
- Mentions : RNCP, France Compétences, Qualiopi (si applicable)

---

## 6. Contact — `/contact`

**Contenu :**
- Formulaire : Nom, Email, Organisme, Rôle (OF / Formateur / Entreprise / EdTech), Message
- Email direct
- Réseaux sociaux
- FAQ rapide (3-4 questions)

---

## 7. Demander une démo — `/demo`

**Objectif** : Page de conversion principale.

**Contenu :**
- Titre : "Voyez Syllabis en action"
- Sous-titre : "30 minutes pour découvrir comment l'IA transforme vos référentiels en formations complètes."
- Formulaire : Nom, Email, Organisme, Nombre de formations/an, Certifications concernées, Créneau préféré
- Ce que la démo inclut : upload d'un vrai référentiel, génération en direct, tour de l'éditeur, export SCORM
- Témoignage ou chiffre clé pour rassurer

---

## 8. Blog — `/blog` (futur)

**Catégories prévues :**
- Tutoriels : "Comment créer un cours BPJEPS en 5 minutes", "Exporter en SCORM pour Moodle"
- Actualités : nouvelles fonctionnalités, mises à jour IA
- Pédagogie : bonnes pratiques e-learning, quiz interactifs, ingénierie pédagogique
- Référentiels : actualités RNCP, France Compétences, Qualiopi

---

## 9. Pages légales — `/legal/`

- `/legal/mentions-legales` : mentions légales standard
- `/legal/cgu` : conditions générales d'utilisation
- `/legal/politique-confidentialite` : politique RGPD, cookies

---

## Éléments communs à toutes les pages

### Navbar
- Logo Syllabis
- Liens : Fonctionnalités (dropdown avec les 6 sous-pages), Tarifs, Cas d'usage, À propos
- CTA : "Demander une démo" (bouton primary)
- Burger menu mobile

### Footer
- 4 colonnes : Produit (liens fonctionnalités), Ressources (blog, démo, contact), Entreprise (à propos, tarifs), Légal (mentions, CGU, confidentialité)
- Logo + baseline
- Réseaux sociaux
- "© 2025 Syllabis. Tous droits réservés."

---

## Priorité de développement recommandée

| Phase | Pages | Pourquoi |
|-------|-------|----------|
| **Phase 1** | Homepage, Tarifs, Contact, Démo, Legal | MVP — suffisant pour lancer et convertir |
| **Phase 2** | Fonctionnalités (hub + 6 sous-pages) | SEO + détail pour les prospects qualifiés |
| **Phase 3** | Cas d'usage (hub + 4 sous-pages) | Personnalisation par persona |
| **Phase 4** | Blog, À propos | SEO long terme + crédibilité |
