# 🎬 PROMPT PREMIUM CURSOR - VIDÉO MATCHING IA NUPLY

## 🎯 MISSION

Crée une vidéo motion design **ULTRA-PREMIUM** de 15-20 secondes (450-600 frames à 30fps) pour le **Matching IA de Nuply**.

La vidéo doit être au niveau des meilleures animations de **Figma, Revolut, Qonto, Replit, Lovable** :
- Transitions fluides et élégantes
- Animations spring naturelles
- Focus dramatique sur les éléments (zoom centré style Revolut)
- Design épuré et premium
- Pas de temps mort, chaque frame compte

---

## 🎨 DESIGN SYSTEM NUPLY - À RESPECTER RELIGIEUSEMENT

### Couleurs EXACTES (depuis `/home/user/nuply-site`)

```typescript
// Violet Nuply (identité de marque)
PRIMARY = "#823F91"           // Violet principal - boutons, highlights, icônes
PRIMARY_LIGHT = "#c081e3"     // Violet clair - gradients, accents
PRIMARY_HOVER = "#6D3478"     // Violet foncé - hover states
BADGE_NEW = "#DD61FF"         // Rose violet - badge "Nouveau"

// Backgrounds Beige Premium
BG_MAIN = "#FBF8F3"          // Beige principal (fond général)
BG_SECTION = "#F5F0E8"       // Beige section alternée
BG_CARD = "#FFFFFF"          // Blanc pur (cartes)
BG_ACCENT = "#E8D4EF"        // Violet très clair (highlights)

// Textes
TEXT_PRIMARY = "#2C1810"     // Beige 900 - titres
TEXT_SECONDARY = "#374151"   // Gris - body text
TEXT_MUTED = "#6B7280"       // Gris clair - métadonnées

// Borders & UI
BORDER = "#E5E7EB"           // Gris clair
BORDER_LIGHT = "#F3F4F6"     // Gris ultra-clair
```

### Typographie

```typescript
FONT_FAMILY = "Geist Sans, SF Pro Text, Helvetica, Arial, sans-serif"

// Hiérarchie (Geist)
H1: 64-80px, font-weight: 800 (extrabold), letter-spacing: -0.02em
H2: 48-60px, font-weight: 700 (bold), letter-spacing: -0.01em
H3: 32-40px, font-weight: 600 (semibold)
Body Large: 20-24px, font-weight: 400, line-height: 1.7
Body: 16-18px, font-weight: 400, line-height: 1.7
Small: 14px, font-weight: 400
```

### Spacing & Layout

```typescript
// Résolution vidéo
WIDTH = 1920px
HEIGHT = 1080px
FPS = 30

// Spacing système (multiples de 8)
XS = 8px
SM = 12px
MD = 16px
LG = 24px
XL = 32px
2XL = 48px
3XL = 64px

// Border Radius
RADIUS_SM = 6px
RADIUS_MD = 8px
RADIUS_LG = 12px
RADIUS_XL = 16px        // Standard pour cards et buttons
RADIUS_PILL = 48px      // Boutons pill-shape
```

### Shadows (depuis globals.css)

```typescript
// Ombres progressives Nuply
SHADOW_SOFT = [
  '0 1px 2px hsl(220 30% 15% / 0.02)',
  '0 2px 4px hsl(220 30% 15% / 0.02)',
  '0 4px 8px hsl(220 30% 15% / 0.02)'
]

SHADOW_ELEVATED = [
  '0 2px 4px hsl(220 30% 15% / 0.02)',
  '0 4px 8px hsl(220 30% 15% / 0.03)',
  '0 8px 16px hsl(220 30% 15% / 0.03)',
  '0 16px 32px hsl(220 30% 15% / 0.02)'
]

SHADOW_FLOAT = [
  '0 4px 6px hsl(220 30% 15% / 0.03)',
  '0 10px 20px hsl(220 30% 15% / 0.04)',
  '0 20px 40px hsl(220 30% 15% / 0.04)'
]

SHADOW_GLOW = '0 8px 32px hsl(250 65% 55% / 0.2)'  // Glow violet pour CTA
```

