# Frederick Avatar — Master Reusable Prompt (v1)

> **Purpose:** Drop this prompt (or the relevant section) into Gemini, ChatGPT, or Midjourney to generate a consistent caricature avatar of Frederick across all content.
> **Reference image:** Always attach the canonical avatar reference when generating in a new tool/session.
> **Last updated:** April 6, 2026

---

## 1. CORE IDENTITY PROMPT (Copy This Every Time)

```
Create a highly detailed semi-realistic caricature illustration of a male AI builder and creative technologist named Frederick.

FACE & BODY (CRITICAL — must match reference image exactly):
- Dense, voluminous curly hair (medium-brown with golden-amber highlights, medium length, springs outward)
- Full beard, well-groomed, slightly lighter brown than hair
- Big warm smile showing teeth, eyes slightly squinted from genuine grinning
- Expressive, bright brown eyes
- Light-medium skin tone with warm undertones
- Slightly stocky build, broad shoulders
- Exaggerated caricature proportions: head is ~40% of total figure height (bigger head = more personality)

STYLE:
- Semi-realistic caricature (between Pixar and editorial illustration)
- High detail rendering with painterly texture
- Warm cinematic lighting from the front-left
- Slightly exaggerated facial features but ALWAYS recognizable as the same person
- Consistent across all generations — this is a personal brand avatar

CLOTHING (default):
- Dark navy/charcoal plaid flannel shirt (open or buttoned)
- Burgundy/maroon undershirt or t-shirt visible at collar
- Sleeves can be rolled up to show forearms when working

SIGNATURE COMPANION — THE AI ROBOT (must appear in EVERY generation):
- Small friendly robot (roughly 30% of Frederick's height)
- Positioned to Frederick's right side (viewer's left)
- Round head, compact body, silver-white metallic finish
- Large expressive blue LED eyes (hex: #58A6FF)
- Glowing blue circular chest emblem
- Cute and helpful demeanor — NOT menacing, NOT generic
- Can hold items, point at things, or react to the scene
- This robot is Frederick's visual brand anchor — treat it like a mascot

HOLOGRAPHIC BRAIN ELEMENT:
- A glowing neural network / brain hologram floating near the workspace
- Electric blue wireframe (#58A6FF) with node connections
- Represents AI thinking / orchestration
- Can be near the laptop, above the desk, or between Frederick and the robot
```

---

## 2. ENVIRONMENT DEFAULTS

```
DEFAULT WORKSPACE:
- Sitting at a wooden desk, working on a laptop
- Laptop screen shows a subtle glow (content varies by scene)
- Desk has creative chaos: notebooks, scattered papers, sticky notes, phone, pens
- Coffee mug (visible, part of the identity — "COFFEE" label or rocket/alien doodle on it)
- Crumpled paper balls (ideas discarded, iteration visual)
- "TASK IDEAS" or similar handwritten notes visible on paper

BACKGROUND OPTIONS (choose per scene):

Option A — Cosmic/Imaginative (default for covers):
- Deep space with stars, nebulae, planets
- Rockets launching in the background
- Blend of warm amber and cool blue tones
- Communicates: builder who thinks big, explores, creates

Option B — Dark Tech (for on-brand carousel slides):
- Dark blue-black background (#0D1117)
- Subtle grid lines or node patterns
- Electric blue (#58A6FF) accent glows
- Matches the existing carousel visual system

Option C — Minimal/Clean (for profile pictures, small thumbnails):
- Solid dark gradient background
- Just Frederick + robot, no desk
- Maximum focus on face and companion
```

---

## 3. COLOR INTEGRATION

The avatar lives at the intersection of two palettes:

| Layer | Colors | Usage |
|-------|--------|-------|
| **Warm (Human)** | Golden-amber highlights, warm skin tones, burgundy shirt, coffee browns | Frederick himself — always warm |
| **Cool (Tech/AI)** | Electric blue `#58A6FF`, bright green `#3FB950`, soft white `#E6EDF3` | Robot eyes, brain hologram, screen glows, data elements |
| **Background** | Dark blue-black `#0D1117` (tech scenes) or deep cosmic navy-purple (cover scenes) | Environment framing |

**Rule:** Frederick is always the warmest element in the frame. Everything tech/AI around him is cool-toned. This contrast = human orchestrating machines.

---

## 4. SCENE VARIATION SYSTEM

Don't rewrite the full prompt each time. Use the Core Identity Prompt above, then append ONE of these scene modifiers:

### 4A. Carousel Cover Image
```
SCENE: Carousel cover for Instagram (1080×1350, 4:5 portrait)
- Frederick centered, slightly below vertical center
- Robot companion visible and engaged (pointing at something, holding a sign, or reacting)
- Background: Option A (cosmic) or Option B (dark tech) — match carousel topic
- Leave clean space at top for title text overlay
- Leave clean space at bottom for subtitle or branding
- The desk can be cropped — show Frederick from chest/waist up
- Mood: confident, inviting, "this is worth swiping through"
```

