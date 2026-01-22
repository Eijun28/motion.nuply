# 🎯 PROMPT CURSOR - CORRECTIONS FINALES VIDÉO NUPLY

## ❌ PROBLÈMES À CORRIGER

1. **Duplication badge 98%** - Il y en a 2 sur la carte, il n'en faut qu'UN SEUL
2. **Mauvais types de prestataires** - On voit "DJ", "Photographe" alors que TOUTES les cartes doivent être des TRAITEURS
3. **Badge vert en bas** - À SUPPRIMER complètement de la carte
4. **Bouton mal placé** - Il est superposé sur la carte, il doit être EN DESSOUS

---

## ✅ CORRECTIONS À APPLIQUER

### 1. DONNÉES DES CARTES - TOUTES DES TRAITEURS

```typescript
// Liste complète des cartes pour la phase chaos (35 cartes)
// TOUTES sont des traiteurs avec des noms différents

const TRAITEURS_DATA = [
  { id: 1, name: "Le Délice Oriental", type: "Traiteur Maghrébin", score: 98 },
  { id: 2, name: "Saveurs & Traditions", type: "Traiteur Événementiel", score: 95 },
  { id: 3, name: "Gourmet Prestige", type: "Traiteur Haut de gamme", score: 92 },
  { id: 4, name: "Al Baraka", type: "Traiteur Halal", score: 89 },
  { id: 5, name: "La Table Orientale", type: "Traiteur Maghrébin", score: 87 },
  { id: 6, name: "Chez Fatima", type: "Traiteur Traditionnel", score: 85 },
  { id: 7, name: "Royal Couscous", type: "Traiteur Spécialités", score: 84 },
  { id: 8, name: "Les Délices d'Alger", type: "Traiteur Maghrébin", score: 82 },
  { id: 9, name: "Festin du Monde", type: "Traiteur International", score: 80 },
  { id: 10, name: "Saveurs d'Ailleurs", type: "Traiteur Fusion", score: 78 },
  { id: 11, name: "La Perle du Sud", type: "Traiteur Méditerranéen", score: 76 },
  { id: 12, name: "Délices & Épices", type: "Traiteur Événementiel", score: 74 },
  { id: 13, name: "Le Jardin des Saveurs", type: "Traiteur Bio", score: 72 },
  { id: 14, name: "Mille et Une Saveurs", type: "Traiteur Oriental", score: 70 },
  { id: 15, name: "Le Festin Royal", type: "Traiteur Prestige", score: 68 },
  { id: 16, name: "Cuisine du Maghreb", type: "Traiteur Traditionnel", score: 66 },
  { id: 17, name: "Le Palais Gourmand", type: "Traiteur Halal", score: 64 },
  { id: 18, name: "Saveurs Authentiques", type: "Traiteur Maghrébin", score: 62 },
  { id: 19, name: "La Table des Rois", type: "Traiteur Haut de gamme", score: 60 },
  { id: 20, name: "Délices de Fès", type: "Traiteur Marocain", score: 58 },
  { id: 21, name: "Les Saveurs d'Orient", type: "Traiteur Oriental", score: 56 },
  { id: 22, name: "Gourmet & Co", type: "Traiteur Événementiel", score: 54 },
  { id: 23, name: "Le Comptoir Oriental", type: "Traiteur Maghrébin", score: 52 },
  { id: 24, name: "Festin & Délices", type: "Traiteur Prestige", score: 50 },
  { id: 25, name: "La Cuisine du Soleil", type: "Traiteur Méditerranéen", score: 48 },
  { id: 26, name: "Saveurs & Partage", type: "Traiteur Bio", score: 46 },
  { id: 27, name: "Le Jardin d'Eden", type: "Traiteur Végétarien", score: 44 },
  { id: 28, name: "Épices & Traditions", type: "Traiteur Halal", score: 42 },
  { id: 29, name: "La Table Berbère", type: "Traiteur Maghrébin", score: 40 },
  { id: 30, name: "Délices du Monde", type: "Traiteur International", score: 38 },
  { id: 31, name: "Le Festin Enchanté", type: "Traiteur Événementiel", score: 36 },
  { id: 32, name: "Saveurs de Marrakech", type: "Traiteur Marocain", score: 34 },
  { id: 33, name: "La Perle Orientale", type: "Traiteur Oriental", score: 32 },
  { id: 34, name: "Gourmet Express", type: "Traiteur Rapide", score: 30 },
  { id: 35, name: "Le Palais des Saveurs", type: "Traiteur Prestige", score: 28 },
];

// Les 3 meilleures cartes qui restent après le scan IA
const TOP_3_TRAITEURS = [
  TRAITEURS_DATA[0],  // Le Délice Oriental - 98%
  TRAITEURS_DATA[1],  // Saveurs & Traditions - 95%
  TRAITEURS_DATA[2],  // Gourmet Prestige - 92%
];
```