---

## 🎬 STORYBOARD DÉTAILLÉ (Frame-by-Frame)

### **SCÈNE 1 : INTRO - LE PROBLÈME** (Frames 0-90, 3 sec)

**Concept :** Montrer rapidement le problème : trouver des prestataires c'est compliqué.

**Visuel :**
```typescript
Frame 0-30 (1 sec):
  Background: #FBF8F3 (beige Nuply)

  // Titre apparaît au centre
  Text: "Comment trouver vos prestataires ?"
  Font: Geist Sans, 48px, bold, #2C1810
  Animation:
    - Fade in + scale 0.9 → 1.0
    - Spring: { damping: 80, mass: 0.5 }

  // Sous-texte
  SubText: "247 photographes, DJ, traiteurs..."
  Font: 24px, #6B7280
  Position: center, y+60px
  Animation: Fade in (delay 10 frames)

Frame 30-60 (1 sec):
  // Grille chaotique de cartes prestataires floues
  Grid: 3x2 mini-cards (200x150px chaque)
  Cards:
    - Background: white avec borders #E5E7EB
    - Blur: 4px (effet "trop d'options")
    - Opacity: 0.6
    - Animation: Apparition staggered (delay 3 frames entre chaque)
    - Légère rotation aléatoire (-2° à +2°)

  // Point d'interrogation géant au centre
  Icon: "?" (lucide-react HelpCircle)
  Size: 120px
  Color: #823F91
  Animation: Scale pulse 0.95 ↔ 1.05 (loop)

Frame 60-90 (1 sec):
  // Transition : tout blur out
  All elements: blur(0px) → blur(20px)
  Opacity: 1 → 0

  // Logo Nuply slide in depuis le top
  Logo: SVG depuis /public/images/logo.svg
  Position: top-center, y: 100px
  Size: 60px height
  Animation:
    - TranslateY: -100 → 0
    - Spring bounce

  // Badge "IA" apparaît à côté du logo
  Badge: "✨ IA"
  Background: gradient #823F91 → #c081e3
  Border-radius: 24px
  Padding: 8px 16px
  Font: 16px, semibold, white
  Animation: Scale 0 → 1.1 → 1.0 (overshoot)
```

---

### **SCÈNE 2 : SÉLECTION IA** (Frames 90-240, 5 sec)

**Concept :** L'IA analyse et sélectionne les 3 meilleurs prestataires. Animation de scan + cartes qui apparaissent.

**Layout :**
```typescript
// 3 cartes côte à côte (style DemandeCard.tsx)
Card dimensions: 480px × 620px
Spacing: 40px entre les cartes
Position: Centrées verticalement et horizontalement
Background: #FFFFFF
Border: 1px solid #E5E7EB
Border-radius: 16px (xl)
Shadow: SHADOW_ELEVATED
```

**Contenu de chaque carte (réel, comme dans Nuply) :**
```typescript
CARD_1 = {
  name: "Sophie Martin",
  role: "Photographe Mariage",
  culture: "🇫🇷 Maghrébin, Européen",
  location: "Paris (75)",
  rating: 4.9,
  reviews: 127,
  price: "À partir de 1 200€",
  experience: "8 ans • 200+ mariages",
  badge: "Nouveau",
  avatar: Gradient circle (#823F91 → #c081e3)
}

CARD_2 = {
  name: "Karim Benali",
  role: "DJ Événementiel",
  culture: "🇫🇷 Maghrébin, Mixte",
  location: "Lyon (69)",
  rating: 4.8,
  reviews: 89,
  price: "À partir de 800€",
  experience: "5 ans • 150+ événements",
  badge: null,
  avatar: Gradient circle (#823F91 → #c081e3)
}

CARD_3 = {
  name: "Fatima Zahra",
  role: "Neggafa Traditionnelle",
  culture: "🇲🇦 Maghrébin",
  location: "Marseille (13)",
  rating: 5.0,
  reviews: 64,
  price: "À partir de 600€",
  experience: "12 ans • Spécialiste traditions",
  badge: null,
  avatar: Gradient circle (#823F91 → #c081e3)
}
```

