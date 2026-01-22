# 🔧 CORRECTIONS LAYOUT - CARTES ET ALIGNEMENT

## ❌ PROBLÈMES IDENTIFIÉS

1. **Cartes mal proportionnées** - Trop larges ou trop hautes
2. **Badge 98% mal placé** - Superposé sur le texte
3. **Éléments qui se chevauchent** - Pas d'espacement clair
4. **Texte coupé** - Layout pas adapté au contenu

---

## ✅ DIMENSIONS EXACTES À RESPECTER

### **CARTE MINI (Phase chaos)**

```typescript
MiniCard: {
  width: 160px       // Fixe
  height: 220px      // Fixe
  aspectRatio: "8/11" // Ratio carte classique

  borderRadius: 12px
  padding: 16px

  // Structure interne (tout en column, pas de superposition)
  display: "flex"
  flexDirection: "column"
  alignItems: "center"
  gap: 12px
}

// Contenu de la mini carte
Avatar: {
  width: 60px
  height: 60px
  borderRadius: "50%"
  marginBottom: 8px
}

Name: {
  fontSize: 14px
  fontWeight: 600
  textAlign: "center"
  maxWidth: "100%"
  overflow: "hidden"
  textOverflow: "ellipsis"
  whiteSpace: "nowrap"
}

Type: {
  fontSize: 11px
  color: "rgba(255, 255, 255, 0.6)"
  textAlign: "center"
}
```

---

### **CARTE FOCUS (Phase principale)**

```typescript
FocusCard: {
  width: 420px       // Fixe
  height: 580px      // Fixe
  aspectRatio: "7/10"

  borderRadius: 24px
  padding: 32px

  // Structure en flexbox verticale
  display: "flex"
  flexDirection: "column"
  alignItems: "center"
  justifyContent: "flex-start"
  gap: 0  // On gère l'espacement manuellement
}

// LAYOUT INTERNE (positions relatives, pas absolues)

// Zone 1: Avatar (en haut)
Avatar: {
  width: 120px
  height: 120px
  borderRadius: "50%"
  marginTop: 0
  marginBottom: 20px  // Espace avant le nom
}

// Zone 2: Nom + Type
NameSection: {
  width: "100%"
  textAlign: "center"
  marginBottom: 24px  // Espace avant les infos
}

Name: {
  fontSize: 28px
  fontWeight: 700
  color: "white"
  marginBottom: 8px
  lineHeight: 1.2
}

Type: {
  fontSize: 16px
  fontWeight: 500
  color: "rgba(255, 255, 255, 0.7)"
}

// Zone 3: Infos badges (en colonne, pas en ligne)
InfoSection: {
  width: "100%"
  display: "flex"
  flexDirection: "column"
  alignItems: "center"
  gap: 12px
  marginBottom: 24px  // Espace avant le score
}

InfoBadge: {
  width: "90%"  // Occupe presque toute la largeur
  maxWidth: 320px
  height: 40px

  display: "flex"
  alignItems: "center"
  justifyContent: "center"
  gap: 8px

  background: "rgba(255, 255, 255, 0.08)"
  backdropFilter: "blur(10px)"
  border: "1px solid rgba(255, 255, 255, 0.12)"
  borderRadius: 12px
  padding: "0 16px"
}

BadgeIcon: {
  fontSize: 18px
}

BadgeText: {
  fontSize: 15px
  fontWeight: 500
  color: "rgba(255, 255, 255, 0.9)"
}

// Zone 4: Score badge (EN BAS, séparé)
ScoreBadge: {
  width: 100px
  height: 100px
  borderRadius: "50%"

  // Position: EN BAS de la carte avec margin-top auto
  marginTop: "auto"  // Pousse le badge en bas
  marginBottom: 0

  display: "flex"
  flexDirection: "column"
  alignItems: "center"
  justifyContent: "center"

  background: "linear-gradient(135deg, #10B981, #059669)"
  border: "3px solid rgba(255, 255, 255, 0.2)"
  boxShadow: "0 0 40px rgba(16, 185, 129, 0.5)"
}

ScoreText: {
  fontSize: 36px
  fontWeight: 800
  color: "white"
  lineHeight: 1
}

ScoreLabel: {
  fontSize: 11px
  fontWeight: 600
  color: "rgba(255, 255, 255, 0.8)"
  marginTop: 4px
}
```

