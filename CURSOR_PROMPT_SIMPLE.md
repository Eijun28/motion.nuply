# 🎬 PROMPT CURSOR - VIDÉO MATCHING NUPLY (VERSION SIMPLE)

## 🎯 MISSION

Crée une vidéo Remotion de **15 secondes** (450 frames à 30fps) qui montre le parcours utilisateur du matching Nuply de façon ultra-simple et claire.

---

## 🎨 DESIGN SYSTEM NUPLY

### Couleurs
```typescript
PRIMARY = "#823F91"           // Violet Nuply
PRIMARY_LIGHT = "#E8D4EF"     // Violet très clair
BG_WHITE = "#FFFFFF"          // Fond blanc
BG_BEIGE = "#FBF8F3"          // Beige Nuply
TEXT_DARK = "#2C1810"         // Texte principal
TEXT_GRAY = "#6B7280"         // Texte secondaire
BORDER = "#E5E7EB"            // Bordures
SUCCESS = "#10B981"           // Vert (score)
```

### Typographie
```typescript
FONT = "Geist Sans, SF Pro Text, Helvetica, Arial, sans-serif"
```

### Dimensions
```typescript
WIDTH = 1920px
HEIGHT = 1080px
FPS = 30
DURATION = 450 frames (15 secondes)
```

---

## 📝 SCÉNARIO (7 ÉTAPES SIMPLES)

### ÉTAPE 1 : Interface de chat (Frames 0-60, 2 sec)

**Visuel :**
```
Fond: Blanc pur (#FFFFFF)
Centre écran: Interface de chat minimaliste

┌─────────────────────────────────────┐
│                                     │
│  [Input avec placeholder]           │
│                                     │
│  [Bouton Envoyer violet]            │
│                                     │
└─────────────────────────────────────┘
```

**Code :**
```typescript
// Input
Width: 800px
Height: 60px
Background: white
Border: 2px solid #E5E7EB
Border-radius: 16px
Placeholder: "Décrivez votre besoin..."
Font: 18px

// Texte qui apparaît caractère par caractère
Text: "Je cherche un traiteur pour 80 personnes à Paris"
Animation: Typing effect (3 caractères/frame)

// Bouton
Width: 180px
Height: 60px
Background: #823F91
Color: white
Text: "Envoyer →"
Border-radius: 16px
Position: À droite de l'input
```

**Animation :**
```typescript
Frame 0-30:
  - Interface fade in (opacity 0 → 1)
  - Input apparaît avec spring

Frame 30-60:
  - Texte typing effect dans l'input
  - Cursor blink dans l'input
```

---

### ÉTAPE 2 : Clic souris (Frames 60-90, 1 sec)

**Visuel :**
```
Zoom sur le bouton "Envoyer"
Curseur souris apparaît et clique
```

**Code :**
```typescript
// Curseur souris
Component: <div> styled comme curseur macOS
Width: 24px
Height: 24px
Background: Blanc avec bordure noire
Shadow: 0 2px 8px rgba(0,0,0,0.2)

// Animation
Frame 60-75:
  - Curseur apparaît en haut à droite (opacity 0 → 1)
  - Se déplace vers le bouton (translateX, translateY)
  - Courbe: ease-out

Frame 75-85:
  - Curseur sur le bouton
  - Bouton hover state (background: #6D3478)
  - Bouton scale: 1.0 → 0.95 (click effect)

Frame 85-90:
  - Bouton scale: 0.95 → 1.0
  - Ripple effect depuis le centre du bouton
```

---

### ÉTAPE 3 : Chargement IA (Frames 90-150, 2 sec)

**Visuel :**
```
┌─────────────────────────────────────┐
│                                     │
│    [Spinner violet animé]           │
│                                     │
│  "Votre assistant vous trouve les   │
│   meilleurs prestataires"           │
│                                     │
└─────────────────────────────────────┘
```

**Code :**
```typescript
// Transition depuis l'input
Frame 90-100:
  - Input + bouton fade out (opacity 1 → 0)
  - Blur: 0 → 10px

// Spinner
Frame 100-150:
  - Circle spinner (lucide-react Loader2)
  - Size: 64px
  - Color: #823F91
  - Animation: rotate 360° (loop)
  - Position: center-center

// Texte
Text: "Votre assistant vous trouve les meilleurs prestataires"
Font: 24px, medium
Color: #2C1810
Position: center, y + 120px
Animation: Fade in (frame 110-120)

// Points animés après "prestataires"
"..." qui apparaissent séquentiellement
Frame 120: "prestataires."
Frame 130: "prestataires.."
Frame 140: "prestataires..."
Loop
```