**Animation détaillée :**
```typescript
Frame 90-120 (1 sec):
  // Texte intro de la scène
  Text: "L'IA analyse vos critères"
  Font: 40px, semibold, #2C1810
  Position: top-center, y: 150px
  Animation: Fade in + translateY(20 → 0)

  // Indicateur de chargement IA
  Loader: 3 dots pulsing
  Color: #823F91
  Animation: Scale 0.8 ↔ 1.2 (stagger 5 frames)

Frame 120-150 (1 sec):
  // Texte disparaît
  Fade out + translateY(0 → -20)

  // CARTE 1 apparaît
  Card 1:
    Position: x: 280, y: 230 (gauche)
    Animation:
      - Opacity: 0 → 1
      - TranslateX: -100 → 0
      - Scale: 0.9 → 1.0
      - Spring: { damping: 100, stiffness: 200 }

    // Avatar
    Circle gradient border (4px)
    Border: conic-gradient from #823F91 to #c081e3
    Rotation: 0 → 360° (2 sec loop)

    // Badge "Nouveau"
    Position: top-right corner, -8px, -8px
    Background: #DD61FF
    Color: white
    Border-radius: 12px
    Padding: 4px 12px
    Font: 12px, semibold
    Animation: Scale 0 → 1.1 → 1.0 (bounce)

    // Éléments de carte apparaissent séquentiellement
    Name: Fade in (delay 5 frames)
    Role: Fade in (delay 10 frames)
    Icons + infos: Fade in staggered (delay 3 frames chaque)

Frame 150-180 (1 sec):
  // CARTE 2 apparaît (même pattern)
  Card 2:
    Position: x: 720, y: 230 (centre)
    Animation identique avec delay de 30 frames

Frame 180-210 (1 sec):
  // CARTE 3 apparaît
  Card 3:
    Position: x: 1160, y: 230 (droite)
    Animation identique avec delay de 60 frames

Frame 210-240 (1 sec):
  // EFFET SCAN IA
  Scan line: Ligne verticale violette
  Width: 3px
  Height: 100vh
  Background: linear-gradient(90deg,
    transparent 0%,
    #823F91 50%,
    transparent 100%
  )
  Box-shadow: 0 0 40px #823F91
  Animation: TranslateX(0 → 1920px) en 30 frames

  // Au passage du scan, checkmarks apparaissent
  Checkmark: Icône Check (lucide-react)
  Color: #10B981 (vert)
  Size: 32px
  Position: top-right de chaque carte
  Background: white avec shadow
  Border-radius: 50%
  Animation: Scale 0 → 1.2 → 1.0 (bounce)

  // Carte 1 focus légèrement
  Card 1:
    Scale: 1.0 → 1.03
    Shadow: SHADOW_ELEVATED → SHADOW_FLOAT
    Border: #E5E7EB → #823F91 (2px)
```

---

### **SCÈNE 3 : CONVERSATION MESSAGES (HERO SCENE)** (Frames 240-480, 8 sec)

**Concept :** ⭐ **LA SCÈNE CENTRALE** ⭐
Zoom dramatique sur une interface de messagerie style Revolut/Qonto. Messages qui apparaissent avec typing effect, centrés et animés.

**Layout :**
```typescript
// Container messagerie (style /app/couple/messagerie/page.tsx)
Container:
  Width: 1400px
  Height: 900px
  Position: center-center (260px, 90px)
  Background: white
  Border: 1px solid #E5E7EB
  Border-radius: 24px
  Box-shadow: SHADOW_FLOAT
  Padding: 32px
```

**Header de la conversation :**
```typescript
Header:
  Height: 80px
  Border-bottom: 1px solid #E5E7EB

  // Avatar + nom prestataire
  Avatar:
    Size: 56px
    Background: gradient #823F91 → #c081e3
    Border: 3px solid white
    Shadow: SHADOW_SOFT

  Name: "Sophie Martin"
  Font: 20px, semibold, #2C1810

  Status: "En ligne"
  Font: 14px, #10B981 (vert)
  Dot: 8px circle, #10B981, pulse animation
```

