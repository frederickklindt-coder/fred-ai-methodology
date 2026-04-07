# Pauli Avatar — Master Reusable Prompt (v1)

> **Purpose:** Drop this prompt (or the relevant section) into Gemini, ChatGPT, or Midjourney to generate a consistent caricature avatar of Pauli across all content — solo or alongside Frederick.
> **Reference images:** Always attach the canonical Pauli face reference when generating in a new tool/session. For duo scenes, attach both Pauli and Frederick canonical references.
> **Last updated:** April 7, 2026

---

## 1. CORE IDENTITY PROMPT (Copy This Every Time)

```
Create a highly detailed semi-realistic caricature illustration of a female creative professional named Pauli.

FACE & BODY (CRITICAL — must match reference image exactly):
- Long, dark brown wavy/curly hair, voluminous, flowing past shoulders
- Natural waves with slight curl, not tight ringlets — more flowing and loose than Frederick's curls
- Big warm smile showing teeth, radiating genuine warmth and energy
- Expressive, dark brown eyes with long lashes
- Medium/olive skin tone with warm undertones (Latina)
- Slightly curvy, feminine build
- Exaggerated caricature proportions: head is ~40% of total figure height (matching Frederick's style)

STYLE:
- Semi-realistic caricature (between Pixar and editorial illustration)
- High detail rendering with painterly texture
- Warm cinematic lighting from the front-left
- Slightly exaggerated facial features but ALWAYS recognizable as the same person
- MUST match Frederick's caricature style exactly — same artist feel, same rendering quality
- Consistent across all generations — this is a personal brand avatar

CLOTHING (default):
- Floral print blouse (blue base with pink/coral flowers) — her signature look
- Can rotate to: solid-color feminine tops, casual-smart outfits
- Small gold hoop earrings (ALWAYS present — identity anchor)
- Pink/coral nail polish visible on hands when shown

ACCESSORIES & IDENTITY ELEMENTS:
- Gold hoop earrings (always)
- Pink nails (always, when hands are visible)
- Can include: ring light, English textbook, nail supplies, hiking gear — depending on scene
```

---

## 2. ENVIRONMENT DEFAULTS

```
DEFAULT CONTEXT:
Pauli is a multi-passionate creative: English teacher, nail artist, hiker, content creator, 
and musician. Her environments reflect this variety.

ENVIRONMENT OPTIONS (choose per scene):

Option A — Creative Studio (default):
- Bright, warm workspace
- Ring light with phone visible (content creation)
- Nail polish bottles, beauty supplies
- English textbook or notebook nearby
- Warm ambient lighting, cozy feel

Option B — Outdoor / Adventure:
- Mountain landscape background
- Hiking boots, backpack visible
- Natural lighting, green and earth tones
- Trees, trails, peaks in background

Option C — Teaching / Community:
- Classroom or cozy teaching corner
- English books, whiteboard or notebook with "Hello!" 
- Speech bubbles with English phrases
- Warm, inviting, community feel

Option D — Dark Tech (for duo scenes with Frederick):
- Dark blue-black background (#0D1117)
- Pauli's warm tones contrast against the dark tech environment
- She brings color and warmth INTO Frederick's world
- Same grid lines, node patterns, electric blue accents

Option E — Minimal/Clean (for profile pictures):
- Solid warm gradient background (soft peach-to-cream or warm neutral)
- Just Pauli, no environment
- Maximum focus on face
```

---

## 3. COLOR INTEGRATION

Pauli's palette complements Frederick's while maintaining her own warmth:

| Layer | Colors | Usage |
|-------|--------|-------|
| **Warm (Human)** | Dark brown hair, olive-warm skin, pink/coral nails, gold earrings | Pauli herself — always warm, slightly warmer than Frederick |
| **Floral Accent** | Coral pink, soft blue, natural greens | Her clothing, nail art, organic elements |
| **Cool (Tech — duo scenes only)** | Electric blue `#58A6FF`, soft white `#E6EDF3` | Only in scenes with Frederick — she doesn't own the tech palette |
| **Background** | Warm neutrals (solo) or dark `#0D1117` (duo scenes) | Environment framing |

**Rule:** Pauli is ALWAYS the warmest, most colorful element in any frame. In duo scenes with Frederick, she's warmer than him (and he's already the warm element in his solo scenes). She humanizes every environment she's in.

---

## 4. SCENE VARIATION SYSTEM

Use the Core Identity Prompt above, then append ONE of these scene modifiers:

### 4A. Solo — Content Creator
```
SCENE: Pauli as content creator
- Pauli centered, holding phone or posing with ring light
- Nail polish and beauty elements visible on desk/surface
- Background: Option A (creative studio) — warm, bright, inviting
- Thought bubble or floating icons showing her content topics
- Mood: energetic, authentic, "watch me create something"
```

### 4B. Solo — Teacher
```
SCENE: Pauli as English teacher
- Pauli in teaching pose — gesturing, writing, or engaging audience
- English textbook open, "Hello!" speech bubble, UK/US flag accent
- Background: Option C (teaching/community)
- Warm, accessible, educational energy
- Mood: approachable expert, "learning is fun"
```