---

### ÉTAPE 4 : Cartes prestataires apparaissent (Frames 150-270, 4 sec)

**Visuel :**
```
3 cartes côte à côte avec scores différents

┌─────────┐  ┌─────────┐  ┌─────────┐
│ Carte 1 │  │ Carte 2 │  │ Carte 3 │
│ 98%     │  │ 95%     │  │ 92%     │
└─────────┘  └─────────┘  └─────────┘
```

**Code :**
```typescript
// Layout
Container: 3 colonnes
Gap: 32px
Width par carte: 420px
Height: 480px

// CARTE 1 (98%)
{
  avatar: Circle 80px avec gradient border (#823F91)
  name: "Le Délice Oriental",
  type: "Traiteur Maghrébin",
  location: "📍 Paris 18ème",
  score: "98%",
  scoreColor: "#10B981",  // Vert
  price: "45€/personne",
  experience: "12 ans • 300+ événements",
  tags: ["Halal", "Spécialités maghrébines"]
}

// CARTE 2 (95%)
{
  avatar: Circle 80px avec gradient border (#823F91)
  name: "Saveurs & Traditions",
  type: "Traiteur Événementiel",
  location: "📍 Paris 15ème",
  score: "95%",
  scoreColor: "#10B981",
  price: "42€/personne",
  experience: "8 ans • 200+ événements",
  tags: ["Bio", "Menu personnalisé"]
}

// CARTE 3 (92%)
{
  avatar: Circle 80px avec gradient border (#823F91)
  name: "Gourmet Prestige",
  type: "Traiteur Haut de gamme",
  location: "📍 Paris 8ème",
  score: "92%",
  scoreColor: "#10B981",
  price: "65€/personne",
  experience: "15 ans • 500+ événements",
  tags: ["Gastronomique", "Chef étoilé"]
}

// Style des cartes
Background: white
Border: 1px solid #E5E7EB
Border-radius: 16px
Padding: 24px
Box-shadow: 0 4px 12px rgba(0,0,0,0.08)

// Score en haut à droite
Position: absolute, top-right
Font: 32px, bold
Color: #10B981
Background: #F0FDF4 (vert très clair)
Padding: 8px 16px
Border-radius: 12px
```

**Animation :**
```typescript
// Transition depuis loading
Frame 150-160:
  - Spinner fade out
  - Texte fade out

// Cartes apparaissent une par une
Frame 160-190 (Carte 1):
  - TranslateY: 50 → 0
  - Opacity: 0 → 1
  - Scale: 0.95 → 1.0
  - Spring: { damping: 100 }

Frame 190-220 (Carte 2):
  - Même animation (delay 30 frames)

Frame 220-250 (Carte 3):
  - Même animation (delay 60 frames)

// Score counter animation sur chaque carte
Carte 1 score: 0% → 98% en 20 frames
Carte 2 score: 0% → 95% en 20 frames
Carte 3 score: 0% → 92% en 20 frames

Frame 250-270:
  - Cartes stables
  - Légère pulse sur Carte 1 (scale 1.0 → 1.02)
```

---

### ÉTAPE 5 : Bouton "Contacter" (Frames 270-330, 2 sec)

**Visuel :**
```
Bouton "Contacter" apparaît sous la Carte 1 (meilleur score)
```

**Code :**
```typescript
// Bouton
Width: 420px (même largeur que la carte)
Height: 56px
Background: linear-gradient(135deg, #823F91 0%, #c081e3 100%)
Color: white
Text: "Contacter Le Délice Oriental"
Font: 18px, semibold
Border-radius: 16px
Box-shadow: 0 4px 12px rgba(130,63,145,0.3)
Position: Sous la carte 1, margin-top: 16px
```

**Animation :**
```typescript
Frame 270-290:
  - Bouton apparaît
  - TranslateY: 20 → 0
  - Opacity: 0 → 1
  - Scale: 0.95 → 1.05 → 1.0 (bounce)

Frame 290-330:
  - Glow effect pulse
  - Box-shadow pulse: opacity 0.3 ↔ 0.5
```

---

