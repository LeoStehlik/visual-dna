# design-dna

Turn any reference design into a structured, reusable Design DNA JSON. Apply it to any content. Reuse it everywhere.

Extract visual identity from screenshots, images, or URLs across three dimensions: design tokens, qualitative style, and visual effects. Then generate faithful implementations from that DNA. Works with any agent - Claude Code, Codex, OpenClaw, Cursor.

Inspired by [zanwei/design-dna](https://github.com/zanwei/design-dna). Built and adapted for use in our OpenClaw workflow.

---

## The Three Dimensions

| Dimension | What it captures |
|-----------|-----------------|
| **design_system** | Colour, typography, spacing, layout, shape, elevation, motion, components |
| **design_style** | Mood, visual language, composition, brand voice, interaction personality |
| **visual_effects** | Canvas, WebGL, particles, shaders, scroll effects, SVG animations |

---

## Three Phases

**Analyze** - give it screenshots, images, or URLs. Get back a complete Design DNA JSON.

**Generate** - give it DNA JSON + your content. Get back a self-contained HTML/CSS/JS implementation that faithfully matches the reference.

**Structure** - ask to see the full schema. Useful before starting a new extraction.

Phases can be chained or used standalone.

---

## Why it matters

"Make it look like that site" is not a spec. Design DNA JSON is.

Once extracted, the JSON can be:
- Committed to version control
- Shared across teams
- Fed to any agent for any future generation
- Refined incrementally as the brand evolves

---

## Pair with no-slop-ui

Design DNA tells agents WHAT the design is.
[no-slop-ui](https://github.com/LeoStehlik/no-slop-ui) tells agents what NOT to do.

Together: faithful to reference, clean execution, no AI defaults slipping in.

---

## Installation

### OpenClaw

Add your workspace skills directory to `openclaw.json`:

```json
{
  "skills": {
    "load": {
      "extraDirs": ["/path/to/your/skills"]
    }
  }
}
```

Clone into that directory:

```bash
git clone https://github.com/LeoStehlik/design-dna.git /path/to/your/skills/design-dna
```

### Claude Code / Codex

Copy the `design-dna` folder into `.agents/skills/` or `.claude/skills/`.

---

## Usage

```
Analyse this website and extract its Design DNA: https://example.com
```

```
I have this Design DNA JSON. Build me a landing page for [product] in this style: [paste JSON]
```

```
Extract the design DNA from this screenshot and generate a matching dashboard for our data
```

---

## What's Inside

```
design-dna/
├── SKILL.md                           Core workflow + phase instructions
└── references/
    ├── schema.md                      Full Design DNA JSON schema
    └── generation-guide.md            How to apply DNA to generate UI
```

---

## License

MIT - see [LICENSE](LICENSE)