### 4C. Solo — Outdoor / Adventure
```
SCENE: Pauli hiking or in nature
- Pauli in casual outdoor wear (can swap floral blouse for hiking outfit)
- Backpack, hiking boots, mountain backdrop
- Background: Option B (outdoor)
- Fresh air, natural light, adventure energy
- Mood: free, alive, "life is bigger than your screen"
```

### 4D. Solo — Nail Artist / Beauty
```
SCENE: Pauli doing nail art
- Pauli holding nail brush or displaying nails
- Nail polish bottles, nail display, beauty supplies
- Background: Option A (creative studio) — clean, well-lit workspace
- Close attention to hands and nail detail
- Mood: focused, creative, precision meets art
```

### 4E. Solo — Profile Picture
```
SCENE: Clean personal avatar
- Pauli head and shoulders only, slightly angled (three-quarter view)
- Big warm smile, gold hoop earrings visible
- Background: warm gradient (peach-to-cream) or solid warm neutral
- Format: 1080×1080 (1:1) or circular crop-safe
- Maximum clarity at small sizes
```

---

## 5. DUO SCENES — Frederick & Pauli Together

> **IMPORTANT:** When generating duo scenes, paste BOTH core identity prompts (Frederick's from `prompts/avatar_master_prompt.md` + Pauli's from this file) before appending the duo scene modifier.

### 5A. Duo — Working Together (Carousel Cover)
```
DUO SCENE: Frederick and Pauli working together (1080×1350, 4:5 portrait)
- Frederick on the left, Pauli on the right (or vice versa)
- Both at a shared workspace: Frederick's laptop + Pauli's creative tools
- Frederick's AI robot companion between or beside them
- Frederick's brain hologram visible above the workspace
- Pauli brings color and warmth; Frederick brings the tech grid
- Background: blend of Option A (cosmic from Frederick) with warm touches (from Pauli)
- Leave space at top for title text overlay
- Mood: partnership, complementary skills, "building together"
```

### 5B. Duo — Debate / Conversation
```
DUO SCENE: Frederick and Pauli in discussion
- Facing each other or angled toward viewer in conversation pose
- Speech bubbles, floating ideas, thought clouds between them
- Robot companion reacting to the conversation
- Background: Option D (dark tech) with Pauli's warm floral elements bleeding in
- Mood: intellectual spark, "two perspectives, one vision"
```

### 5C. Duo — Adventure / Travel
```
DUO SCENE: Frederick and Pauli outdoors
- Both in casual adventure wear
- Mountain/nature backdrop (Patagonia vibes — Argentine landscape)
- Frederick's robot companion as a hiking buddy
- Backpacks, hiking boots, coffee thermos
- Background: natural landscape with subtle tech elements (data lines in the sky, constellation patterns)
- Mood: life partners who build AND explore, "not just screens"
```

### 5D. Duo — Podcast / YouTube Thumbnail
```
DUO SCENE: Frederick and Pauli as co-hosts (1920×1080 or 1080×1080)
- Side by side, animated discussion poses
- Frederick gesturing, Pauli reacting (or vice versa)
- Robot companion between them
- Holographic screens behind showing episode topic
- Background: Option A (cosmic) with warm spotlight on both
- Leave space for episode title text on one side
- Mood: chemistry, banter, "these two have something to say"
```

### 5E. Duo — Profile / Brand
```
DUO SCENE: Clean couple brand image (1080×1080 or 1080×1350)
- Both characters, head and upper body
- Frederick slightly behind-left, Pauli slightly forward-right (or equal)
- Robot peeking between them or on Frederick's shoulder
- Background: dark gradient blending warm-to-cool (Pauli's side warm, Frederick's side cool)
- Format: circular crop-safe for profile images
- Mood: "the team behind the brand"
```

---

## 6. CONSISTENCY CHECKLIST

Before accepting any generated image of Pauli, verify:

- [ ] Hair: long, dark brown, wavy/curly, voluminous, flowing
- [ ] Smile: big, warm, teeth showing, genuine
- [ ] Eyes: dark brown, expressive
- [ ] Skin: medium/olive, warm undertones
- [ ] Earrings: gold hoops (ALWAYS)
- [ ] Nails: pink/coral (when hands visible)
- [ ] Clothing: floral or feminine, colorful
- [ ] Proportions: caricature (big head), NOT realistic portrait
- [ ] Style match: SAME caricature style as Frederick (critical for duo scenes)

---

## 7. GENERATION TIPS

### Creating the Canonical Face Reference
Generate a clean portrait with this prompt:
```
Using this reference image, generate a clean portrait of ONLY the character 
(the woman with long wavy dark brown hair, gold hoop earrings, and floral blouse).

- Head and upper body only, three-quarter angle
- Same exact face, hair, smile, clothing, earrings
- Solid warm neutral background, no environment, no objects
- Semi-realistic caricature style matching the reference
- High resolution, sharp detail on face

This will be used as a character reference sheet for future generations.
```

Save result as: `images/pauli_avatar_canonical_v1.png`

### For Duo Scenes
- Always attach BOTH canonical face references (Frederick + Pauli)
- State explicitly: "These two characters must appear in the SAME image, matching caricature styles"
- Frederick's style anchors the tech world; Pauli's warmth humanizes it

---

## 8. VERSION HISTORY

| Version | Date | Changes |
|---------|------|---------|
| v1 | 2026-04-07 | Initial canonical avatar prompt based on ChatGPT caricature reference image |