---

### 2. STRUCTURE DE LA CARTE - SANS BADGE EN BAS

```typescript
// Carte focus (420×580px)

FocusCard: {
  width: 420px
  height: 580px
  borderRadius: 24px
  padding: 32px

  // Layout vertical
  display: "flex"
  flexDirection: "column"
  alignItems: "center"
  gap: 0
}

// Contenu de la carte (dans l'ordre)

// 1. Avatar en haut
Avatar: {
  width: 120px
  height: 120px
  borderRadius: "50%"
  background: "linear-gradient(135deg, #823F91, #c081e3)"
  marginBottom: 20px
}

// 2. Nom + Type
Name: "Le Délice Oriental"
  fontSize: 28px
  fontWeight: 700
  color: "white"
  marginBottom: 8px

Type: "Traiteur Maghrébin"
  fontSize: 16px
  color: "rgba(255, 255, 255, 0.7)"
  marginBottom: 24px

// 3. Badges info
InfoBadge1: "⭐ 4.9 · 127 avis"
  marginBottom: 12px

InfoBadge2: "📍 Paris 18ème"
  marginBottom: 12px

InfoBadge3: "💰 45€/personne"
  marginBottom: 0

// 4. FIN - Pas de badge score en bas de la carte
// Le badge score n'apparaît QUE pendant la phase explosion
```

---

### 3. PHASE EXPLOSION - UN SEUL BADGE SCORE GÉANT

```typescript
// Séquence 4 : Score explosion (frames 150-180)

// La carte reste visible mais plus petite et blur
Card: {
  scale: 1.0 → 0.85
  blur: 0 → 6px
  opacity: 1 → 0.4
}

// Badge score GÉANT apparaît AU-DESSUS (position absolue écran)
GiantScoreBadge: {
  // IMPORTANT : Position ABSOLUE par rapport à l'écran
  // PAS par rapport à la carte
  position: "absolute"
  left: "50%"
  top: "50%"
  transform: "translate(-50%, -50%)"

  width: 240px
  height: 240px
  borderRadius: "50%"

  background: "linear-gradient(135deg, #10B981, #059669)"
  border: "6px solid rgba(255, 255, 255, 0.3)"
  boxShadow: [
    "0 0 80px rgba(16, 185, 129, 0.6)",
    "0 0 160px rgba(16, 185, 129, 0.4)"
  ]

  // z-index au-dessus de tout
  zIndex: 100
}

ScoreText: "98%"
  fontSize: 96px
  fontWeight: 900
  color: "white"

ScoreLabel: "Match parfait"
  fontSize: 20px
  color: "rgba(255, 255, 255, 0.9)"

// Confetti explosion autour du badge
Confetti: {
  count: 80
  // ... (comme défini précédemment)
}

// IMPORTANT : Il n'y a QU'UN SEUL badge 98%
// Celui qui apparaît en géant au centre de l'écran
```

---

### 4. BOUTON CTA - EN DESSOUS DE LA CARTE

```typescript
// Séquence 5 : CTA (frames 180-240)

// Transition : Badge géant se transforme en bouton
Frames 180-200:
  // Badge morphing
  GiantScoreBadge: {
    borderRadius: "50%" → 48px  // Devient rectangle arrondi
    width: 240px → 480px
    height: 240px → 72px
    background: gradient vert → gradient violet

    // IMPORTANT : Position change
    // Du centre de l'écran vers EN DESSOUS de la carte
    top: "50%" → 720px  // Position absolue en dessous de la carte
    transform: "translate(-50%, -50%)" → "translate(-50%, 0)"
  }

// État final du bouton
CTAButton: {
  // Position FIXE en dessous de la carte
  position: "absolute"
  left: "50%"
  top: 720px  // En dessous de la carte (carte top:250 + height:580 = 830, -110 de margin)
  transform: "translateX(-50%)"

  width: 480px
  height: 72px
  background: "linear-gradient(135deg, #823F91, #c081e3)"
  borderRadius: 48px

  // Glow effect
  boxShadow: "0 0 60px rgba(130, 63, 145, 0.5)"

  // z-index en dessous du badge géant
  zIndex: 50
}

ButtonText: "Contacter maintenant →"
  fontSize: 24px
  fontWeight: 600
  color: "white"

// La carte reste visible au-dessus (blur + petite)
Card: {
  position: "absolute"
  top: 250px
  left: 750px
  scale: 0.85
  blur: 6px
  opacity: 0.4
  zIndex: 10  // En arrière-plan
}
```

