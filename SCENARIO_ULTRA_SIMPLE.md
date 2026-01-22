# 🎬 VIDÉO NUPLY - SCÉNARIO ULTRA-SIMPLE (10 SECONDES)

## 🎯 CONCEPT

**Une seule idée claire :** Vous cherchez → L'IA trouve → Vous contactez

**3 écrans. 10 secondes. Zéro bug.**

---

## 📱 ÉCRAN 1 : LA RECHERCHE (0-3 sec, frames 0-90)

### Visuel

```
┌────────────────────────────────────┐
│                                    │
│         [Logo Nuply petit]         │
│                                    │
│                                    │
│     Vous cherchez un traiteur      │
│        pour votre mariage ?        │
│                                    │
│                                    │
└────────────────────────────────────┘
```

### Code

```typescript
// Background
background: "#FFFFFF"
aucune animation de fond (on garde simple)

// Logo en haut
Logo Nuply:
  height: 40px
  position: center-top, margin-top: 120px
  color: "#823F91"

// Texte principal
Text: "Vous cherchez un traiteur"
  fontSize: 56px
  fontWeight: 700
  color: "#2C1810"
  position: center, y: 420px
  letterSpacing: "-0.02em"

Text2: "pour votre mariage ?"
  fontSize: 56px
  fontWeight: 700
  color: "#2C1810"
  position: center, y: 490px

// Animation simple
Frames 0-20:
  - Logo fade in (opacity 0 → 1)

Frames 20-50:
  - Text1 fade in + translateY(20 → 0)
  - Spring gentle

Frames 50-80:
  - Text2 fade in + translateY(20 → 0)
  - Spring gentle

Frames 80-90:
  - Tout stable (on lit)
```

---

## 🎯 ÉCRAN 2 : LE MATCH PARFAIT (3-7 sec, frames 90-210)

### Visuel

```
┌────────────────────────────────────┐
│                                    │
│      ┌─────────────────────┐      │
│      │                     │      │
│      │   [Avatar 120px]    │      │
│      │                     │      │
│      │  Le Délice Oriental │      │
│      │  Traiteur Maghrébin │      │
│      │                     │      │
│      │  ⭐ 4.9 · 127 avis  │      │
│      │  📍 Paris 18ème     │      │
│      │  💰 45€/personne    │      │
│      │                     │      │
│      │      ┌──────┐       │      │
│      │      │ 98% │       │      │  ← Score
│      │      └──────┘       │      │
│      │                     │      │
│      └─────────────────────┘      │
│                                    │
└────────────────────────────────────┘
```

### Code

```typescript
// Transition depuis écran 1
Frames 90-100:
  - Texte écran 1 fade out (opacity 1 → 0)
  - Logo reste visible en haut

// Carte prestataire
Card:
  width: 600px
  height: 700px
  background: "#FFFFFF"
  border: "2px solid #E5E7EB"
  borderRadius: 24px
  padding: 48px
  position: center-center
  boxShadow: [
    "0 8px 24px rgba(0, 0, 0, 0.08)",
    "0 4px 12px rgba(0, 0, 0, 0.04)"
  ]

// Contenu de la carte
Avatar:
  size: 120px
  background: "linear-gradient(135deg, #823F91, #c081e3)"
  borderRadius: "50%"
  position: center-top de la card
  border: "4px solid white"
  boxShadow: "0 4px 12px rgba(130, 63, 145, 0.2)"

Name: "Le Délice Oriental"
  fontSize: 32px
  fontWeight: 700
  color: "#2C1810"
  marginTop: 24px

Type: "Traiteur Maghrébin"
  fontSize: 20px
  fontWeight: 500
  color: "#6B7280"
  marginTop: 8px

// Infos en colonnes
Rating: "⭐ 4.9 · 127 avis"
  fontSize: 18px
  color: "#2C1810"
  marginTop: 32px

Location: "📍 Paris 18ème"
  fontSize: 18px
  color: "#6B7280"
  marginTop: 12px

Price: "💰 45€/personne"
  fontSize: 18px
  color: "#823F91"
  fontWeight: 600
  marginTop: 12px

// Score en bas (GROS)
ScoreBadge:
  width: 160px
  height: 160px
  background: "linear-gradient(135deg, #10B981, #059669)"
  borderRadius: "50%"
  position: center-bottom de la card
  marginTop: 40px

ScoreText: "98%"
  fontSize: 64px
  fontWeight: 800
  color: "white"
  position: center de ScoreBadge

ScoreLabel: "Compatible"
  fontSize: 14px
  fontWeight: 600
  color: "white"
  opacity: 0.9
  position: under score

// Animation de la carte
Frames 100-130:
  - Card apparaît
  - Scale: 0.8 → 1.0
  - Opacity: 0 → 1
  - TranslateY: 50 → 0
  - Spring: { damping: 80, mass: 0.5 }

Frames 130-140:
  - Avatar fade in + scale

Frames 140-150:
  - Name + Type fade in

Frames 150-160:
  - Infos fade in (stagger 3 frames chaque)

Frames 160-190:
  - Score badge apparaît
  - Scale: 0 → 1.2 → 1.0 (bounce)
  - Score counter: 0% → 98% (animation compteur)

Frames 190-210:
  - Tout stable
  - Score badge pulse léger (scale 1.0 ↔ 1.05)
```

