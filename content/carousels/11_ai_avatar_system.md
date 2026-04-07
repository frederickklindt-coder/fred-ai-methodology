# Carousel 11 — How to Build a Reusable AI Avatar System

> **Topic:** From real photo to consistent brand character you can drop into any scene
> **Audience:** Beginners + builders curious about AI, systems, and leverage
> **Keyword CTA:** AVATAR
> **Date:** April 7, 2026
> **Visual note:** Each slide will have a generated image background/example. Text is designed to complement the visuals.
> **Process note:** This carousel teaches the REAL process used to build Frederick's avatar system. Includes the cross-AI workflow (ChatGPT generates → ChatGPT analyzes → Claude refines → Gemini generates scenes) and Gemini-specific guardrails from hard-won lessons.

---

```
Slide 1:
I built a digital version of myself
that shows up in Paris, Venice, and mid-parachute jump.

Same face. Same style. Every single time.

No Photoshop.
No design skills.
No illustrator on retainer.

Just one photo, a cross-AI workflow, and a system.

Here's the exact process. ↓
```

---

```
Slide 2:
STEP 1 — START WITH ONE REAL PHOTO

Your phone camera is enough.

Rules:
→ Head + shoulders, clean background
→ Good lighting (face a window)
→ Natural expression — the AI learns YOUR face

This is the only "real" asset you need.
Everything else gets generated.

📸 PROMPT (paste in ChatGPT with your photo):

"Using this photo as reference,
create a semi-realistic caricature
illustration. Exaggerated proportions
(head ~40% of body). Keep the EXACT
face features, hair, and expression.
Style: between Pixar and editorial
illustration. Warm cinematic lighting."
```

---

```
Slide 3:
STEP 2 — ITERATE UNTIL IT'S *YOU*

The first generation won't be perfect.
That's the point.

Feed the output back and refine:

🔁 ITERATION PROMPT:

"This is close but adjust:
— [specific hair fix]
— [specific facial feature fix]
— [expression/mood adjustment]
— keep the same caricature style
Regenerate with these corrections."

Pro tip: ChatGPT lets you HIGHLIGHT
the exact area of the image you want
changed. Circle the hair, the eyes,
the shirt — and describe the fix.

Text + visual highlight = surgical edits.
Way faster than describing everything
in words alone.

3–5 rounds gets you a character
that's unmistakably YOU.
```

---

```
Slide 4:
STEP 3 — LET AI ANALYZE YOUR AVATAR

This is the step nobody talks about.

Once you have a caricature you love,
DON'T jump to using it.

Ask AI to BREAK IT DOWN first:

🔍 ANALYSIS PROMPT:

"Analyze this image. Focus on the
persona — me. I need a solid prompt
capable of replicating this character
as an avatar across all my future
content. Break down: face structure,
hair, expression, clothing, style
language, color temperature, and what
makes this character recognizable."

The output = your identity spec.
ChatGPT gave me core identity, visual
archetypes, style language, and the
exact consistency anchors to lock.

This becomes the blueprint for
everything that follows.
```

---

```
Slide 5:
STEP 4 — BUILD YOUR MASTER PROMPT

Take the AI analysis from Step 3
and turn it into a reusable prompt.

I used Claude to refine mine:

🧩 CROSS-AI WORKFLOW:
ChatGPT → generated the caricature
ChatGPT → analyzed the identity elements
Claude  → structured the master prompt
Gemini  → generates all future scenes

Your master prompt should lock:
→ Face + hair + expression (identity)
→ Clothing defaults (brand anchor)
→ Companion/symbols (visual recurring)
→ Color temperature rules
→ Art style + proportions
→ What MUST appear in every generation

THE FLOW:
Photo → Caricature → AI Analysis → Master Prompt
  📸      🎨           🔍              📋
            ↓
     Canonical → Any Scene
       🎯         🌍
```

---

```
Slide 6:
STEP 5 — EXTRACT YOUR CANONICAL IMAGE

A canonical = your character on a clean
background. No scene, no clutter.

Your MASTER REFERENCE for all generations.

🎯 EXTRACTION PROMPT:

"Using this reference, generate a clean
portrait of ONLY the character.
Head and upper body, three-quarter angle.
Same exact face, hair, smile, clothing.
Solid dark background (#0D1117),
no environment, no objects, no extras.
Semi-realistic caricature style.
This is a character reference sheet
for future generations."

Save it. Name it. Version it.
This file is your brand's visual DNA.
```

---

```
Slide 7:
STEP 6 — GENERATE SCENES (with guardrails)

Attach canonical + describe any scene.

But here's what NOBODY warns you about:
AI image generators misinterpret prompts.

🛡️ SCENE PROMPT (with Gemini guardrails):

"Using the attached canonical reference,
place this character in [SCENE].
Keep the EXACT same face and style.

IMPORTANT:
— Do NOT render any text on the image
— Visual motifs only, no literal code
  or fake UI screenshots
— Specify: 'realistic environment' or
  'illustrated environment' (pick one)
— Camera: [wide/medium/close-up]
— Mood: [sunset/dramatic/peaceful]
— Format: 1080×1350 (4:5 portrait)"

Without these guardrails, you get
random text, broken UI, and drift.
Ask me how I know.
```

---

```
Slide 8:
This isn't theory. This is my actual week.

📸 Took a selfie.
🎨 ChatGPT generated a caricature.
🔁 Iterated 5 times on the face.
🔍 ChatGPT analyzed the identity elements.
📋 Claude built my master prompt system.
🎯 Extracted the canonical image.
🌍 Gemini now generates me — anywhere.

Venice dinner with my girlfriend.
Paris at sunset. Parachuting over mountains.
Working at my desk with my AI robot.

3 AI tools. 1 system. Infinite outputs.

Did the same for Pauli in one afternoon.
Now we have duo scenes together.

The entire system: documented, versioned,
and reusable by any creator.
```

---

```
Slide 9:
AI can replace the 40 hours of design work.
It can't replace YOUR face, YOUR story,
or YOUR visual identity.

Build the system once.
Use it forever.

Found this useful?
→ Comment AVATAR and I'll send you
  my canonical image extraction prompt
→ Save this for when you build yours
→ Follow for more AI systems that
  actually work

— Fred 🚀
```