**Messages (style exact depuis messagerie/page.tsx) :**
```typescript
MESSAGES = [
  {
    from: "user",
    content: "Bonjour Sophie, je cherche un photographe pour mon mariage le 15 juin à Paris",
    timestamp: "14:23",
  },
  {
    from: "ai-typing",  // Typing indicator
    content: "...",
  },
  {
    from: "provider",
    content: "Bonjour ! 😊 Je serais ravie d'immortaliser votre journée. J'ai photographié plus de 200 mariages, notamment plusieurs mariages maghrébins.",
    timestamp: "14:23",
  },
  {
    from: "user",
    content: "Parfait ! Quel est votre tarif ?",
    timestamp: "14:24",
  },
  {
    from: "provider",
    content: "À partir de 1 200€ pour 8h de couverture complète + album premium 📸",
    timestamp: "14:24",
    hasCard: true,  // Card avec détails
  },
]
```

**Animation ULTRA-DÉTAILLÉE :**
```typescript
Frame 240-270 (1 sec):
  // ZOOM IN DRAMATIQUE
  // Carte 1 (Sophie) grossit et devient le container de chat
  Card 1:
    Scale: 1.03 → 2.5
    TranslateX: 280 → 960 (center)
    TranslateY: 230 → 540 (center)
    Border-radius: 16px → 24px

  // Autres cartes disparaissent
  Cards 2, 3:
    Opacity: 1 → 0
    Blur: 0 → 10px

  // Container chat apparaît
  Chat Container:
    Opacity: 0 → 1
    Blur: 10px → 0px
    Spring smooth

Frame 270-300 (1 sec):
  // Header conversation slide in
  Header:
    TranslateY: -80 → 0
    Spring: { damping: 80 }

  Avatar rotation: 0 → 360° (smooth)
  Status dot pulse: scale 0.9 ↔ 1.1 (loop)

Frame 300-330 (1 sec):
  // MESSAGE 1 - User (couple)
  Bubble:
    Position: right side, max-width: 70%
    Background: #823F91
    Color: white
    Border-radius: 16px 16px 4px 16px (style chat)
    Padding: 12px 16px
    Box-shadow: SHADOW_SOFT

  Animation:
    - TranslateX: 100 → 0
    - Scale: 0.95 → 1.0
    - Opacity: 0 → 1
    - Spring: { damping: 100 }

  // Typing effect sur le texte
  Text: "Bonjour Sophie, je cherche un photographe..."
  Animation: Caractères apparaissent 1 par 1
  Speed: 4 caractères/frame

  Timestamp:
    "14:23"
    Font: 12px, white opacity 70%
    Position: bottom-right de la bubble
    Fade in après texte complet (delay 5 frames)

Frame 330-360 (1 sec):
  // TYPING INDICATOR (pendant que l'IA "réfléchit")
  Indicator:
    Position: left side
    Background: #E8D4EF (violet très clair)
    Border-radius: 24px
    Padding: 12px 16px

  // 3 dots qui bounce
  Dots: "•••"
  Animation: Chaque dot scale 0.8 ↔ 1.2
  Stagger: 5 frames entre chaque dot
  Color: #823F91

Frame 360-400 (1.3 sec):
  // Typing indicator disparaît
  Scale: 1.0 → 0

  // MESSAGE 2 - Provider (Sophie)
  Bubble:
    Position: left side, max-width: 70%
    Background: #E8D4EF (violet clair Nuply)
    Color: #2C1810
    Border-radius: 16px 16px 16px 4px

  Text: "Bonjour ! 😊 Je serais ravie d'immortaliser..."
  Typing speed: 5 caractères/frame (plus rapide)

  // Mots-clés surlignés
  "200 mariages" → color: #823F91, font-weight: 600
  "maghrébins" → color: #823F91, font-weight: 600

  Timestamp: "14:23", #6B7280

Frame 400-420 (0.7 sec):
  // MESSAGE 3 - User court
  Bubble: (style Message 1)
  Text: "Parfait ! Quel est votre tarif ?"
  Animation: Faster (20 frames total)

Frame 420-480 (2 sec):
  // MESSAGE 4 - Provider avec CARD
  Bubble: (style Message 2)
  Text: "À partir de 1 200€ pour 8h..."

  // CARD ENRICHIE apparaît DANS le message
  Card:
    Width: 100% de la bubble
    Height: 220px
    Background: white
    Border: 1px solid #E5E7EB
    Border-radius: 12px
    Margin-top: 12px
    Box-shadow: SHADOW_SOFT

  Card Content:
    // Avatar
    Avatar: 80px circle, gradient border rotating

    // Info
    Name: "Sophie Martin"
    Font: 18px, semibold, #2C1810

    Role: "Photographe Mariage"
    Font: 14px, #6B7280

    // Rating stars
    Stars: ★★★★★ (4.9/5)
    Color: #FCD34D (jaune doré)
    Animation: Apparition staggered (3 frames delay chaque)

    // Reviews
    Text: "127 avis"
    Font: 12px, #6B7280

    // Price counter animation
    Price: "1 200€"
    Animation: Counter de 0 → 1200 en 20 frames
    Font: 24px, semibold, #823F91

    // Badge cultures
    Badges: ["Maghrébin", "Européen"]
    Background: #E8D4EF
    Color: #823F91
    Border-radius: 8px
    Padding: 4px 8px
    Font: 12px
    Animation: Slide in from bottom, staggered

  // Sparkles autour de la card
  Sparkles: 4-5 small stars (lucide-react Sparkles)
  Color: #823F91
  Size: 16px
  Position: Coins de la card
  Animation: Fade in + rotate + scale pulse
```