### ÉTAPE 6 : Curseur clique (Frames 330-360, 1 sec)

**Visuel :**
```
Curseur réapparaît et se déplace vers le bouton "Contacter"
```

**Animation :**
```typescript
Frame 330-345:
  - Curseur apparaît (opacity 0 → 1)
  - Position initiale: haut droite
  - Se déplace vers le centre du bouton
  - Ease-out curve

Frame 345-355:
  - Curseur sur le bouton
  - Bouton hover: brightness 110%
  - Bouton scale: 1.0 → 0.98 (click)

Frame 355-360:
  - Bouton scale: 0.98 → 1.0
  - Ripple effect
```

---

### ÉTAPE 7 : Pop-up conversation (Frames 360-450, 3 sec)

**Visuel :**
```
Modal de conversation apparaît au centre

┌────────────────────────────────────┐
│  Le Délice Oriental      [✕]       │
├────────────────────────────────────┤
│                                    │
│  [Message pré-rempli]              │
│                                    │
│                                    │
│  ┌──────────────────────────────┐ │
│  │ Bonjour, je suis intéressé   │ │
│  │ par vos services pour un     │ │
│  │ événement de 80 personnes    │ │
│  │ à Paris.                     │ │
│  └──────────────────────────────┘ │
│                                    │
│                    [Envoyer →]     │
└────────────────────────────────────┘
```

**Code :**
```typescript
// Modal
Width: 700px
Height: 500px
Background: white
Border-radius: 24px
Box-shadow: 0 20px 60px rgba(0,0,0,0.15)
Position: center-center
Backdrop: rgba(0,0,0,0.4) avec blur 8px

// Header
Height: 80px
Border-bottom: 1px solid #E5E7EB
Padding: 20px

// Avatar
Size: 48px
Background: gradient #823F91 → #c081e3
Border: 2px solid white

// Nom
Text: "Le Délice Oriental"
Font: 20px, semibold, #2C1810

// Status
Text: "En ligne"
Font: 14px, #10B981
Dot: 8px circle green, pulse

// Bouton fermer
Icon: X (lucide-react)
Size: 24px
Color: #6B7280
Position: top-right

// Zone message
Padding: 24px
Background: #F9FAFB

// Input pré-rempli
Width: 100%
Height: 150px
Background: white
Border: 2px solid #E5E7EB
Border-radius: 12px
Padding: 16px
Font: 16px, line-height: 1.6

Message: "Bonjour, je suis intéressé par vos services pour un événement de 80 personnes à Paris. Pourriez-vous me faire un devis ?"

// Bouton Envoyer
Width: 140px
Height: 48px
Background: #823F91
Color: white
Text: "Envoyer →"
Border-radius: 12px
Position: bottom-right
Margin-top: 16px
```

**Animation :**
```typescript
Frame 360-375:
  // Backdrop apparaît
  - Overlay opacity: 0 → 1
  - Blur: 0 → 8px

  // Cartes en arrière-plan blur + scale down
  - Cards scale: 1.0 → 0.95
  - Cards blur: 0 → 8px

Frame 375-400:
  // Modal apparaît
  - Scale: 0.8 → 1.1 → 1.0 (bounce overshoot)
  - Opacity: 0 → 1
  - Spring: { damping: 60, mass: 0.8 }

Frame 400-420:
  // Contenu du modal fade in séquentiel
  - Header fade in
  - Avatar rotation 360°
  - Status dot pulse

Frame 420-450:
  // Message pré-rempli typing effect
  - Texte apparaît caractère par caractère (4 chars/frame)
  - Cursor blink à la fin du texte

  // Bouton "Envoyer" glow pulse
  - Box-shadow pulse
```

---

## 📁 STRUCTURE DU CODE

### Fichiers à créer

```
/src/NuplyMatchingSimple/
├── NuplyMatchingSimple.tsx          // Composition principale (450 frames)
├── constants.ts                     // Couleurs + constantes
├── components/
│   ├── ChatInput.tsx                // Step 1: Input de recherche
│   ├── Cursor.tsx                   // Curseur souris animé
│   ├── LoadingScreen.tsx            // Step 3: Écran de chargement
│   ├── ProviderCard.tsx             // Step 4: Carte prestataire
│   └── ConversationModal.tsx        // Step 7: Pop-up conversation
└── utils/
    └── animations.ts                // Helpers animations
```

### Composition principale