---

## 💬 ÉCRAN 3 : CALL TO ACTION (7-10 sec, frames 210-300)

### Visuel

```
┌────────────────────────────────────┐
│                                    │
│      [Carte reste visible         │
│       mais plus petite + blur]     │
│                                    │
│                                    │
│    ┌──────────────────────────┐   │
│    │  Contacter maintenant →  │   │  ← Bouton
│    └──────────────────────────┘   │
│                                    │
│      Réponse en moins de 2h        │
│                                    │
└────────────────────────────────────┘
```

### Code

```typescript
// Transition
Frames 210-225:
  - Card scale down: 1.0 → 0.85
  - Card blur: 0 → 4px
  - Card translateY: 0 → -80px (monte un peu)

// Bouton CTA
Button:
  width: 480px
  height: 72px
  background: "linear-gradient(135deg, #823F91, #c081e3)"
  borderRadius: 36px
  position: center, y: 640px

ButtonText: "Contacter maintenant →"
  fontSize: 24px
  fontWeight: 600
  color: "white"
  letterSpacing: "-0.01em"

ButtonShadow: [
  "0 12px 32px rgba(130, 63, 145, 0.3)",
  "0 6px 16px rgba(130, 63, 145, 0.2)",
  "inset 0 1px 0 rgba(255, 255, 255, 0.2)"
]

// Sous-texte
SubText: "Réponse en moins de 2h"
  fontSize: 16px
  color: "#6B7280"
  position: center, y: 730px

// Animation bouton
Frames 225-250:
  - Button apparaît
  - TranslateY: 40 → 0
  - Scale: 0.9 → 1.05 → 1.0
  - Opacity: 0 → 1
  - Spring bounce

Frames 250-265:
  - SubText fade in

Frames 265-300:
  - Button glow pulse
  - BoxShadow blur: 32px ↔ 40px
  - Opacity: 0.3 ↔ 0.4
  - Loop

  - Gradient animé
  - BackgroundPosition: 0% → 200%
  - Duration: 80 frames, loop
```

---

## 🎬 TIMELINE COMPLÈTE

```
0:00  (0)    - Logo fade in
0:01  (20)   - "Vous cherchez un traiteur"
0:02  (50)   - "pour votre mariage ?"
0:03  (90)   - Transition
0:03  (100)  - Carte prestataire apparaît
0:04  (130)  - Avatar + nom
0:05  (150)  - Infos détaillées
0:05  (160)  - Score 98% s'anime
0:07  (210)  - Carte scale down
0:07  (225)  - Bouton CTA apparaît
0:08  (250)  - Sous-texte
0:10  (300)  - FIN
```

**Total : 10 secondes (300 frames)**

---

## 📁 STRUCTURE CODE ULTRA-SIMPLE