### 4B. Inner Carousel Slide (Avatar as Visual Element)
```
SCENE: Small avatar for carousel slide corner or callout
- Frederick bust only (head + shoulders) or chibi/mini version
- Robot can be mini-sized next to him
- Background: transparent or dark (#0D1117)
- Style: slightly more simplified/iconic than the full illustration
- Size: will be composited at ~200-300px within a 1080×1350 slide
- Use as: proof element ("real person behind this"), narrator indicator, or CTA companion
```

### 4C. Podcast / YouTube Thumbnail
```
SCENE: Podcast episode artwork or YouTube thumbnail
- Frederick in animated discussion pose (hand gesturing, leaning forward, or thinking pose)
- Robot reacting alongside (surprised, thinking, or pointing at a floating topic)
- Two floating holographic screens showing debate/comparison content
- Background: Option A (cosmic) with warm spotlight on Frederick
- Leave space on right side for episode title text
- Format: 1920×1080 (16:9) or 1080×1080 (1:1)
- Mood: energetic, intellectual, "tune in for this debate"
```

### 4D. Philosophy / Thinking Post
```
SCENE: Reflective/philosophical visual
- Frederick in a thinking pose (chin on hand, looking slightly upward)
- Robot mirroring the pose or sitting thoughtfully
- Background: more abstract — floating questions, philosophical symbols, soft cosmic
- Fewer desk elements, more open space
- Glowing brain hologram more prominent
- Mood: contemplative, deep, "this person thinks before they build"
```

### 4E. Systems / Architecture Post
```
SCENE: Technical/building visual
- Frederick actively working — typing, pointing at screen, reviewing
- Multiple floating holographic screens around him showing code, architecture diagrams, node graphs
- Robot is "assisting" — projecting code, running diagnostics, pointing at a screen
- Desk is more cluttered with tech: multiple devices, terminal output visible
- Background: Option B (dark tech grid)
- Floating stats: "35 agents", "254 commits", "3 systems"
- Mood: in the zone, productive, "this is how AI systems get built"
```

### 4F. Profile Picture / Avatar Icon
```
SCENE: Clean personal brand avatar
- Frederick head and shoulders only, slightly angled (three-quarter view)
- Big warm smile
- Robot peeking from behind his shoulder or sitting on his shoulder
- Background: solid dark gradient, no environment
- Format: 1080×1080 (1:1) or circular crop-safe
- Maximum clarity at small sizes — no small details that disappear at 110×110px
```

---

## 5. CONSISTENCY CHECKLIST

Before accepting any generated image, verify:

- [ ] Hair: dense curly, medium-brown with golden highlights
- [ ] Beard: full, groomed, slightly lighter than hair
- [ ] Smile: warm, teeth showing, eyes squinted
- [ ] Shirt: plaid/flannel, dark tones
- [ ] Robot companion: present, silver-white, blue LED eyes, friendly
- [ ] Brain hologram: present (can be subtle in minimal scenes)
- [ ] Color temperature: Frederick warm, tech elements cool
- [ ] Proportions: caricature (big head), NOT realistic portrait proportions

---

## 5B. DUO SCENES — Frederick & Pauli Together

For scenes that include both Frederick and Pauli, see **`prompts/avatar_pauli_prompt.md` Section 5** which contains the full duo scene system (working together, debate, adventure, podcast, brand).

**When generating duo scenes:**
1. Paste Frederick's Core Identity Prompt (Section 1 above)
2. Paste Pauli's Core Identity Prompt (from `avatar_pauli_prompt.md` Section 1)
3. Append the relevant duo scene modifier (from `avatar_pauli_prompt.md` Section 5)
4. Attach BOTH canonical face references

---

## 6. GENERATION TIPS BY TOOL

### Gemini (Nano Banana)
- Attach reference image + this Core Identity Prompt
- Gemini responds well to detailed physical descriptions
- May need to emphasize "caricature NOT realistic" to avoid portrait mode

### ChatGPT (DALL·E)
- Best for quick iterations and style experiments
- Tends to default to softer style — push for "detailed, sharp rendering"
- Include "semi-realistic caricature" explicitly

### Midjourney
- Add `--style raw` for more control
- Use `--cref [reference_url]` for character consistency
- Append: `semi-realistic caricature, editorial illustration, warm lighting, detailed`

---

## 7. VERSION HISTORY

| Version | Date | Changes |
|---------|------|---------|
| v1 | 2026-04-06 | Initial canonical avatar prompt based on ChatGPT caricature reference image |
| v1.1 | 2026-04-07 | Added duo scene cross-reference to Pauli's avatar prompt |
