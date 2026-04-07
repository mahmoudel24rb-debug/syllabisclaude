# Prompt Corrections Homepage — Syllabis

## Contexte
La homepage actuelle est bien structurée visuellement mais le contenu texte doit être retravaillé et le responsive mobile a des problèmes d'alignement. Ce prompt concerne UNIQUEMENT la homepage (`src/app/page.tsx` et les composants utilisés dedans).

---

## 1. CORRECTIONS CONTENU — Ce qu'il faut changer

### Règle générale sur le ton
- **NE PAS** mentionner "227+ endpoints API" — c'est technique et ça ne parle pas aux clients
- **NE PAS** mentionner des chiffres techniques internes (endpoints, routes API)
- **METTRE EN AVANT** les bénéfices concrets : gain de temps, qualité pédagogique, simplicité
- **TON** : professionnel, orienté résultat, accessible — pas de jargon dev

### Bandeau chiffres sous le hero
Remplacer :
```
✓ 39+ blocs interactifs
✓ 6 certifications supportées
✓ 227+ endpoints API          ← SUPPRIMER
✓ Export SCORM 1.2 & 2004
```

Par :
```
✓ 39+ blocs interactifs
✓ 6 certifications supportées
✓ 4 modèles IA disponibles
✓ Export SCORM 1.2 & 2004
```

### Section "Les 6 piliers"
Le contenu actuel est correct mais les descriptions peuvent être améliorées pour être plus orientées bénéfice :

1. **Génération IA complète** — "Uploadez un référentiel RNCP (TP, BTS, CAP, CQP, BPJEPS) et obtenez une formation structurée en quelques minutes. L'IA détecte automatiquement les blocs de compétences, modules et heures."

2. **Éditeur 39+ blocs interactifs** — "Créez du contenu pédagogique riche : quiz QCM, vrai/faux, drag & drop, vidéos, podcasts, mind maps, flashcards — dans un éditeur intuitif style Notion."

3. **Médias IA (NotebookLM)** — "Générez automatiquement des vidéos explicatives, podcasts audio, quiz adaptatifs et flashcards à partir de votre contenu pédagogique."

4. **Export SCORM universel** — "Exportez en SCORM 1.2 & 2004 et déployez sur n'importe quel LMS : Moodle, Canvas, Docebo, TalentLMS. Player moderne avec tracking complet."

5. **Pilotage & Planning** — "Planifiez vos sessions avec un calendrier drag & drop, assignez vos formateurs et exportez un planning Excel professionnel en 7 onglets."

6. **Multi-tenant & Enterprise** — "Gérez plusieurs organisations avec branding personnalisé, 5 niveaux de rôles et un suivi détaillé des coûts et de l'activité IA."

### Section chiffres clés
Remplacer "Endpoints API" par quelque chose de plus parlant :

```
39+ Blocs interactifs
6 Certifications supportées
227+ Endpoints API          ← REMPLACER
4 Modèles IA
7 Types de médias
2 Formats SCORM
```

Remplacer "227+ Endpoints API" par :
```
5 Rôles utilisateur
```

Ou :
```
10+ Thèmes de cours
```

### Section CTA finale
Le texte actuel est bien. Garder tel quel.

---

## 2. CORRECTIONS RESPONSIVE MOBILE

### Problème principal : les badges de durée dans "Comment ça marche"
Sur mobile, les badges `3 secondes`, `Instantané`, `2-5 minutes`, `Personnalisation`, `Déploiement` ne sont pas bien alignés avec le titre. Ils débordent ou passent à la ligne de manière moche.

**Correction :**
Changer le layout des titres + badges dans la section timeline. Au lieu de `flex items-center gap-2` (qui met tout sur une ligne), utiliser un layout qui s'adapte :

```tsx
// AVANT (problème sur mobile)
<div className="flex items-center gap-2 mb-1">
  <h3 className="text-lg font-semibold text-neutral-900">Uploadez votre référentiel</h3>
  <span className="rounded-full bg-amber-50 border border-amber-300 px-2.5 py-0.5 text-xs font-medium text-amber-800">3 secondes</span>
</div>

// APRÈS (responsive)
<div className="flex flex-wrap items-center gap-2 mb-1">
  <h3 className="text-lg font-semibold text-neutral-900">Uploadez votre référentiel</h3>
  <span className="rounded-full bg-amber-50 border border-amber-300 px-2.5 py-0.5 text-xs font-medium text-amber-800 whitespace-nowrap">3 secondes</span>
</div>
```

Ajouter `flex-wrap` pour que le badge passe en dessous sur petit écran, et `whitespace-nowrap` sur le badge pour éviter qu'il se coupe.