---

## 📐 SCHÉMA VISUEL DE LA CARTE

```
┌────────────────────────────────┐  ← Card 420×580px
│         padding: 32px          │
│                                │
│       ┌────────────┐           │  ← Avatar 120×120px
│       │            │           │
│       │  [Avatar]  │           │
│       │            │           │
│       └────────────┘           │
│                                │  ← 20px gap
│     Le Délice Oriental         │  ← Name 28px
│                                │  ← 8px gap
│    Traiteur Maghrébin          │  ← Type 16px
│                                │  ← 24px gap
│  ┌──────────────────────────┐ │  ← Badge 1
│  │  ⭐ 4.9 · 127 avis       │ │    90% width, 40px height
│  └──────────────────────────┘ │
│                                │  ← 12px gap
│  ┌──────────────────────────┐ │  ← Badge 2
│  │  📍 Paris 18ème          │ │
│  └──────────────────────────┘ │
│                                │  ← 12px gap
│  ┌──────────────────────────┐ │  ← Badge 3
│  │  💰 45€/personne         │ │
│  └──────────────────────────┘ │
│                                │  ← 24px gap
│          [ESPACE]              │
│                                │  ← margin-top: auto
│         ┌──────┐               │  ← Score badge 100×100px
│         │ 98% │               │    En bas, centré
│         └──────┘               │
│                                │
└────────────────────────────────┘
```

---

## 🎯 POSITIONNEMENT DES 3 CARTES (Phase sélection)

```typescript
// Les 3 cartes doivent être ALIGNÉES horizontalement

Container: {
  width: 1920px
  height: 1080px

  display: "flex"
  flexDirection: "row"
  justifyContent: "center"
  alignItems: "center"
  gap: 48px  // Espace entre les cartes
}

// Positions calculées automatiquement par flexbox
// Mais si positions absolues nécessaires :

Card1_Left: {
  position: "absolute"
  left: 376px      // (1920 - (3×420 + 2×48)) / 2
  top: 250px       // (1080 - 580) / 2
}

Card2_Center: {
  position: "absolute"
  left: 844px      // 376 + 420 + 48
  top: 250px
}

Card3_Right: {
  position: "absolute"
  left: 1312px     // 844 + 420 + 48
  top: 250px
}

// IMPORTANT : Les 3 cartes ont le même Y (250px)
// pour être parfaitement alignées horizontalement
```

---

## 🔍 PHASE FOCUS - CARTE CENTRALE GROSSIT

```typescript
// La carte du centre grossit et se centre

AnimationFocus: {
  from: {
    width: 420px
    height: 580px
    left: 844px
    top: 250px
  }

  to: {
    width: 420px      // GARDE LA MÊME TAILLE
    height: 580px     // Pas de scale pour éviter déformation
    left: 750px       // Centre horizontal: (1920 - 420) / 2
    top: 250px        // MÊME Y, ne bouge pas verticalement
  }

  // Alternative si vraiment besoin de grossir:
  // Utiliser transform: scale() au lieu de changer width/height
  transform: "scale(1.0)" → "scale(1.15)"
  transformOrigin: "center center"
}

// Les cartes latérales disparaissent
Card1_Left, Card3_Right: {
  opacity: 1 → 0
  blur: 0 → 8px
  scale: 1.0 → 0.95
  duration: 15 frames
}
```

---

## 🎨 BADGE SCORE EXPLOSION (Phase 4)