```
/src/NuplySimple/
├── NuplySimple.tsx              // Composition principale
├── constants.ts                 // Couleurs
├── Scene1_Question.tsx          // Écran 1 : Question
├── Scene2_Match.tsx             // Écran 2 : Carte
└── Scene3_CTA.tsx               // Écran 3 : Bouton
```

### Composition principale

```typescript
// NuplySimple.tsx
import { AbsoluteFill, useCurrentFrame } from 'remotion';
import { Scene1_Question } from './Scene1_Question';
import { Scene2_Match } from './Scene2_Match';
import { Scene3_CTA } from './Scene3_CTA';

export const NuplySimple = () => {
  const frame = useCurrentFrame();

  return (
    <AbsoluteFill style={{ backgroundColor: '#FFFFFF' }}>
      {/* Logo toujours visible */}
      {frame >= 0 && <Logo frame={frame} />}

      {/* Scène 1: Question (0-90) */}
      {frame < 100 && <Scene1_Question frame={frame} />}

      {/* Scène 2: Match (100-210) */}
      {frame >= 100 && <Scene2_Match frame={frame} />}

      {/* Scène 3: CTA (210-300) */}
      {frame >= 210 && <Scene3_CTA frame={frame} />}
    </AbsoluteFill>
  );
};
```

---

## ✅ POURQUOI CE SCÉNARIO EST PARFAIT

### ✅ ULTRA-SIMPLE
- 3 écrans seulement
- Pas de typing effect compliqué
- Pas de curseur souris
- Pas de zoom caméra
- Juste des fade in/out et spring animations

### ✅ ZÉRO BUG
- Chaque scène est indépendante
- Timings clairs et fixes
- Pas de dépendances complexes
- Animations Remotion standard

### ✅ EFFICACE
- Message clair en 10 secondes
- Met en valeur LE meilleur match (pas 3)
- Score 98% bien visible
- CTA impossible à rater

### ✅ PREMIUM
- Animations spring smooth
- Shadows et gradients élégants
- Typographie claire (Geist)
- Couleurs Nuply respectées

---

## 🎨 COULEURS (constants.ts)

```typescript
export const COLORS = {
  // Brand
  PRIMARY: "#823F91",
  PRIMARY_LIGHT: "#c081e3",
  PRIMARY_BG: "#E8D4EF",

  // Backgrounds
  WHITE: "#FFFFFF",
  GRAY_50: "#F9FAFB",

  // Textes
  TEXT_DARK: "#2C1810",
  TEXT_GRAY: "#6B7280",

  // UI
  BORDER: "#E5E7EB",
  SUCCESS: "#10B981",
  SUCCESS_DARK: "#059669",
};
```

---

## 🚀 INSTRUCTIONS POUR CURSOR

```
Crée une vidéo Remotion de 10 secondes (300 frames) avec ce scénario:

ÉCRAN 1 (0-90 frames):
- Logo Nuply en haut
- Texte centré: "Vous cherchez un traiteur pour votre mariage ?"
- Animations fade in simples

ÉCRAN 2 (100-210 frames):
- UNE SEULE carte prestataire au centre
- Nom: "Le Délice Oriental"
- Infos: rating, location, prix
- Score 98% en cercle vert qui s'anime (counter 0→98%)
- Animations spring smooth

ÉCRAN 3 (210-300 frames):
- Carte devient plus petite et blur
- Bouton gradient violet: "Contacter maintenant →"
- Sous-texte: "Réponse en moins de 2h"
- Glow pulse sur le bouton

Couleurs: #823F91 (violet), #FFFFFF (blanc), #10B981 (vert)
Font: Geist Sans
Résolution: 1920×1080, 30fps

GARDE ÇA SIMPLE. Pas de typing effect, pas de curseur, pas de zoom.
Juste des fade in/out et spring animations.
```

---

**C'EST TOUT. SIMPLE. EFFICACE. SANS BUG. 🎯**

Tu veux que je crée les fichiers directement ou tu préfères tester ce prompt dans Cursor ?