### Problème : section chiffres clés sur mobile
Les 6 chiffres en grille `grid-cols-2 sm:grid-cols-3 lg:grid-cols-6` avec `border-r` ne rendent pas bien sur mobile car les bordures droites créent des séparations incohérentes sur 2 colonnes.

**Correction :**
```tsx
// Remplacer border-r par un séparateur conditionnel
<div className="text-center lg:border-r border-gray-200 lg:last:border-0">
```
Ou supprimer les `border-r` et utiliser un `gap` plus grand + fond alterné pour séparer visuellement.

### Problème : hero sur mobile
Le screenshot dans le BrowserMockup prend trop de place sur mobile. La barre du navigateur (3 points) est bien mais le screenshot peut être trop petit pour être lisible.

**Correction :**
Sur mobile, ajouter un peu plus de padding et s'assurer que le mockup ne soit pas trop écrasé :
```tsx
<div className="mt-8 lg:mt-0">  // Ajouter un mt-8 sur mobile pour séparer du texte
```

### Problème : navbar mobile
Le burger menu existe mais vérifier que :
- Le menu s'ouvre/ferme bien (state toggle)
- Les liens sont visibles et cliquables
- Le dropdown "Fonctionnalités" fonctionne en mobile (accordéon ou liste simple)
- Le CTA "Demander une démo" est visible dans le menu mobile

### Problème : tableau "Avant/Après" sur mobile
La grille `grid-cols-3` est trop serrée sur mobile. Les textes sont coupés.

**Correction :**
```tsx
// Option 1 : Stack vertical sur très petit écran
<div className="grid grid-cols-1 sm:grid-cols-3 gap-4 px-5 py-4 items-center">

// Option 2 : Garder 3 colonnes mais réduire la taille du texte
<span className="text-xs sm:text-sm font-medium text-neutral-900">
```

Option recommandée : garder `grid-cols-3` mais utiliser `text-xs` sur mobile et `sm:text-sm` sur desktop pour les cellules du tableau.

---

## 3. AMÉLIORATIONS MINEURES

### Hero — Ordre des boutons CTA
Actuellement : "Voir comment ça marche" (secondaire) puis "Demander une démo" (primaire).
Sur desktop c'est OK, mais sur mobile (flex-col) le bouton primaire devrait être en premier.

**Correction :**
```tsx
<div className="mt-12 flex flex-col sm:flex-row items-center lg:items-start justify-center lg:justify-start gap-3">
  {/* Mobile : démo en premier, desktop : voir comment en premier */}
  <a className="w-full sm:w-auto ... order-2 sm:order-1 ..." href="#comment-ca-marche">Voir comment ça marche</a>
  <a className="w-full sm:w-auto ... order-1 sm:order-2 ..." href="/demo">Demander une démo</a>
</div>
```

### Section "Les 6 piliers" — Ajouter des liens "En savoir plus"
Chaque card devrait avoir un lien vers la page de fonctionnalité détaillée :
```tsx
<a href="/fonctionnalites/generation-ia" className="inline-flex items-center gap-1 text-sm font-semibold text-brand-600 hover:text-brand-700 mt-3">
  En savoir plus
  <ArrowRight className="size-4" />
</a>
```

Mapping :
- Génération IA → `/fonctionnalites/generation-ia`
- Éditeur → `/fonctionnalites/editeur`
- Médias IA → `/fonctionnalites/medias-ia`
- Export SCORM → `/fonctionnalites/export-scorm`
- Pilotage → `/fonctionnalites/pilotage-planning`
- Multi-tenant → `/fonctionnalites/multi-tenant`

### Footer — Copyright
Changer "© 2025" en "© 2026" (nous sommes en 2026).

---

## 4. VÉRIFICATION RESPONSIVE

Après les corrections, vérifier sur ces breakpoints :
- **320px** (iPhone SE) — tout doit être lisible et cliquable
- **375px** (iPhone standard) — badges alignés, tableau lisible
- **768px** (tablet) — layout intermédiaire correct
- **1024px** (desktop) — layout 2 colonnes hero, grille 3 colonnes piliers
- **1280px+** (large desktop) — max-width container respecté

---

## Ordre de travail

1. Corriger le contenu texte (supprimer "227+ endpoints API", améliorer descriptions)
2. Fixer le responsive des badges dans "Comment ça marche" (flex-wrap + whitespace-nowrap)
3. Fixer le responsive du tableau "Avant/Après" (text-xs sur mobile)
4. Fixer le responsive des chiffres clés (border conditionnel)
5. Ajouter les liens "En savoir plus" sur les 6 piliers
6. Corriger l'ordre des boutons CTA sur mobile
7. Mettre à jour le copyright à 2026
8. Tester le responsive sur différentes tailles
9. Build + commit + push