---

### **SCÈNE 4 : CALL-TO-ACTION FINALE** (Frames 480-600, 4 sec)

**Concept :** Le bouton "Contacter" apparaît de façon dramatique avec glow effect et invitation claire.

**Animation :**
```typescript
Frame 480-510 (1 sec):
  // Chat container scale down + blur
  Chat Container:
    Scale: 1.0 → 0.9
    Blur: 0 → 8px
    Opacity: 1 → 0.7

  // Overlay sombre
  Overlay:
    Background: rgba(0, 0, 0, 0.4)
    Opacity: 0 → 1
    Backdrop-filter: blur(4px)

Frame 510-550 (1.3 sec):
  // BOUTON CTA APPARAÎT AU CENTRE
  Button:
    Width: 480px
    Height: 72px
    Position: center-center
    Background: linear-gradient(135deg, #823F91 0%, #c081e3 100%)
    Border-radius: 48px (pill)
    Box-shadow: SHADOW_GLOW + pulse

  Text: "Contacter Sophie →"
  Font: Geist Sans, 28px, semibold, white

  Animation:
    - Scale: 0.5 → 1.2 → 1.0 (bounce overshoot)
    - Spring: { damping: 50, mass: 0.8 }
    - Rotation: -5° → 0°

  // Glow effect pulsing
  Box-shadow animation:
    0 0 0 0 rgba(130, 63, 145, 0.4)
    → 0 0 60px 20px rgba(130, 63, 145, 0.6)
    → 0 0 0 0 rgba(130, 63, 145, 0.4)
  Duration: 60 frames (2 sec loop)

  // Flèche animation
  Arrow "→":
    TranslateX: 0 → 8px → 0
    Loop: 30 frames

  // Gradient background animé
  Background-position: 0% → 200% (loop infini)

  // Shine effect traverse le bouton
  Shine:
    Width: 60px
    Height: 100%
    Background: linear-gradient(90deg,
      transparent 0%,
      rgba(255,255,255,0.3) 50%,
      transparent 100%
    )
    Animation: TranslateX(-100% → 200%)
    Duration: 60 frames

Frame 550-575 (0.8 sec):
  // Sous-texte apparaît
  SubText: "Réponse en moyenne sous 2h ⚡"
  Font: 18px, #F3F4F6 (clair sur fond sombre)
  Position: y + 100px du bouton

  Animation:
    - Fade in
    - TranslateY: 20 → 0
    - Spring smooth

  // Icône éclair pulse
  ⚡ Scale: 0.9 ↔ 1.1 (loop)

Frame 575-600 (0.8 sec):
  // Logo Nuply + tagline réapparaissent en bas
  Logo:
    Position: bottom-center, y: 920px
    Size: 40px height
    Opacity: 0 → 1

  Tagline: "NUPLY - Le mariage moderne"
  Font: 16px, #F3F4F6
  Position: bottom-center, y: 980px
  Letter-spacing: 2px (uppercase)

  // Fade out global vers blanc
  Overlay white:
    Opacity: 0 → 1
    Duration: 25 frames (dernières frames)
```