```typescript
// /src/NuplyMatchingSimple/NuplyMatchingSimple.tsx
import { AbsoluteFill, useCurrentFrame, interpolate, spring } from 'remotion';

export const NuplyMatchingSimple = () => {
  const frame = useCurrentFrame();

  return (
    <AbsoluteFill style={{ backgroundColor: '#FFFFFF' }}>
      {/* Step 1: Chat Input (0-60) */}
      {frame < 90 && <ChatInput frame={frame} />}

      {/* Step 2: Cursor click (60-90) */}
      {frame >= 60 && frame < 90 && <Cursor frame={frame} action="click-send" />}

      {/* Step 3: Loading (90-150) */}
      {frame >= 90 && frame < 150 && <LoadingScreen frame={frame} />}

      {/* Step 4: Provider cards (150-270) */}
      {frame >= 150 && frame < 360 && (
        <>
          <ProviderCard data={CARD_1} frame={frame} startFrame={160} position={0} />
          <ProviderCard data={CARD_2} frame={frame} startFrame={190} position={1} />
          <ProviderCard data={CARD_3} frame={frame} startFrame={220} position={2} />
        </>
      )}

      {/* Step 5: Contact Button (270-330) */}
      {frame >= 270 && frame < 360 && <ContactButton frame={frame} />}

      {/* Step 6: Cursor click button (330-360) */}
      {frame >= 330 && frame < 360 && <Cursor frame={frame} action="click-contact" />}

      {/* Step 7: Conversation Modal (360-450) */}
      {frame >= 360 && <ConversationModal frame={frame} startFrame={360} />}
    </AbsoluteFill>
  );
};
```

### Enregistrer dans Root.tsx

```typescript
// /src/Root.tsx
import { NuplyMatchingSimple } from "./NuplyMatchingSimple/NuplyMatchingSimple";

// Ajouter dans <Remotion.Root>:
<Composition
  id="NuplyMatchingSimple"
  component={NuplyMatchingSimple}
  durationInFrames={450}
  fps={30}
  width={1920}
  height={1080}
  defaultProps={{}}
/>
```

---

## 🎨 DÉTAILS TECHNIQUES

### Typing Effect

```typescript
const typingEffect = (text: string, frame: number, startFrame: number, charsPerFrame: number = 3) => {
  const elapsed = Math.max(0, frame - startFrame);
  const charsToShow = Math.floor(elapsed * charsPerFrame);
  return text.substring(0, charsToShow);
};
```

### Counter Animation (scores)

```typescript
const counterAnimation = (target: number, frame: number, startFrame: number, duration: number) => {
  return Math.floor(
    interpolate(
      frame,
      [startFrame, startFrame + duration],
      [0, target],
      { extrapolateRight: 'clamp' }
    )
  );
};
```

### Spring Bounce

```typescript
const bounceScale = spring({
  frame: frame - startFrame,
  fps: 30,
  config: {
    damping: 60,
    mass: 0.8,
    stiffness: 150,
  },
});
```

---

## ✅ CHECKLIST

Avant de valider :

- [ ] Fond blanc (#FFFFFF) sur toute la vidéo
- [ ] Couleurs Nuply respectées (#823F91, #E8D4EF)
- [ ] Font Geist Sans utilisée partout
- [ ] Typing effects fluides (3-4 chars/frame)
- [ ] Curseur souris visible et smooth
- [ ] Loading screen avec spinner animé
- [ ] 3 cartes avec scores différents (98%, 95%, 92%)
- [ ] Bouton "Contacter" avec glow
- [ ] Pop-up conversation centrée
- [ ] Message pré-rempli avec typing effect
- [ ] Durée totale: 15 secondes (450 frames)
- [ ] 30 FPS constant
- [ ] Aucun temps mort

---

## 🚀 RÉSULTAT ATTENDU

Une vidéo de **15 secondes** ultra-claire qui montre :
1. ✅ User tape sa recherche
2. ✅ Clic sur "Envoyer"
3. ✅ IA cherche (loading)
4. ✅ 3 résultats avec scores
5. ✅ Clic sur "Contacter"
6. ✅ Conversation pré-remplie

**Style :** Simple, épuré, efficace. Pas de fioritures. Chaque étape est claire et visible.

**Niveau :** Productif et pro, pas besoin d'être ultra-fancy. L'important c'est de montrer le flow.

---

**GO! 🚀**
