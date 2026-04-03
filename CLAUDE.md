# Gym App — Claude Code Context

## Project Overview
Personal PWA strength training app for Cyril. Static HTML, dark theme, mobile-first.
No framework, no build step. Deploy via Netlify on push to main.

## URLs
- Live: https://cyrilmaire91-cmd.github.io/gym-app/ (also cyril-gym-app.netlify.app)
- Repo: https://github.com/cyrilmaire91-cmd/gym-app

## Stack
- Single-file static HTML PWA (`index.html`)
- Vanilla JS + CSS (no framework, no bundler)
- Dark theme throughout — no white backgrounds ever
- Mobile-first, touch-friendly
- Deployed via Netlify (auto-deploy on push to main)

## App Structure & Features

### Navigation
- Session tabs (Upper A, Upper B, Lower A, Lower B)
- Burger menu → Block switcher (WK 1-2 / WK 3-4 / Recovery)
- History tab
- Injury status system

### Training Program
- 4-day Upper/Lower split
- Week 1-2 vs Week 3-4 toggle (different exercises/rep schemes)
- Accordion set logging per exercise
- YouTube links on each exercise name
- Ambrose prehab protocols embedded in warm-ups
- Dynamic "Adapt" button → calls Anthropic API directly from browser for on-the-fly session modifications

### UI Components
- Rest timer — bottom bar, persistent across sets
- Burger menu with block switcher
- Injury status badges

## Athlete Profile (context for exercise logic)
- 37yo, trains 4×/week lunch breaks (45–70 min)
- Equipment: Hammer Strength, Panatta, Technogym
- Injuries: right TFCC wrist, patellar tendinopathy, golfer's elbow, left shoulder on fixed-path machines, limited hip abduction
- Morphology: ecto-mesomorph, long limbs (long femurs + forearms), central fat storage
- Key substitution chain: belt squat → hack squat → leg press
- Preferred: incline DB press over flat bench
- Priority weak points: rear delts, glutes, legs

## Design Rules
- Dark theme strict — background `#0f0f0f` or similar, never white
- Accent color: keep consistent with existing palette
- Mobile-first — all interactions thumb-friendly
- No external CSS frameworks
- Animations: subtle only, nothing flashy
- Keep the single-file architecture unless explicitly asked to split

## Feature Roadmap (Apr 2026)

### Quick Wins (do these first)
- [ ] Smart weight pre-fill (highest priority)
- [ ] Progress charts
- [ ] Session summary
- [ ] Haptic feedback
- [ ] Rest timer per exercise (distinct from global timer)

### Mid-term
- [ ] Pain log
- [ ] Plate calculator
- [ ] Focus mode
- [ ] Superset A1/A2 display
- [ ] Warm-up timer
- [ ] Bloc switcher improvements
- [ ] Muay Thai return tracker
- [ ] Weekly PDF export for physio (Ambrose)
- [ ] JSON export

### Long-term
- [ ] AI coaching (PB detection, stagnation alerts, auto-adapt)
- [ ] Sleep × performance correlation
- [ ] Tendon load curve visualisation
- [ ] iPad layout (board mode)
- [ ] Session share image
- [ ] MacroFactor export integration
- [ ] Multi-profile support

## Physio Context
- Physio: Ambrose (DPT/BHSc MSK, Muay Thai champion)
- Prehab protocols integrated in warm-ups
- Any rehab-related feature must be conservative and injury-aware

## Coding Conventions
- Keep everything in `index.html` unless explicitly asked to split files
- Use `localStorage` for persistence (weights, history, settings)
- No TypeScript, no build tools
- Comments in English
- CSS variables for theming — never hardcode colors inline
- Prefer progressive enhancement — app must work even if JS partially fails

## When Making Changes
1. Read the existing relevant section before modifying
2. Preserve all existing functionality — never remove features silently
3. Test on mobile viewport mentally (375px wide)
4. Keep the dark theme strictly — no light backgrounds introduced
5. If adding a new UI section, match the existing visual language exactly