---

## 💎 CONFIGURATIONS ANIMATIONS REMOTION

### Spring Configs (créer fichier `animations/springConfigs.ts`)

```typescript
export const SPRING_CONFIGS = {
  // Doux et naturel (textes, fades)
  gentle: {
    damping: 100,
    mass: 0.5,
    stiffness: 100
  },

  // Dynamique (cartes, éléments UI)
  snappy: {
    damping: 80,
    mass: 0.3,
    stiffness: 200
  },

  // Bounce expressif (CTA, badges)
  bouncy: {
    damping: 50,
    mass: 0.8,
    stiffness: 150,
    overshootClamping: false
  },

  // Ultra-smooth (zooms, transitions)
  smooth: {
    damping: 200,
    mass: 1,
    stiffness: 80
  },

  // Elastic (hover effects)
  elastic: {
    damping: 20,
    mass: 0.6,
    stiffness: 100
  },
};
```

### Easing Functions

```typescript
export const easings = {
  // Transitions smooth Nuply
  nuplySmooth: [0.4, 0, 0.2, 1] as const,

  // Bounce back (boutons)
  nuplyBounce: [0.34, 1.56, 0.64, 1] as const,

  // Expo out (apparitions)
  nuplyExpo: [0.19, 1, 0.22, 1] as const,
};
```

---

## 📁 STRUCTURE FICHIERS À CRÉER

```
/src/MatchingIA/
├── MatchingIA.tsx                    // Composition principale
├── constants.ts                      // Couleurs Nuply + constantes
├── schemas.ts                        // Zod schemas pour props
├── scenes/
│   ├── Scene1_Intro.tsx             // Frames 0-90
│   ├── Scene2_Selection.tsx          // Frames 90-240
│   ├── Scene3_Messages.tsx           // Frames 240-480 (HERO)
│   └── Scene4_CTA.tsx                // Frames 480-600
├── components/
│   ├── ProviderCard.tsx              // Carte prestataire (style DemandeCard)
│   ├── MessageBubble.tsx             // Bulle de message
│   ├── TypingIndicator.tsx           // "..." animé
│   ├── CTAButton.tsx                 // Bouton final avec glow
│   └── ChatHeader.tsx                // Header conversation
└── animations/
    ├── springConfigs.ts              // Configs spring
    └── easings.ts                    // Courbes d'animation
```

### Enregistrer la composition dans `/src/Root.tsx`

```typescript
import { MatchingIA } from "./MatchingIA/MatchingIA";
import { matchingIASchema } from "./MatchingIA/schemas";

// Dans <Remotion.Root>:
<Composition
  id="MatchingIA"
  component={MatchingIA}
  durationInFrames={600}
  fps={30}
  width={1920}
  height={1080}
  schema={matchingIASchema}
  defaultProps={{
    // Props dynamiques si besoin
  }}
/>
```

---

## 🎨 COMPOSANTS À DÉVELOPPER

### 1. ProviderCard.tsx (style DemandeCard Nuply)

```typescript
interface ProviderCardProps {
  name: string;
  role: string;
  culture: string;
  location: string;
  rating: number;
  reviews: number;
  price: string;
  experience: string;
  badge?: string | null;
  frame: number;  // Pour animations
}

// Rendu exact comme dans /components/prestataire/demandes/DemandeCard.tsx
// Background: white
// Border: 1px solid #E5E7EB
// Border-radius: 16px
// Shadow: SHADOW_ELEVATED
// Padding: 24px
// Icons: lucide-react (MapPin, Star, Euro, Calendar)
```