---

### 5. SCHÉMA VISUEL FINAL

```
┌─────────────────────────────────────────┐
│                                         │
│         [Logo Nuply en haut]            │
│                                         │
│                                         │
│      ┌─────────────────────┐            │
│      │    [Avatar]         │            │ ← Carte 420×580
│      │                     │            │   (blur + opacity 0.4)
│      │  Le Délice Oriental │            │
│      │  Traiteur Maghrébin │            │
│      │                     │            │
│      │  ⭐ 4.9 · 127 avis  │            │
│      │  📍 Paris 18ème     │            │
│      │  💰 45€/personne    │            │
│      │                     │            │
│      │  (pas de badge ici) │            │ ← PAS de badge 98% ici
│      └─────────────────────┘            │
│                                         │
│                                         │
│  ┌────────────────────────────────┐    │ ← Bouton EN DESSOUS
│  │  Contacter maintenant →        │    │   (position: top 720px)
│  └────────────────────────────────┘    │
│                                         │
│      Réponse en moins de 2h             │
│                                         │
└─────────────────────────────────────────┘
```

---

## 📋 RÉSUMÉ DES CORRECTIONS

```
✅ TOUTES les cartes sont des TRAITEURS (35 traiteurs différents)
✅ Les 3 meilleures : Le Délice Oriental (98%), Saveurs & Traditions (95%), Gourmet Prestige (92%)
✅ La carte focus N'A PAS de badge 98% en bas
✅ Le badge 98% apparaît UNIQUEMENT pendant l'explosion (géant au centre)
✅ Le bouton "Contacter" est EN DESSOUS de la carte (top: 720px), PAS superposé
✅ Plus de duplication de badge
✅ Layout propre et clair
```

---

## 🚀 PROMPT COMPLET POUR CURSOR

```
APPLIQUE CES CORRECTIONS AU PROJET NuplyPremium :

1. DONNÉES DES CARTES :
   - TOUTES les 35 cartes mini sont des TRAITEURS (pas de DJ, photographe, etc.)
   - Utilise la liste TRAITEURS_DATA fournie ci-dessus
   - Les 3 meilleures : Le Délice Oriental (98%), Saveurs & Traditions (95%), Gourmet Prestige (92%)

2. CARTE FOCUS (420×580px) :
   - Avatar 120px
   - Nom : "Le Délice Oriental" (28px, bold)
   - Type : "Traiteur Maghrébin" (16px)
   - 3 badges info (⭐ 4.9, 📍 Paris, 💰 45€)
   - PAS DE BADGE 98% EN BAS DE LA CARTE
   - Fin de la carte après les badges info

3. BADGE SCORE (explosion seulement) :
   - UN SEUL badge 98% dans toute la vidéo
   - Apparaît en GÉANT (240×240px) pendant la phase explosion (frames 150-180)
   - Position absolue centre de l'écran : left: 50%, top: 50%, transform: translate(-50%, -50%)
   - z-index: 100 (au-dessus de tout)
   - Avec confetti explosion autour

4. BOUTON CTA :
   - Position EN DESSOUS de la carte (PAS superposé)
   - Position absolue : left: 50%, top: 720px, transform: translateX(-50%)
   - Le badge 98% se transforme (morphing) en ce bouton
   - Dimensions finales : 480×72px, border-radius 48px
   - Gradient violet, glow effect
   - z-index: 50

5. TRANSITIONS :
   - Frames 150-180 : Badge 98% géant au centre avec confetti
   - Frames 180-200 : Badge morphing (cercle → rectangle, centre → bas, vert → violet)
   - Frames 200-240 : Bouton stable en dessous de la carte avec glow pulse

Assure-toi qu'il n'y ait AUCUNE duplication de badge et que le layout soit propre.
```

---

**Avec ces corrections, la vidéo sera PARFAITE ! 🎯**

CHECKLIST :
- [ ] 35 cartes de traiteurs avec noms différents
- [ ] Pas de DJ ou photographe
- [ ] Carte focus sans badge en bas
- [ ] Un seul badge 98% (géant pendant explosion)
- [ ] Bouton en dessous de la carte (top: 720px)
- [ ] Pas de superposition
- [ ] Morphing badge → bouton smooth