```typescript
// Le badge REMPLACE temporairement la carte, pas superposé

Phase4_ScoreExplosion: {
  // Carte devient plus petite et blur
  Card: {
    scale: 1.0 → 0.85
    blur: 0 → 6px
    opacity: 1 → 0.5
  }

  // Badge géant apparaît AU-DESSUS (z-index)
  GiantScoreBadge: {
    position: "absolute"
    left: "50%"         // Centre horizontal
    top: "50%"          // Centre vertical
    transform: "translate(-50%, -50%)"  // Vraiment centré

    width: 240px
    height: 240px
    borderRadius: "50%"

    // Pas de positionnement relatif à la carte
    // Position absolue par rapport à l'écran
  }
}
```

---

## 📝 CODE EXEMPLE CORRECT

### Composant Carte Focus

```typescript
// components/FocusCard.tsx
import { AbsoluteFill } from 'remotion';

interface FocusCardProps {
  name: string;
  type: string;
  rating: number;
  reviews: number;
  location: string;
  price: string;
  score: number;
}

export const FocusCard: React.FC<FocusCardProps> = ({
  name, type, rating, reviews, location, price, score
}) => {
  return (
    <div
      style={{
        width: 420,
        height: 580,
        borderRadius: 24,
        padding: 32,
        background: 'rgba(255, 255, 255, 0.12)',
        backdropFilter: 'blur(40px)',
        border: '2px solid rgba(255, 255, 255, 0.15)',
        boxShadow: '0 20px 60px rgba(0, 0, 0, 0.3)',

        // FLEXBOX pour layout vertical propre
        display: 'flex',
        flexDirection: 'column',
        alignItems: 'center',
        justifyContent: 'flex-start',
      }}
    >
      {/* Avatar */}
      <div
        style={{
          width: 120,
          height: 120,
          borderRadius: '50%',
          background: 'linear-gradient(135deg, #823F91, #c081e3)',
          border: '4px solid rgba(255, 255, 255, 0.2)',
          marginBottom: 20,
        }}
      />

      {/* Nom + Type */}
      <div style={{ width: '100%', textAlign: 'center', marginBottom: 24 }}>
        <h2 style={{
          fontSize: 28,
          fontWeight: 700,
          color: 'white',
          marginBottom: 8,
          lineHeight: 1.2,
        }}>
          {name}
        </h2>
        <p style={{
          fontSize: 16,
          fontWeight: 500,
          color: 'rgba(255, 255, 255, 0.7)',
        }}>
          {type}
        </p>
      </div>

      {/* Badges info (en colonne) */}
      <div style={{
        width: '100%',
        display: 'flex',
        flexDirection: 'column',
        alignItems: 'center',
        gap: 12,
        marginBottom: 24,
      }}>
        {/* Badge 1 */}
        <div style={{
          width: '90%',
          maxWidth: 320,
          height: 40,
          display: 'flex',
          alignItems: 'center',
          justifyContent: 'center',
          gap: 8,
          background: 'rgba(255, 255, 255, 0.08)',
          backdropFilter: 'blur(10px)',
          border: '1px solid rgba(255, 255, 255, 0.12)',
          borderRadius: 12,
          padding: '0 16px',
        }}>
          <span style={{ fontSize: 18 }}>⭐</span>
          <span style={{ fontSize: 15, fontWeight: 500, color: 'rgba(255, 255, 255, 0.9)' }}>
            {rating} · {reviews} avis
          </span>
        </div>

        {/* Badge 2 */}
        <div style={{
          width: '90%',
          maxWidth: 320,
          height: 40,
          display: 'flex',
          alignItems: 'center',
          justifyContent: 'center',
          gap: 8,
          background: 'rgba(255, 255, 255, 0.08)',
          backdropFilter: 'blur(10px)',
          border: '1px solid rgba(255, 255, 255, 0.12)',
          borderRadius: 12,
          padding: '0 16px',
        }}>
          <span style={{ fontSize: 18 }}>📍</span>
          <span style={{ fontSize: 15, fontWeight: 500, color: 'rgba(255, 255, 255, 0.9)' }}>
            {location}
          </span>
        </div>

        {/* Badge 3 */}
        <div style={{
          width: '90%',
          maxWidth: 320,
          height: 40,
          display: 'flex',
          alignItems: 'center',
          justifyContent: 'center',
          gap: 8,
          background: 'rgba(255, 255, 255, 0.08)',
          backdropFilter: 'blur(10px)',
          border: '1px solid rgba(255, 255, 255, 0.12)',
          borderRadius: 12,
          padding: '0 16px',
        }}>
          <span style={{ fontSize: 18 }}>💰</span>
          <span style={{ fontSize: 15, fontWeight: 500, color: 'rgba(255, 255, 255, 0.9)' }}>
            {price}
          </span>
        </div>
      </div>

      {/* Spacer pour pousser le badge en bas */}
      <div style={{ flex: 1 }} />

      {/* Badge score EN BAS */}
      <div
        style={{
          width: 100,
          height: 100,
          borderRadius: '50%',
          background: 'linear-gradient(135deg, #10B981, #059669)',
          border: '3px solid rgba(255, 255, 255, 0.2)',
          boxShadow: '0 0 40px rgba(16, 185, 129, 0.5)',
          display: 'flex',
          flexDirection: 'column',
          alignItems: 'center',
          justifyContent: 'center',
        }}
      >
        <span style={{
          fontSize: 36,
          fontWeight: 800,
          color: 'white',
          lineHeight: 1,
        }}>
          {score}%
        </span>
        <span style={{
          fontSize: 11,
          fontWeight: 600,
          color: 'rgba(255, 255, 255, 0.8)',
          marginTop: 4,
        }}>
          Match
        </span>
      </div>
    </div>
  );
};
```

