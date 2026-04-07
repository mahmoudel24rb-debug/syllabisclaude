# CLAUDE.md — Projet Syllabis (Sanity + Next.js)

## Contexte du projet

Projet de test/apprentissage pour créer une landing page Next.js connectée à Sanity CMS.
L'objectif est d'avoir **90% du site en statique (codé en dur en React)** et **uniquement la section Services/Features dynamique depuis Sanity Studio**.

## Architecture

```
C:\Users\dglco\Documents\Syllabis\
├── studio-syllabis/     ← Sanity Studio (CMS admin)
│   └── localhost:3333
└── nextjs-syllabis/     ← Front Next.js (site public)
    └── localhost:3000
```

## Stack technique

- **Front** : Next.js 16.2.2 (App Router, TypeScript, Tailwind CSS, Turbopack)
- **CMS** : Sanity.io (projet ID: `xj1jfi1v`, dataset: `production`)
- **Dépendances** : `next-sanity`, `@sanity/image-url`
- **Structure front** : `src/` directory (src/app/, src/sanity/)

## Sanity Studio — Schéma actuel

Un seul type de document : **Service**

```typescript
// schemaTypes/service.ts
{
  name: "service",
  type: "document",
  fields: [
    { name: "title", type: "string" },       // Nom du service
    { name: "description", type: "text" },    // Description
    { name: "icon", type: "string" },         // Emoji ou nom d'icône
    { name: "order", type: "number" },        // Ordre d'affichage
  ]
}
```

3-4 services de test sont déjà créés et publiés dans le Studio.

## Front Next.js — Structure actuelle

```
nextjs-syllabis/src/
├── sanity/
│   ├── client.ts          ← Client Sanity configuré (projectId, dataset)
│   └── queries.ts         ← Query GROQ pour récupérer les services
├── app/
│   ├── page.tsx           ← Page principale (fetch services + rendu)
│   ├── layout.tsx         ← Layout par défaut Next.js
│   └── components/
│       ├── Navbar.tsx      ← Navigation (statique)
│       ├── Hero.tsx        ← Section hero (statique)
│       ├── Services.tsx    ← Section services (DYNAMIQUE depuis Sanity)
│       ├── About.tsx       ← Section à propos (statique)
│       ├── Contact.tsx     ← Formulaire de contact (statique)
│       └── Footer.tsx      ← Pied de page (statique)
```

### Client Sanity (`src/sanity/client.ts`)

```typescript
import { createClient } from "next-sanity";
import imageUrlBuilder from "@sanity/image-url";
import type { SanityImageSource } from "@sanity/image-url/lib/types/types";

export const client = createClient({
  projectId: "xj1jfi1v",
  dataset: "production",
  apiVersion: "2024-01-01",
  useCdn: false,
});

const { projectId, dataset } = client.config();

export const urlFor = (source: SanityImageSource) =>
  projectId && dataset
    ? imageUrlBuilder({ projectId, dataset }).image(source)
    : null;
```

### Query GROQ (`src/sanity/queries.ts`)

```typescript
export const SERVICES_QUERY = `*[_type == "service"] | order(order asc) {
  _id,
  title,
  description,
  icon,
  order
}`;
```

### Page principale (`src/app/page.tsx`)

```typescript
// Fetch les services depuis Sanity, passe en props au composant Services
// Tous les autres composants sont statiques (pas de données Sanity)
```

## Ce qui est DYNAMIQUE (Sanity)

- **Services.tsx** : reçoit `services` en props, les affiche en grille. Le client peut ajouter/modifier/supprimer des services dans le Studio.

## Ce qui est STATIQUE (codé en dur)

- Navbar, Hero, About, Contact, Footer : tout le contenu est écrit directement dans le JSX.

## Design attendu

Le design actuel est basique (Tailwind CSS utilities). L'objectif est d'obtenir un design de qualité professionnelle inspiré des landing pages modernes type SaaS :

- **Navbar** : fixe, glassmorphism, logo + liens + CTA
- **Hero** : grand titre, sous-titre, 2 boutons (CTA primaire + secondaire), image/mockup
- **Logos band** : logos de clients/partenaires (statique)
- **Services** : grille de cards avec icônes, titres, descriptions (dynamique Sanity)
- **Témoignage** : quote highlight avec avatar (statique)
- **FAQ** : accordion (statique)
- **Blog** : aperçu de 3 articles (statique)
- **CTA final** : bannière d'appel à l'action (statique)
- **Footer** : colonnes de liens + copyright

### Directives de design

- Utiliser Tailwind CSS pour le styling
- Typographie soignée, espacement généreux
- Animations subtiles (hover, transitions)
- Responsive (mobile-first)
- Palette de couleurs cohérente et moderne
- Pas de design générique "AI slop" — le site doit avoir du caractère

## Commandes utiles

```bash
# Lancer le Studio Sanity
cd studio-syllabis && npm run dev
# → http://localhost:3333

# Lancer le front Next.js
cd nextjs-syllabis && npm run dev
# → http://localhost:3000
```

## Points d'attention

- Les fichiers qui contiennent des balises `<a>` posent problème quand on les crée via PowerShell (le `<` est interprété comme une redirection). Utiliser un script Node.js (.cjs) avec `fs.writeFileSync()` et des arrays de strings `.join("\n")` pour contourner le problème.
- Le projet utilise `src/` directory (pas de fichiers directement dans `app/`)
- Next.js 16 avec Turbopack — hot reload automatique
- Les services dans Sanity sont déjà publiés et accessibles via l'API