### 2. MessageBubble.tsx (style messagerie Nuply)

```typescript
interface MessageBubbleProps {
  from: "user" | "provider";
  content: string;
  timestamp: string;
  frame: number;
  startFrame: number;
  hasCard?: boolean;
  cardData?: ProviderCardData;
}

// User (couple):
//   Background: #823F91
//   Color: white
//   Border-radius: 16px 16px 4px 16px
//   Position: flex-end (right)

// Provider:
//   Background: #E8D4EF
//   Color: #2C1810
//   Border-radius: 16px 16px 16px 4px
//   Position: flex-start (left)

// Timestamp: 12px, opacity 70%
```

### 3. TypingIndicator.tsx

```typescript
// 3 dots qui bounce
// Background: #E8D4EF
// Border-radius: 24px
// Padding: 12px 16px
// Dots animation: translateY oscillation staggered
```

### 4. CTAButton.tsx

```typescript
// Gradient background animé
// Glow shadow pulsing
// Arrow translateX loop
// Shine effect crossing
// Spring bounce entrance
```

---

## ✅ CHECKLIST QUALITÉ

Avant de considérer la vidéo terminée :

**Design Nuply respecté :**
- [ ] Couleurs EXACTES : #823F91, #E8D4EF, #FBF8F3
- [ ] Font Geist Sans partout
- [ ] Border-radius: 16px (cards), 24px (containers), 48px (buttons)
- [ ] Shadows Nuply (SHADOW_SOFT, SHADOW_ELEVATED)
- [ ] Texture grain subtile en arrière-plan (optionnel)

**Animations premium :**
- [ ] Toutes les animations utilisent `spring()` ou `interpolate()`
- [ ] Scène 3 (Messages) dure 8 secondes minimum (c'est le moment clé)
- [ ] Typing effects fluides (4-5 chars/frame)
- [ ] Glow effects sur CTA
- [ ] Pas de cuts brutaux, transitions fluides

**Technique :**
- [ ] 30 FPS constant
- [ ] 1920×1080
- [ ] Aucun élément hors cadre
- [ ] TypeScript strict sans erreurs
- [ ] Code formatté Prettier

**Storytelling :**
- [ ] Progression claire : Problème → IA → Conversation → Action
- [ ] Messages réalistes (pas de lorem ipsum)
- [ ] CTA impossible à rater
- [ ] Branding Nuply visible mais élégant

---

## 🚀 ORDRE D'EXÉCUTION RECOMMANDÉ

1. **Setup** (10 min)
   - Créer dossier `/src/MatchingIA/`
   - Copier couleurs dans `constants.ts`
   - Créer `schemas.ts`
   - Enregistrer composition

2. **Composants** (45 min)
   - `ProviderCard.tsx` (style DemandeCard)
   - `MessageBubble.tsx`
   - `TypingIndicator.tsx`
   - `CTAButton.tsx`

3. **Scènes** (2-3 heures)
   - Scene 1 : Intro (30 min)
   - Scene 2 : Sélection (1h)
   - Scene 3 : Messages (1.5h - LA SCÈNE CRITIQUE)
   - Scene 4 : CTA (30 min)

4. **Polish** (30 min)
   - Transitions entre scènes
   - Timings adjustments
   - Shadows & effects
   - Export test

---

## 🎯 RÉSULTAT ATTENDU

Une vidéo de **15-20 secondes** qui :
- Montre clairement le problème (trop de choix)
- Démontre la puissance de l'IA (sélection instantanée)
- Met en avant la conversation naturelle (ZOOM CENTRÉ style Revolut)
- Appelle à l'action de façon irrésistible

**Niveau de qualité :** Figma Config 2023 / Revolut App Promo / Qonto Product Video

**Style :** Premium, épuré, moderne, pas corporate. Chaque frame doit être parfaite.

---

**GO MAKE THE BEST MOTION DESIGN VIDEO EVER! 🚀✨**