---

## ✅ CHECKLIST CORRECTIONS

Applique ces règles :

- [ ] **Toutes les cartes ont des dimensions FIXES** (pas de calculs dynamiques)
- [ ] **Utilise Flexbox** pour layout vertical (pas de positions absolues internes)
- [ ] **gap entre éléments** bien défini (12px, 20px, 24px)
- [ ] **marginTop: auto** pour pousser le score badge en bas
- [ ] **Les 3 cartes ont le même top** (250px) pour alignement horizontal
- [ ] **Pas de superposition** : chaque élément a son espace
- [ ] **Badge score SÉPARÉ** de la carte (position absolute sur l'écran, pas sur la carte)
- [ ] **transform: scale()** au lieu de changer width/height pour grossir
- [ ] **textOverflow: ellipsis** pour textes trop longs
- [ ] **maxWidth sur badges** pour éviter débordement

---

## 🚀 PROMPT POUR CURSOR

```
CORRIGE LE LAYOUT DES CARTES avec ces règles strictes :

1. DIMENSIONS FIXES :
   - Mini carte : 160×220px
   - Carte focus : 420×580px
   - Badge score : 100×100px (dans la carte) ou 240×240px (explosion)

2. LAYOUT FLEXBOX :
   - display: flex, flexDirection: column
   - alignItems: center
   - gap: 12px entre badges, 20px avatar→nom, 24px nom→badges
   - marginTop: auto pour pousser score badge en bas

3. POSITIONNEMENT 3 CARTES :
   - Card1: left 376px, top 250px
   - Card2: left 844px, top 250px
   - Card3: left 1312px, top 250px
   - Gap 48px entre chaque

4. AUCUNE SUPERPOSITION :
   - Tous les éléments en position relative DANS la carte
   - Score badge explosion en position absolute PAR RAPPORT À L'ÉCRAN

5. UTILISE LE CODE EXEMPLE FocusCard.tsx fourni ci-dessus

Applique ces corrections à TOUTES les cartes du projet.
```

---

**Maintenant les cartes seront PARFAITES ! 📐✨**
