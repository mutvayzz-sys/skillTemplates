# GlitchCAP Labs — gcap.online Site Brief

## The Brand
- **Name:** GlitchCAP Labs (Glitch Cap Labs)
- **Domain:** gcap.online
- **Vibe:** Startup / AI lab / indie tech — cinematic, dark, immersive

---

## Design Direction (from inspo videos + cornrevolution.resn.global)
- Scrollytelling — scroll drives animations, video, 3D transitions
- Full-bleed cinematic hero — edge to edge, no padding
- Bold oversized condensed type overlaid on imagery/dark backgrounds
- Embedded interactive 3D (Spline or Three.js)
- Dark atmospheric backgrounds with dramatic lighting
- Particle / scatter / explode animations
- Editorial serif + italic mixed with modern sans
- Hover-triggered info reveals
- Overall feel: this is an EXPERIENCE, not a document

---

## Sections

### 1. Hero
- GlitchCAP Labs branding
- Cinematic full-bleed opening
- Sets the tone for the whole site

### 2. TayX-0.1 (Coming Soon)
- AI model dropping soon
- Based on: Xiaomi-Mini-2.5 + Kimi-2.6 + DeepSeek V4
- Context window: 1 million tokens
- Benchmarks: same as Claude Sonnet 3.5
- Framing: "Coming Soon" — tease it, make it feel major

### 3. Brainstack — AI Memory, Explained Simply
- Repo: https://github.com/yepyhun/Brainstack
- What it actually is: a structured memory system for AI agents
  - Instead of one big memory dump, it uses 5 "shelves":
    - Profile — who you are, your preferences
    - Continuity — what happened recently in this session
    - Transcript — the actual conversation history
    - Graph-truth — facts, relationships, things that change over time
    - Corpus — big external documents / knowledge
  - Pulls from the right shelf instead of flooding everything in at once
  - Built on Hindsight + Graphiti + MemPalace, unified for Hermes
- Explain this to a NORMAL PERSON — no jargon, visual metaphors

### 4. Kanbans in Hermes Agent
- Hermes Agent is the main orchestrator/runner
- Kanbans = task boards (like Trello) but inside the AI system
- Agents use them to track what needs doing, what's in progress, what's done
- Explain visually — make it feel intuitive

### 5. Conductor Role
- The Conductor is the orchestrator — the one in charge
- It directs other agents like a conductor directs an orchestra
- Visualized and explained — not just text
- Key idea: one brain coordinating many workers

### 6. TaySwarm
- Inspired by / equivalent to: https://github.com/swarmclawai/swarmclaw
- Called TaySwarm (Matvey's version)
- What it is: a team of AI agents that self-organize and collaborate
- Agents delegate to each other, have roles, work in parallel
- Self-hosted, multi-provider, MCP-native

### 7. GlitchLand (Game)
- Inspired by: https://github.com/pablodelucca/pixel-agents
- Pixel art game interface where AI agents are animated characters
- Characters walk around, sit at desks, visually reflect what they're doing
- Typing when coding, reading when searching, idle when waiting
- Matvey's version: GlitchLand

---

## Tech Stack (to decide)
- Pure HTML/CSS/JS (Vanilla, maximum control for animations)
- OR: Next.js + Framer Motion + Spline
- Animations: GSAP + ScrollTrigger for scrollytelling
- 3D: Spline embeds or Three.js
- Particles: tsParticles or custom canvas

---

## Files in this folder
- BRIEF.md — this file (project overview)
- NOTES.md — running notes as we build
- /site — the actual site code
