# MoodCook — Master Design Prompt (v2.0 "Flavor & Feeling")

> **How to use this file.**
> - **Claude Design / Figma AI / v0 / Lovable:** paste §1–§6 as the system brief, then paste one screen block from §7 per artboard.
> - **Google Stitch:** Stitch prefers shorter prompts. Paste the **STITCH BLOCK** at the end of each screen in §7 — it is self-contained and already carries the palette and type tokens.
> - **Everything in §7 is mandatory.** All 25 screens must exist in the final file. Nothing here is optional.
> - Screens 1–12 are redesigns of what already ships. Screens 13–25 are new.

---

## 1. PRODUCT BRIEF

**MoodCook** is a mood-first cooking companion. You tell it (or it detects) how you feel, and it answers with food — a recipe, a drink, a 10-minute rescue meal — plus an AI sous-chef that cooks alongside you.

- **Category:** Food & Drink with a wellness crossover
- **Platform:** iOS + Android (React Native), portrait-first, **393×852** design frame (iPhone 15 / Pixel 8 class). Must degrade gracefully to 375×667.
- **Audience:** 18–34, emotionally literate, cooks 3–5×/week, phone-in-hand in the kitchen, short attention span, greasy fingers.
- **Emotional promise:** *"Cook how you feel."* Warm, playful, never clinical. A friend who happens to be a chef — not a diet app, not a mood tracker with a clipboard.
- **Anti-goals:** no calorie shaming, no clinical mental-health framing, no beige minimalism, no stock-photo grid of sad salads.

---

## 2. ART DIRECTION

**The look: "Warm Kitchen Brutalism."** Confident chunky type, thick soft-rounded cards, saffron heat against cream, one bold accent per screen that shifts with the user's mood. Food photography is the hero and is always full-bleed, never floating in whitespace. UI chrome is flat and matte so the food reads glossy by contrast.

**Visual pillars**

1. **Big food, small chrome.** Imagery gets 40–60% of every browse screen. Controls stay compact and hug the edges.
2. **Mood is a color, not a label.** Accent, background tint, gradient, and icon weight all shift per mood. A "stressed" screen and a "happy" screen must be distinguishable from across the room.
3. **Steam, sizzle, bubble.** The motion language is borrowed from cooking: things rise, wobble, pour, and settle. Nothing slides in flatly from the right.
4. **Handmade marks.** Sparse hand-drawn accents — a squiggle underline, a rough circle around the selected mood, a dotted "cut here" line on the shopping list. Ink-black, 2px, deliberately imperfect.
5. **Grain.** A 3% monochrome noise overlay on all solid color fields. Kills the sterile flat-vector feel.

**Photography direction:** overhead or 45°, natural window light from the left, real ceramic and linen, visible crumbs and drips, warm white balance (~5200K). Warm grade: shadows lifted +5, saturation +8 on reds and yellows only.

**Illustration direction:** for empty states and onboarding — flat vector, 3 colors max (cream + mood accent + charcoal ink), thick 3px ink outline offset 1px from the fill, like misregistered risograph printing.

---

## 3. DESIGN SYSTEM

### 3.1 Core palette

| Token | Hex | Use |
|---|---|---|
| `saffron/500` | `#F4C149` | Primary brand, header bar, primary buttons |
| `saffron/600` | `#E8AE2A` | Primary pressed |
| `ember/500` | `#F3891B` | Secondary accent, button borders, streak flame |
| `ember/600` | `#D9740B` | Ember pressed |
| `charcoal/900` | `#16130E` | Primary text, ink outlines |
| `charcoal/600` | `#4A4238` | Secondary text |
| `charcoal/400` | `#8B8175` | Tertiary text, placeholders |
| `cream/50` | `#FFFBF2` | App background (light) |
| `cream/100` | `#F7F0E1` | Card background, input fill |
| `cream/200` | `#EDE3D0` | Dividers, hairline borders |
| `white` | `#FFFFFF` | Elevated surfaces |
| `success/500` | `#4CAF50` | Confirmations |
| `danger/500` | `#D32F2F` | Destructive only |
| `info/500` | `#3B82F6` | Informational, links |

### 3.2 Mood palette (drives per-screen theming)

Five moods. **This is the canonical set — do not substitute.**

| Mood | Emoji | Accent | Tint (bg wash) | Gradient | Personality |
|---|---|---|---|---|---|
| **Happy** | 😊 | `#FFC53D` | `#FFF6DF` | `#FFC53D → #FF9E45` | Bright, celebratory, sweet |
| **Sad** | 😢 | `#5B7FA8` | `#EEF3F9` | `#5B7FA8 → #7BA3CC` | Soft, comforting, slow |
| **Bored** | 😐 | `#8B5CF6` | `#F3EEFE` | `#8B5CF6 → #C084FC` | Novel, surprising, weird |
| **Stressed** | 😫 | `#6FA287` | `#EDF5F1` | `#6FA287 → #9BC4AC` | Calm, simple, few steps |
| **Angry** | 😠 | `#E4572E` | `#FDEEE9` | `#E4572E → #FF8A5B` | Loud, spicy, physical |

**Theming rule:** when a mood is active, the screen background becomes the mood **tint**, the primary CTA becomes the mood **accent**, and progress/selection indicators use the mood **gradient**. The saffron header bar stays saffron always — it is the brand anchor.

### 3.3 Dark mode

| Token | Dark value |
|---|---|
| Background | `#141210` |
| Card surface | `#1F1B17` |
| Elevated | `#2A241E` |
| Primary text | `#F7F0E1` |
| Secondary text | `#A79C8C` |
| Divider | `#332C24` |

Saffron stays `#F4C149` but drops to 90% opacity on large fills. Mood tints become 12%-opacity washes of the accent over the dark background. Food imagery is never dimmed.

### 3.4 Typography

| Role | Family | Size / Line / Weight / Tracking |
|---|---|---|
| Display | Montserrat ExtraBold | 34 / 38 / 800 / −1.5% |
| H1 | Montserrat Bold | 26 / 32 / 700 / −1% |
| H2 | Montserrat Bold | 20 / 26 / 700 / −0.5% |
| H3 | Montserrat SemiBold | 17 / 22 / 600 / 0 |
| Body L | Montserrat Regular | 16 / 24 / 400 / 0 |
| Body M | Montserrat Regular | 14 / 21 / 400 / 0 |
| Caption | Montserrat Medium | 12 / 16 / 500 / +1% |
| **Mono / brand** | **Fragment Mono Regular** | 13 / 18 / 400 / +2% |
| Mono numeric | Fragment Mono Regular | 48 / 52 / 400 / 0 |

**Fragment Mono is the signature.** Use it for the wordmark, all micro-labels (`ingredients`, `12 min`, `step 3 of 7`), timers, prices, streak counts, and any lowercase system text. It is what keeps MoodCook from looking like every other recipe app. Never use it for paragraphs longer than two lines.

*Substitutes if unavailable:* Fragment Mono → Space Mono → JetBrains Mono. Montserrat → Poppins → Inter.

**Casing rule:** section headers are `UPPERCASE` Montserrat Bold with +4% tracking. Micro-labels are `all lowercase` Fragment Mono. Never sentence-case a section header.

### 3.5 Spacing, radius, elevation

- **Grid:** 8pt base. Scale `4 / 8 / 12 / 16 / 24 / 32 / 48 / 64`.
- **Screen gutter:** 20px. Full-bleed elements ignore it entirely (edge-to-edge, zero margin).
- **Radius:** `sm 8` (chips, inputs) · `md 16` (buttons, small cards) · `lg 24` (content cards, sheets) · `xl 32` (hero cards, modals) · `full 999` (avatars, pills, FAB).
- **Elevation:** shadows are warm, never gray. `0 4px 16px rgba(90,60,20,0.10)` for cards, `0 12px 32px rgba(90,60,20,0.16)` for sheets and modals, and `0 2px 0 #16130E` — a hard offset with no blur — for the "pressed ink" style on primary buttons. That hard shadow is a signature; use it consistently.
- **Borders:** 2px `charcoal/900` on primary buttons and selected states. 1px `cream/200` on neutral cards.

### 3.6 Iconography

24×24, 2px stroke, rounded caps and joins, `charcoal/900`. A custom set is required for: the five mood faces, pantry, chat-bubble-with-whisk, camera-with-sparkle, flame/streak, bookmark, timer, shopping basket, sparkle (AI), mic, chef hat, chart.

**AI marker:** every AI-powered affordance carries a 4-point sparkle glyph in the mood accent, at 60% the size of the adjacent icon, positioned top-right. This sparkle is the single consistent signal that a model produced something.

### 3.7 Layout skeleton

- **Top bar (56px):** saffron `#F4C149`, full-bleed edge-to-edge (no inset, no percentage-width hacks), logo left 32×32, `hi, {name}` in Fragment Mono 13 plus a 32×32 circular avatar right.
- **Bottom tab bar (64px + safe area):** five tabs — **Today** (home), **Discover** (compass), **Cook** (center, elevated 56px circular FAB in the mood accent with a sparkle), **Journal** (chart), **You** (avatar). Active: filled icon plus a 4px dot beneath in the mood accent. Inactive: 2px stroke, `charcoal/400`.
- **Footer credit:** keep `created by avg` in Fragment Mono 12 `charcoal/400`, centered — but only on Splash, Onboarding, and the About row in Settings. Remove it from every scrolling screen.

---

## 4. MOTION SYSTEM

Motion is a first-class requirement. Every screen in §7 names its entrance, its idle life, and its exit.

### 4.1 Curves and durations

| Name | Curve | Duration | Use |
|---|---|---|---|
| `swift` | cubic-bezier(0.2, 0, 0, 1) | 200ms | Taps, toggles, chips |
| `settle` | spring(stiffness 220, damping 26, mass 1) | ~420ms | Cards, sheets, mood selection |
| `pour` | cubic-bezier(0.45, 0, 0.15, 1) | 520ms | Screen transitions, hero expands |
| `wobble` | spring(stiffness 380, damping 12) | ~600ms | Playful confirmations, streaks, favoriting |
| `simmer` | ease-in-out, infinite alternate | 3000ms | Ambient idle loops |

**Never use linear.** **Never exceed 600ms** for a user-initiated transition.

### 4.2 Signature motions — design these explicitly

1. **Steam rise** — three translucent white wisps (blur 8, opacity 0.0→0.35→0.0) drifting up 40px over 3s, staggered 400ms, looping. Sits behind headers on Splash, Cook Mode, and any "hot" recipe card. This is the app's ambient signature.
2. **Mood morph** — on mood change, the background tint cross-fades over 520ms `pour` while the accent animates through **HSL** space (not RGB — RGB interpolation muddies the midpoint). The previously selected card shrinks to 0.92 as the new one springs 1.06 → 1.0 on `wobble`.
3. **Ink circle** — selecting a mood draws a rough hand-drawn circle around it: an SVG path with stroke-dashoffset animating 0→100% over 400ms `swift`, 3px charcoal, overshooting the start point slightly like a real pen.
4. **Card bloom** — grid tiles enter with opacity 0→1, scale 0.94→1, translateY 12→0, staggered 60ms in reading order, on `settle`.
5. **Bookmark pop** — the icon scales 1→0.8→1.25→1 on `wobble`, emits six tiny particles in the mood accent radiating 24px and fading, plus a light haptic.
6. **Shared-element hero** — tapping a tile expands that exact image into the detail hero over 520ms `pour`; title and body fade and rise 16px, delayed 120ms.
7. **Sizzle progress** — loading bars are a saffron→ember gradient with a 2px vertical shimmer traveling left-to-right every 1.2s. AI thinking states use three dots rising and falling like bubbles in a pot, 400ms apart.
8. **Pull-to-refresh: the pan flip** — a pancake illustration flips 360° on the Y axis as you pull, completing exactly at the release threshold.
9. **Skeletons** — never gray boxes. `cream/100` shapes with a saffron-tinted shimmer sweep, 1.4s loop, 20° angle.
10. **Number rolls** — timers, streaks, prices, and stats animate digit-by-digit on a vertical odometer roll, 240ms `swift` per digit, staggered 40ms.

### 4.3 Haptics (annotate these on the design)

Light on selection · Medium on favorite and step-complete · Success notification on recipe finished and subscription confirmed · Warning on destructive confirm · **No haptic on scroll or navigation.**

### 4.4 Reduced motion

When "reduce motion" is on: all transforms become cross-fades at 160ms, steam and shimmer stop, odometers snap. Content and hierarchy must remain fully legible with zero animation.

---

## 5. COMPONENT LIBRARY

Build each of these as a reusable component with the listed variants and states.

1. **Button** — variants: `primary` (mood-accent fill, 2px charcoal border, 2px hard offset shadow, radius 16, height 52), `secondary` (cream fill, charcoal border), `ghost` (text plus squiggle underline), `destructive` (danger fill), `ai` (charcoal fill, mood-accent sparkle, subtle animated gradient sheen). States: default / pressed (translateY +2, shadow collapses to 0) / disabled (60% opacity) / loading (label swaps to three bubbling dots).
2. **Mood chip** — pill, 20px emoji plus lowercase Fragment Mono label. States: idle / selected (accent fill plus ink circle) / disabled.
3. **Mood card** — 1:1, radius 24, 44px emoji centered, label below, accent-tint fill. Selected adds the ink circle and scales to 1.03.
4. **Recipe tile** — square, full-bleed image, radius 20, bottom scrim `transparent → rgba(22,19,14,0.72)`, title Montserrat Bold 15 white, meta row Fragment Mono 11 white 80% (`18 min · easy`), bookmark on a 32px blurred circle top-right, mood dot top-left.
5. **Recipe row** — horizontal; 96×96 image left at radius 16, title + description + meta right, chevron.
6. **Input** — height 52, radius 12, `cream/100` fill, 1px `cream/200` border. On focus the label floats up 8px and shrinks to Fragment Mono 11, and the border becomes 2px in the mood accent. The password variant uses the eye / eye-off SVG toggle — never an emoji.
7. **Segmented filter bar** — horizontally scrolling chip row, 8px gaps, sticky under the header on a cream blur backdrop.
8. **Bottom sheet** — 32 radius on top corners, 4×40 grab handle, backdrop `rgba(22,19,14,0.45)` with 8px blur, springs up on `settle`, drag to dismiss.
9. **AI message bubble** — user: mood-accent fill, right-aligned, radius 20 with 4 at bottom-right. AI: cream fill with a 1px accent border, left-aligned, radius 20 with 4 at bottom-left, sparkle at top-left. Streaming shows a blinking 2px caret.
10. **Stat tile** — Fragment Mono 32 number (odometer), caption label, sparkline, mood-tint background.
11. **Toast** — top, radius 16, slides down and settles, auto-dismiss at 3s; success / danger / warning / info variants.
12. **Paywall feature row** — 24px icon, bold title, one-line description, saffron check.
13. **Timer pill** — Fragment Mono 20 countdown inside a circular progress ring, tap to pause.
14. **Streak flame** — animated ember-gradient flame flickering on `simmer`.
15. **Empty state** — riso-style illustration, H2, one line of body, one primary button.

---

## 6. THE FIVE AI FEATURES

Each has a name, a surface, a visible input, a visible output, and a failure state. Every AI surface must show: (a) the sparkle marker, (b) a streaming/thinking state, (c) an "AI can be wrong — check before you cook" disclaimer in Fragment Mono 11, and (d) a thumbs-up / thumbs-down feedback pair on every generated result.

### AI-1 · MoodLens — mood detection
**Surface:** Screen 7. **Input:** front camera selfie, a free-text journal line, or both. **Output:** a ranked mood guess with a confidence ring (e.g. `stressed — 78%`), two runner-up moods as chips, and a one-line rationale in the AI's voice ("your words leaned tired and rushed"). **Design requirements:** an on-device-processing badge, a large "use this mood" primary CTA, and an always-present "pick manually instead" ghost button. **Failure:** low confidence (<50%) collapses to the manual mood grid with the copy "I'm not sure — you tell me."
**Privacy UI is mandatory:** a lock glyph plus `analyzed on device · photo never uploaded`.

### AI-2 · Sous-Chef — conversational cooking assistant
**Surface:** Screens 11 (full chat) and 10 (docked while cooking). **Input:** text, voice (hold-to-talk mic), or quick-reply chips (`substitute an ingredient`, `halve this recipe`, `what can I do while this simmers?`). **Output:** streaming chat with rich cards inline — a substitution card, a converted-measurements table, a mini recipe card. **Design requirements:** the mic button pulses with a live waveform ring while recording; the assistant has a small chef-hat avatar that blinks on `simmer`; hands-free mode shows extra-large text and a persistent "next step" voice affordance.

### AI-3 · PantryVision — photo-to-ingredients
**Surface:** Screen 12. **Input:** a photo of a fridge shelf, counter, or pantry (or a barcode). **Output:** detected ingredients as removable chips with per-item confidence, an editable "add missing" field, then a ranked list of recipes labeled `you have everything` / `missing 2`. **Design requirements:** the scanning state overlays the photo with animated corner brackets and a saffron sweep line; detected items pop in one by one with a light haptic; each chip is long-pressable to correct the label.

### AI-4 · FlavorForge — generative recipe creation
**Surface:** Screen 13. **Input:** mood (pre-filled), plus dials for time, spice, effort, and servings; a pantry toggle ("only what I have"); and an optional free-text wish ("something warm I can eat with one hand"). **Output:** a fully generated recipe — title, hero image, blurb, ingredients, numbered steps, time and difficulty — presented as a card that can be saved, cooked, or re-rolled. **Design requirements:** a prominent **"remix" dice button** that regenerates with the same constraints; a generation animation where ingredients illustration-fly into a bowl and the title types itself out; a "3 of 5 free generations left today" counter in Fragment Mono that links to the paywall.

### AI-5 · TasteGraph — personalization and insight engine
**Surface:** Screen 19 (visible) and Screen 8 (invisible, ranks the feed). **Input:** mood check-in history, cooked recipes, favorites, skips, ratings, time of day. **Output:** (a) the Today feed ordering with a "why am I seeing this?" explainer chip on every card; (b) correlation insights ("you cook 3× more on stressed evenings — and you rate the 15-minute recipes highest"); (c) a predictive nudge ("Thursdays run stressed for you — want a 15-minute plan ready?"); (d) a weekly AI recap card. **Design requirements:** every insight must be plain-language, never a raw statistic; charts always pair with one sentence of interpretation; include a "this isn't right" correction control on each insight.

---

## 7. THE 25 SCREENS

Tags: `[EXISTING]` = redesign of a shipping screen · `[NEW]` = net-new.

---

### 1 · SPLASH `[EXISTING]`
**Purpose:** brand moment while auth state resolves. Max 1.5s — never a fixed timeout that stalls a signed-in user.
**Layout:** full-bleed `cream/50` with a very soft radial saffron glow behind center. Logo mark 120×120 centered. Wordmark `moodcook` in Fragment Mono 18, +6% tracking, 24px below. A 3px saffron progress hairline pinned 96px from the bottom. `created by avg` in Fragment Mono 12 at the bottom safe area.
**Motion:** logo enters at scale 0.7 → 1.04 → 1.0 on `wobble` with opacity 0→1; wordmark letters fade in staggered 40ms each; **steam rise** loops behind the logo; the progress hairline fills with the sizzle shimmer. Exit: whole screen scales to 1.06 and fades over 300ms `pour` into the next screen.
**States:** first-launch → Onboarding · signed-out → Sign In · signed-in with today's mood → Today · signed-in without today's mood → Mood Check-In.
> **STITCH BLOCK:** Mobile splash screen, 393×852. Warm cream background #FFFBF2 with a soft radial saffron #F4C149 glow behind the center. A 120px circular logo mark of a magnifying glass over a chef's pan, centered. Below it the wordmark "moodcook" in a lowercase monospace font, letter-spaced. A thin 3px saffron progress line near the bottom. Tiny caption "created by avg" at the very bottom in monospace. Three soft translucent steam wisps rising behind the logo. Minimal, warm, playful, grainy texture overlay.

---

### 2 · ONBOARDING CAROUSEL `[NEW]`
**Purpose:** sell the premise in three swipes before asking for anything.
**Layout:** three full-screen slides, each with a 320×320 riso illustration on top, Display headline, two lines of Body L, and a fixed bottom bar with a 3-dot indicator (active dot is a 24px saffron pill), a `skip` ghost link left, and a circular 56px `next` FAB right that becomes a full-width `get started` button on slide 3. Each slide's background is a different mood tint, so swiping visibly changes the app's color.
**Copy:**
- Slide 1 — **"Cook how you feel."** / *Tell us your mood. We'll answer with dinner.*
- Slide 2 — **"An AI sous-chef in your pocket."** / *Ask anything mid-cook. Swap an ingredient. Halve a recipe. Hands-free.*
- Slide 3 — **"Your fridge, understood."** / *Snap what you have. Get what you can make. Right now.*
**Motion:** parallax — illustration moves at 1.2× the swipe distance, text at 0.8×, background tint cross-fades continuously as you drag (not on release). Each illustration has one looping element (a whisk stirring, steam, a blinking eye). The `next` FAB morphs width to become the slide-3 button over 420ms `settle`.
> **STITCH BLOCK:** Mobile onboarding carousel, 393×852, three slides. Each slide: a large flat-vector risograph-style illustration (3 colors, thick charcoal outlines, slightly misregistered) filling the top 45%, a bold Montserrat headline, two lines of gray body text, and a bottom bar with three dot indicators where the active one is a stretched saffron pill, a "skip" text link on the left and a round yellow next button on the right. Slide backgrounds are pale mood tints: warm cream, pale blue, pale lavender. Warm, playful, grainy.

---

### 3 · SIGN UP `[EXISTING]`
**Layout:** 72px logo top-center; H1 `CREATE AN ACCOUNT` uppercase, centered, with a hand-drawn saffron squiggle underline. Four floating-label underline inputs (name, email, password, confirm password) at 280px wide, 20px apart. Password fields carry the eye/eye-off SVG toggle. A live password-strength meter under the password field — a 4-segment bar that fills saffron→ember, with a Fragment Mono label (`weak` / `getting there` / `solid`). Below: an inline `passwords match ✓` in success green. Primary `register` button. Divider `or` with hairlines. Two social buttons (Google, Apple) as 52px cream pills with a charcoal border. Bottom: `already have an account? login here`.
**States:** idle · focused (label floats, 2px saffron border) · error (2px danger border + Fragment Mono 11 message below, field shakes ±6px twice over 240ms) · loading (button label becomes bubbling dots) · success toast.
**Motion:** fields stagger in 60ms apart on `settle`; the strength meter segments fill with `swift`; on successful submit the button collapses into a circle, shows a check, then the screen wipes upward.
> **STITCH BLOCK:** Mobile sign-up screen, 393×852, warm cream #FFFBF2 background. Small chef-pan logo at top. Bold uppercase heading "CREATE AN ACCOUNT" with a hand-drawn yellow squiggle underline. Four underline-style text fields with floating labels: name, email, password, confirm password, each 280px wide, password fields with an eye icon on the right. A four-segment password strength bar in yellow-to-orange under the password field. A wide yellow "register" button with a 2px black border and a hard 2px black offset shadow. An "or" divider, then two outlined social login buttons. Small monospace footer "already have an account? login here". Warm, chunky, friendly.

---

### 4 · SIGN IN `[EXISTING]`
**Layout:** 180px logo, `moodcook` wordmark in Fragment Mono 16, and the tagline *"Discover recipes that match your mood. Let your feelings guide your cooking."* in Fragment Mono 12, centered, 3 lines, 22px line-height. Two boxed inputs (`email or username`, `password` with eye toggle) at 285px. A `forgot password?` ghost link right-aligned under the password field. Primary `sign in` button. Biometric row: a 48px Face ID / fingerprint circle button with the Fragment Mono label `use face id`. Bottom: `don't have account yet? register here`.
**States:** idle · loading (`signing in...`) · error toast at top · biometric prompt overlay.
**Motion:** logo does a slow 3s `simmer` breathe (scale 1.0 ↔ 1.02); steam wisps behind it; error toast slides down and settles.
> **STITCH BLOCK:** Mobile login screen, 393×852, cream background. Large 180px chef-pan-and-magnifier logo centered at top, the lowercase monospace wordmark "moodcook" beneath, then three centered lines of small monospace tagline text. Two rounded rectangular input fields with thin borders: "email or username" and "password" with an eye icon. A small right-aligned "forgot password?" link. A wide saffron yellow "sign in" button with a black border and hard offset shadow. Below, a circular Face ID button with the monospace label "use face id". Tiny footer "don't have account yet? register here". Warm, minimal, grainy.

---

### 5 · TASTE PROFILE SETUP `[NEW]`
**Purpose:** a 4-step wizard that makes every later AI output personal. Runs once after sign-up; editable later from Settings.
**Layout:** a 4-segment progress bar pinned under the header (filled segments use the mood gradient). H1 question, one line of helper text, then a selection area. A sticky bottom bar with `back` ghost and `continue` primary; step 4's CTA reads `start cooking`.
**Steps:**
1. **Diet** — 6 selectable cards in a 2×3 grid with icons: everything, vegetarian, vegan, halal, pescatarian, keto. Multi-select.
2. **Allergies & dislikes** — a chip cloud (nuts, dairy, gluten, shellfish, egg, soy, spice) plus a free-text "anything else?" field. Selected chips turn danger-red with a strikethrough on the label — a deliberate, memorable inversion.
3. **Skill & time** — two custom sliders. Skill is a 3-stop slider with an emoji thumb that changes face (🥄 → 🔪 → 👨‍🍳). Time is a dial from 10 to 90 minutes with a Fragment Mono 48 numeric readout that odometer-rolls as you drag.
4. **Kitchen** — a grid of toggleable equipment tiles (oven, microwave, blender, air fryer, rice cooker, none of these). Unselected tiles are grayscale; selected snap to full color.
**Motion:** the progress segment fills left-to-right on `pour` at each step advance; the outgoing question slides left 24px and fades while the next rises 24px and fades in; slider thumbs use `wobble` on release; the equipment tile flips on its Y axis when toggled.
> **STITCH BLOCK:** Mobile onboarding questionnaire screen, 393×852, cream background. A four-segment progress bar at the top with the first two segments filled in a yellow-to-orange gradient. A bold heading "What do you eat?" and a line of gray helper text. A 2×3 grid of selectable cards with icons and labels: everything, vegetarian, vegan, halal, pescatarian, keto — one card selected with a yellow fill, a 2px black border and a hand-drawn circle around it. A sticky bottom bar with a ghost "back" button and a wide yellow "continue" button with a hard black offset shadow. Warm, chunky, friendly.

---

### 6 · MOOD CHECK-IN `[EXISTING — was MoodRegister]`
**Purpose:** the emotional front door. Must be the most beautiful screen in the app.
**Layout:** **the saffron header bar is required here** (it is missing today). Below it, a Fragment Mono 13 date line `tuesday · 6:40 pm`, then Display headline **"how are you feeling?"** left-aligned with a squiggle under "feeling". Then a **2 / 2 / 1 mood grid** where cards are `width: 47%` with a 1:1 aspect ratio — **percentage-based, never a fixed 150px**, so it never collapses to one column on a 375pt screen. The fifth card is centered and full-width-half. Each card: 44px emoji, lowercase Fragment Mono label, mood-tint fill, radius 24. Beneath the grid: a secondary `let AI read my mood` button with a sparkle that routes to Screen 7. At the bottom, a `skip for now` ghost link.
**Motion:** cards bloom in staggered 60ms. Hovering/pressing lifts a card 4px. On selection: **ink circle** draws, the card springs to 1.06 → 1.0 on `wobble`, the whole screen's background morphs to that mood's tint over 520ms, the emoji does a single 8° wiggle, medium haptic fires, and after 400ms the screen auto-advances to Today with a shared-element transition that carries the selected card's color as an expanding circular wipe.
**Empty/edge:** if the user already checked in today, the screen shows the current mood pre-selected with the copy `feeling different now?` and a `keep it` button.
> **STITCH BLOCK:** Mobile mood selection screen, 393×852, cream background with a full-width 56px saffron yellow top bar containing a small logo, the text "hi, gilbert" in monospace and a round avatar. Below: a small monospace date line, then a large bold heading "how are you feeling?" with a hand-drawn yellow squiggle under one word. Then a grid of five square mood cards, two per row with the fifth centered: happy with 😊 on pale yellow, sad with 😢 on pale blue, bored with 😐 on pale lavender, stressed with 😫 on pale green, angry with 😠 on pale coral. Each card has a large emoji and a lowercase monospace label, rounded 24px corners. One card is selected with a rough hand-drawn ink circle around it. Below the grid a dark secondary button "let AI read my mood" with a sparkle icon. Warm, playful, grainy.

---

### 7 · AI MOOD SCAN — MoodLens `[NEW · AI-1]`
**Layout:** near-full-bleed camera viewfinder with rounded 32px corners inset 12px. Animated corner brackets frame the face. A mode toggle pill floats at the top: `face` | `journal`. In `journal` mode the viewfinder is replaced by a cream card with a large multi-line text area and the prompt *"how was your day? one line is enough."* Bottom sheet holds: a 72px circular shutter with a sparkle, the privacy row (`🔒 analyzed on device · photo never uploaded`), and a `pick manually instead` ghost link.
**Result state:** the viewfinder shrinks to a 120px rounded thumbnail top-left; a large **confidence ring** (circular progress, mood gradient, Fragment Mono 48 percentage in the center) and the detected mood name in Display; one line of rationale in Body M; two runner-up mood chips labeled `or maybe...`; primary `use this mood` and ghost `try again`; and a thumbs-up/down feedback pair.
**Motion:** scanning shows a saffron sweep line traveling down the viewfinder every 1.2s with brackets pulsing on `simmer`; on result, the ring fills 0→N% over 900ms `pour` while the percentage odometer-rolls, then the mood tint floods the background from the ring outward as a circular wipe.
**Failure:** no face detected → illustration + "I can't see you clearly — try better light, or just tell me." Confidence <50% → auto-fallback to the manual grid.
> **STITCH BLOCK:** Mobile AI mood-detection screen, 393×852. A near-fullscreen camera viewfinder with 32px rounded corners showing a young person's face, with animated white corner brackets and a horizontal saffron scan line. A floating pill toggle at the top with two options "face" and "journal". At the bottom a cream sheet with a large 72px circular shutter button in saffron yellow with a sparkle icon, a small monospace privacy line with a lock icon reading "analyzed on device · photo never uploaded", and a ghost link "pick manually instead". Warm, futuristic but friendly, grainy.

---

### 8 · TODAY (DASHBOARD) `[EXISTING]`
**Purpose:** the home feed, ranked by TasteGraph.
**Layout (scrolling, background = current mood tint):**
1. Saffron header bar.
2. **Greeting block** — `gilbert,` in H2 lowercase, then `your current mood is happy.` with the mood word in the mood accent, bold, and a small tappable pencil icon to re-check-in.
3. **Mood quote card** — full-width, radius 24, mood-gradient fill, the rotating quote in Montserrat Italic 17 white with a large decorative quotation mark at 30% opacity, and a `↻` reshuffle button in the corner.
4. **"for your mood" section** — UPPERCASE section header plus a `see all` link, then a 2×2 recipe-tile grid. Every tile carries a small `why?` chip that opens a TasteGraph explainer sheet.
5. **AI strip** — a horizontally scrolling row of three action cards, each 160×120 with a charcoal fill and a mood-accent sparkle: `scan my fridge`, `make me something new`, `ask sous-chef`.
6. **"quick tonight" section** — a horizontal carousel of recipe tiles filtered to under 20 minutes.
7. **Streak strip** — a slim card with the animated flame, `7 day streak`, and a mini 7-dot week tracker.
8. Two legacy full-width buttons, restyled: `see other happy recipes` and `see all recipes` — now secondary cream buttons with a charcoal border and a right chevron.
9. Bottom tab bar.
**Motion:** header greeting fades and rises on load; the quote card's gradient slowly pans on `simmer`; tiles bloom staggered; the reshuffle button spins 180° and the quote cross-fades; pull-to-refresh runs the pan flip.
**States:** loading skeletons for every block · no-mood-yet (replaces blocks 2–4 with a "check in to see your recipes" prompt) · no-results (illustration plus `explore all recipes`).
> **STITCH BLOCK:** Mobile recipe home feed, 393×852, pale warm background. A full-width 56px saffron top bar with a small logo, "hi, gilbert" in monospace, and a round avatar. Below: a bold lowercase greeting "gilbert," and a second line "your current mood is happy" with the word happy in bold amber. Then a full-width rounded card with a yellow-to-orange gradient containing an italic inspirational quote in white and a large faded quotation mark. Then an uppercase section label "FOR YOUR MOOD" with a "see all" link, and a 2×2 grid of square food photo tiles with rounded corners, dark bottom gradients, white bold titles and small monospace meta text like "18 min · easy", each with a bookmark icon in a blurred circle. Then a horizontal row of three dark action cards with sparkle icons reading "scan my fridge", "make me something new", "ask sous-chef". Then a slim streak card with an orange flame and "7 day streak". A bottom tab bar with five icons and a raised center circular button. Warm, food-forward, grainy.

---

### 9 · RECIPE DETAIL `[EXISTING]`
**Layout:**
1. **Collapsing hero** — full-bleed food photo, 380px tall, collapsing to a 56px saffron bar on scroll. Overlaid: a back button and a share button on 40px blurred circles, and a mood dot chip bottom-left (`for: happy`).
2. **Content card** — overlaps the hero by −28px, radius 32 top, `cream/50` fill.
3. **Title row** — H1 recipe name, plus a 44px bookmark/star button top-right that runs the bookmark-pop animation.
4. **Description** in Body M `charcoal/600`.
5. **Meta strip** — three Fragment Mono stat pills separated by hairlines: `18 min` · `easy` · `4 servings`, with the servings pill tappable to open a stepper that live-rescales every ingredient quantity.
6. **AI action row** — two `ai` buttons: `ask about this recipe` and `swap an ingredient`.
7. **Ingredients block** — the signature saffron `#F4C149` panel at radius 24, with a Fragment Mono `ingredients` label. Each line is a checkbox row; checking strikes it through and dims it. A footer button reads `add 6 items to shopping list`.
8. **Instructions block** — numbered steps, each with the number in a 28px charcoal circle, the step in Body L, and any embedded time (`8–10 minutes`) auto-linked as a tappable timer chip.
9. **Nutrition** — a collapsible row of 4 stat tiles.
10. **"you might also like"** — a horizontal tile carousel.
11. **Sticky bottom bar** — a full-width primary `start cooking` button with a play glyph, present at all scroll positions.
**Motion:** shared-element hero expand on entry; parallax — the hero scrolls at 0.5× the content speed; the content card rises 24px and fades in delayed 120ms; checkboxes tick with a spring plus light haptic; ingredient quantities odometer-roll when servings change; the sticky bar slides up after 400ms.
**Fix from current build:** replace `height: '95%'` on the card with intrinsic content height; the whole screen must scroll as one, not two nested scroll regions.
> **STITCH BLOCK:** Mobile recipe detail screen, 393×852. A full-bleed food photo of pesto pasta with cherry tomatoes filling the top 45%, with a round blurred back button top-left and a share button top-right. Below, a cream content sheet with 32px rounded top corners overlapping the photo. Bold recipe title "Pesto Pasta with Cherry Tomatoes" with an outlined star bookmark button on the right, a gray one-line description, then a row of three monospace stat pills "18 min", "easy", "4 servings" separated by hairlines. Two dark AI buttons with sparkle icons: "ask about this recipe" and "swap an ingredient". Then a saffron yellow rounded panel labeled "ingredients" in lowercase monospace containing a checklist of ingredients with checkboxes. Below it a numbered instruction list with each number in a dark circle. A sticky bottom bar with a wide yellow "start cooking" button with a play icon, black border and hard offset shadow. Warm, appetizing, chunky.

---

### 10 · AI COOK MODE `[NEW · supports AI-2]`
**Purpose:** hands-free, greasy-fingers step-by-step cooking. Screen stays awake.
**Layout:** one step per full screen, swipe or voice to advance.
1. Top: a segmented progress bar with one segment per step, plus Fragment Mono `step 3 of 7` and a close `×`.
2. A 200px step illustration or photo.
3. The step text in **Display 34** — deliberately huge, readable from two feet away at a counter.
4. Any timer in the step becomes a large **timer pill** with a circular ring; tapping starts it, and running timers dock into a persistent strip at the top so several can run at once.
5. A docked Sous-Chef bar at the bottom: a mic button, the prompt `"ask me anything"`, and three quick chips (`repeat that`, `substitute`, `how do I know it's done?`).
6. Large `previous` / `next` arrow buttons in the bottom corners, each 64px.
**Voice mode:** a toggle switches to a giant-text, high-contrast layout where the whole screen is tappable to advance and a waveform ring surrounds the mic while listening.
**Finish state:** a full-screen celebration — confetti in the mood palette, `you cooked it!` in Display, the streak flame incrementing on an odometer, a 5-star rating row, a `add a photo` button, and `share your plate`.
**Motion:** steps slide horizontally with a 0.85× parallax on the image; the progress segment fills on `pour`; the timer ring depletes smoothly and pulses red plus a warning haptic in the last 10 seconds; the mic waveform reacts to live amplitude; the finish confetti uses `wobble` physics.
> **STITCH BLOCK:** Mobile step-by-step cooking screen, 393×852, cream background. A segmented progress bar at the top with 7 segments, 3 filled in a yellow-orange gradient, with "step 3 of 7" in small monospace and a close X. A 200px rounded photo of a pan of sautéing tomatoes. Below it, very large bold text: "Sauté halved cherry tomatoes in olive oil until they blister." A large pill-shaped timer showing "04:32" in monospace inside a circular progress ring. At the bottom a docked dark bar with a circular microphone button, the placeholder "ask me anything", and three small chips "repeat that", "substitute", "how do I know it's done?". Two large round arrow buttons in the bottom corners. Warm, high-contrast, kitchen-friendly.

---

### 11 · SOUS-CHEF CHAT `[NEW · AI-2]`
**Layout:** a saffron header with the chef-hat avatar, the name `sous-chef`, and a Fragment Mono `online` dot. The message list uses the AI bubble component. Rich inline cards render inside AI bubbles: a **substitution card** (crossed-out original → replacement, with a ratio note), a **conversion table**, and a **mini recipe card** with a `view` CTA. A quick-reply chip row sits directly above the composer. The composer is a 52px pill: a `+` attach button (photo of your dish for feedback), the text field, and a mic button that swaps to a send arrow once text exists.
**Empty state:** the chef-hat avatar plus `what are we making?` and four large starter cards — `what can I cook with chicken and rice?`, `I have 15 minutes`, `make this less spicy`, `is my dough ready?`.
**Motion:** bubbles enter rising 12px with a scale from 0.96 on `settle`; the AI's response streams token-by-token with a blinking caret; the thinking state is three bubbling dots; the mic press expands a waveform ring; long responses reveal a "scroll to bottom" pill.
> **STITCH BLOCK:** Mobile AI chat screen, 393×852, cream background. A saffron top bar with a small chef-hat avatar, the title "sous-chef" in bold, and a small green online dot with monospace label. A conversation: a right-aligned amber user bubble reading "can I use yogurt instead of cream?", then a left-aligned cream AI bubble with a thin amber border and a small sparkle icon, containing a reply plus an embedded white substitution card showing "1 cup cream" crossed out with an arrow to "1 cup Greek yogurt + 1 tsp lemon". A row of quick-reply chips above the input: "halve this recipe", "what can I do while it simmers", "substitute". A pill-shaped composer at the bottom with a plus button, "ask me anything" placeholder, and a microphone button. Warm, friendly, grainy.

---

### 12 · PANTRY SCAN `[NEW · AI-3]`
**Layout, three states in one screen:**
- **Capture** — camera viewfinder, animated corner brackets, a hint chip `point at your fridge shelf`, a 72px shutter, a gallery-picker thumbnail left, and a `type it instead` ghost link right.
- **Detecting** — the captured photo stays visible with a saffron sweep line and pulsing dots landing on each recognized object; detected ingredient chips pop into a tray at the bottom one by one with a light haptic each.
- **Results** — the photo shrinks into a 96px thumbnail. An editable chip cloud of detected ingredients follows, each chip showing an `×` to remove and a Fragment Mono confidence percentage; a dashed `+ add missing` chip opens an input. Then a primary `find recipes` button, and below it a results list grouped under two headers: **`you have everything`** (green check badges) and **`missing 1–2 things`** (amber badges naming what's absent, with an `add to list` shortcut).
**Motion:** brackets pulse on `simmer`; the sweep line repeats every 1.2s; chips pop in on `wobble` with a 120ms stagger; removing a chip collapses its width to 0 and the row reflows on `settle`; results bloom in.
**Failure:** nothing recognized → illustration plus `I couldn't make anything out — try more light, or type what you have.`
> **STITCH BLOCK:** Mobile AI pantry-scanning screen, 393×852. Top half: a photo of an open fridge shelf with vegetables, with animated white corner brackets and a horizontal saffron scan line, plus small pulsing dots marking recognized items. Bottom half: a cream sheet titled "i found 7 things" in lowercase monospace, containing a cloud of rounded ingredient chips — eggs 98%, spinach 94%, cheddar 91%, tomato 88% — each with a small × to remove and a tiny monospace confidence percentage, plus a dashed-outline chip reading "+ add missing". Below, a wide saffron "find recipes" button with a black border and hard offset shadow. Warm, technical but friendly, grainy.

---

### 13 · FLAVORFORGE GENERATOR `[NEW · AI-4]`
**Layout:**
1. Header `MAKE ME SOMETHING` with a sparkle.
2. **Mood pill** pre-filled with the current mood, tappable to change.
3. **Four dials** in a 2×2 grid, each a custom control on a mood-tint card: **time** (10–90 min radial dial, Fragment Mono 48 readout), **spice** (a 5-chili scale that ignites one chili at a time), **effort** (3-stop slider with emoji thumb), **servings** (a stepper with an odometer number).
4. **Pantry toggle** — a switch row: `only use what I have` with a live subtitle `7 ingredients from your last scan`.
5. **Wish field** — a large text area, placeholder *"something warm I can eat with one hand"*.
6. **Generate button** — full-width `ai` variant reading `forge my recipe`, with a Fragment Mono counter beneath: `3 of 5 free generations left today` (tappable to the paywall).
7. **Result card** — hero image, title, blurb, the meta strip, collapsed ingredients and steps, and a bottom action row: `save`, `cook now`, and a **dice `remix`** button.
**Motion:** the generating state is a full-screen takeover — illustrated ingredients fly in an arc into a bowl, the bowl wobbles, steam rises, and the generated title types itself out character by character at 30ms per character. Dials give a light haptic per detent. `remix` spins the dice 720° and cross-dissolves the card.
> **STITCH BLOCK:** Mobile AI recipe generator screen, 393×852, pale lavender background. Bold uppercase heading "MAKE ME SOMETHING" with a sparkle icon. A selected mood pill reading "😐 bored". A 2×2 grid of control cards: a radial time dial reading "25 min" in large monospace, a spice scale with five chili icons and three lit, a three-stop effort slider with an emoji thumb, and a servings stepper showing "2". A toggle row "only use what I have" with the subtitle "7 ingredients from your last scan". A large text area with the placeholder "something warm I can eat with one hand". A wide dark button with a sparkle reading "forge my recipe", and beneath it small monospace text "3 of 5 free generations left today". Warm, playful, tactile.

---

### 14 · SEARCH & DISCOVER `[NEW]`
**Layout:** a sticky search bar at the top (52px, `cream/100`, magnifier left, mic right) that expands on focus while the header collapses. Below, when idle: **`recent`** chips with an `×` on each, **`trending now`** as a numbered list with tiny thumbnails, and **`browse by mood`** as a 5-tile horizontal strip of mood gradients. When typing: live suggestions with the matched substring bolded, grouped under `recipes` / `ingredients` / `moods`. When results are shown: a sticky filter chip row (`mood`, `time`, `difficulty`, `diet`, `has in pantry`) where an active chip fills with the accent and shows a count badge, plus a right-side `filters` button opening a bottom sheet with full controls and a `clear all` link.
**Empty:** `no matches for "quinoa lasagna"` plus an illustration and a `let AI invent it` button routing to FlavorForge with the query pre-filled — **this is a required flourish**, turning every dead end into a generation.
**Motion:** the search bar expands and the header collapses simultaneously over 240ms `swift`; result rows stagger in; the filter sheet springs on `settle`; clearing filters makes chips deflate in sequence.
> **STITCH BLOCK:** Mobile search and discovery screen, 393×852, cream background. A sticky rounded search bar with a magnifier icon and a microphone icon. Below: a "recent" label in lowercase monospace with removable chips, then "TRENDING NOW" in bold uppercase as a numbered list with small square food thumbnails, then "BROWSE BY MOOD" with a horizontal strip of five gradient tiles labeled happy, sad, bored, stressed, angry in yellow, blue, purple, green and coral gradients. A bottom tab bar with five icons and a raised center button. Warm, browsable, grainy.

---

### 15 · ALL RECIPES (BROWSE) `[EXISTING]`
**Layout:** saffron header. H2 `ALL RECIPES` with a Fragment Mono count `· 20 recipes`. **Fix the filter control:** replace the full-width gray `Picker` with a horizontally scrolling **mood chip row** (`all` + the five moods, each chip carrying its mood color) plus a compact right-aligned `sort` button (a bottom sheet offering newest / quickest / easiest / most loved). Then a 2-column masonry grid of recipe tiles with intentionally varied heights (alternating 1:1 and 3:4) so the grid feels editorial rather than mechanical. Infinite scroll with skeleton tiles at the tail.
**States:** loading skeletons · filtered-empty (illustration + `clear filters`) · offline (a cached badge on tiles).
**Motion:** changing the mood filter cross-fades the grid — old tiles scale to 0.96 and fade over 160ms, new tiles bloom in staggered — while the background tint morphs to the selected mood.
> **STITCH BLOCK:** Mobile recipe browse screen, 393×852, cream background, full-width saffron top bar. A bold uppercase heading "ALL RECIPES" with a small monospace count "· 20 recipes". A horizontally scrolling row of mood filter chips: "all" selected in dark, then happy in amber, sad in blue, bored in purple, stressed in green, angry in coral. A compact "sort" button on the right. Below, a two-column masonry grid of food photo tiles with rounded 20px corners, varied heights, dark bottom gradients, white bold titles and small monospace meta text. A bottom tab bar. Warm, editorial, food-forward.

---

### 16 · MOOD COLLECTION `[EXISTING — was "Others"]`
**Purpose:** the full set for one mood. **Fix:** the current screen is hardcoded to "OTHER HAPPY RECIPES" and links to non-existent routes — it must be mood-parameterized and route to the real Recipe Detail.
**Layout:** a 200px **mood banner** at the top: a full-bleed mood gradient with the 64px emoji, the mood name in Display white, and a Fragment Mono subtitle (`12 recipes · because you're feeling it`). Below, a full-width recipe-row list (image left, content right) — a deliberately different rhythm from the grids elsewhere. A floating `switch mood` pill button at the bottom opens a mood-picker sheet.
**Motion:** the banner gradient pans slowly on `simmer`; the emoji does a gentle 4s float; rows slide in from the left staggered 50ms; switching mood morphs the banner gradient through HSL and re-blooms the list.
> **STITCH BLOCK:** Mobile mood collection screen, 393×852. A 200px full-bleed banner with a yellow-to-orange gradient containing a large 😊 emoji, the bold white word "HAPPY", and a small white monospace line "12 recipes · because you're feeling it". Below, a vertical list of recipe rows, each with a 96px square rounded food photo on the left and a bold title, gray description and small monospace meta on the right, with a chevron. A floating dark pill button at the bottom center reading "switch mood". Warm, immersive, grainy.

---

### 17 · FAVORITES `[EXISTING]`
**Layout:** saffron header, H2 `MY FAVORITES` with a count. A segmented control: `all` | `by mood` | `recently added`. In `by mood` the list groups under sticky mood headers with a colored left rail. Cards are recipe rows with a filled bookmark button; swipe-left reveals `remove` (danger) and `add to list` (saffron) actions. A `collections` row lets the user create named folders (weeknight, impress someone, hangover) as 120×120 cards with a stacked-photo mosaic thumbnail.
**Empty state:** riso illustration of an empty plate, `nothing saved yet`, *"tap the star on any recipe to keep it here"*, and a primary `browse recipes` button.
**Fix from current build:** remove the 680px bottom padding — use normal 24px plus the tab-bar inset.
**Motion:** removing a favorite collapses the row height to 0 over 300ms `settle` while adjacent rows close the gap; an undo toast appears for 4s; swipe actions follow the finger with a rubber-band limit.
> **STITCH BLOCK:** Mobile saved recipes screen, 393×852, cream background, full-width saffron top bar. Bold uppercase "MY FAVORITES" with a small monospace count "· 9 saved". A three-option segmented control: all, by mood, recently added. Below, a vertical list of recipe rows each with a 96px rounded food photo, bold title, gray description, small monospace meta, and a filled amber bookmark star on the right. One row is mid-swipe revealing a red "remove" action. Above the list, a horizontal row of 120px collection cards with stacked photo mosaics labeled "weeknight" and "impress someone". Warm, organized.

---

### 18 · SHOPPING LIST `[NEW]`
**Layout:** H2 `SHOPPING LIST` plus a Fragment Mono progress line `4 of 12 got`. A slim progress bar in the mood gradient. Items group under **aisle headers** (produce, dairy, pantry, spices) with a Fragment Mono label and a hairline. Each row: a large 28px round checkbox, the item name, the quantity in Fragment Mono right-aligned, and a small source chip naming the recipe it came from. Checked items strike through, dim to 40%, and animate to a collapsed `got it (4)` section at the bottom. A dashed "cut here" divider separates pending from got — a hand-drawn detail. The bottom bar offers `+ add item`, a `share list` button (exports as text or an image card), and a `clear got` link.
**AI touch:** a `smart merge` chip that consolidates duplicates across recipes ("2 onions + 1 onion → 3 onions") with an undo.
**Motion:** checking runs a spring tick plus a strikethrough line drawing left-to-right over 240ms; the row then flies down into the collapsed section on `pour`; the progress bar and its count odometer-roll; clearing all triggers a small confetti burst.
> **STITCH BLOCK:** Mobile shopping list screen, 393×852, cream background. Bold uppercase "SHOPPING LIST" with monospace "4 of 12 got" and a thin yellow-orange progress bar. Items grouped under lowercase monospace aisle headers "produce", "dairy", "pantry", each with a hairline. Each row has a large round checkbox on the left, the item name, a monospace quantity on the right, and a tiny gray chip naming the source recipe. Some rows are checked with a strikethrough and dimmed. A hand-drawn dashed "cut here" divider near the bottom above a collapsed "got it (4)" section. A bottom bar with "+ add item" and a "share list" button. Warm, tactile, paper-like.

---

### 19 · MOOD JOURNAL & INSIGHTS `[NEW · AI-5 surface]`
**Layout (scrolling):**
1. H1 `YOUR KITCHEN, LATELY` plus a range selector (`week` | `month` | `all`).
2. **Mood ribbon** — a horizontal stacked timeline where each day is a rounded vertical bar colored by that day's mood; tapping a day expands a detail card showing what was cooked. This is the hero chart and must be beautiful.
3. **Stat tile row** — three tiles: `18` meals cooked, `7` day streak, `stressed` top mood, each with an odometer number and a sparkline.
4. **AI insight cards** — 2–3 cards, each with a sparkle, a plain-language headline in H3 ("you cook 3× more on stressed evenings"), one supporting line, a small supporting visual, and a `this isn't right` correction link. **Never present a raw statistic without a sentence interpreting it.**
5. **Mood → food matrix** — a 5×5 heatmap of mood against food category, using accent-tinted cells, with a one-line reading beneath it.
6. **Weekly recap card** — a shareable summary card in a mood gradient with a `share` button that exports a 1080×1920 story image.
7. **Predictive nudge** — a card: *"Thursdays run stressed for you. Want a 15-minute plan ready?"* with `yes, plan it` and `no thanks`.
**Motion:** ribbon bars grow from the baseline staggered 40ms on `settle`; stat numbers roll on first view; the heatmap fills cell by cell in a diagonal wave; insight cards slide up as they enter the viewport.
**Empty:** fewer than 3 check-ins → illustration plus `check in a few more times and I'll start noticing patterns`.
> **STITCH BLOCK:** Mobile analytics and insights screen, 393×852, cream background. Bold uppercase heading "YOUR KITCHEN, LATELY" with a week/month/all segmented selector. A horizontal timeline of rounded vertical bars, one per day, each colored by mood — amber, blue, purple, green, coral. Below, three stat tiles with large monospace numbers 18, 7 and the word "stressed", each with a small sparkline. Then two insight cards with sparkle icons, each with a bold plain-language headline like "you cook 3× more on stressed evenings", a line of gray supporting text and a small chart. Then a 5×5 colored heatmap grid. Warm, data-rich but friendly, grainy.

---

### 20 · STREAKS & ACHIEVEMENTS `[NEW]`
**Layout:** a hero **flame** — a large animated ember-gradient flame with the Fragment Mono 64 streak number inside it, on a charcoal card so the flame glows. Below: a 7-dot week tracker where cooked days are filled with that day's mood color and today pulses. Then `BADGES` as a 3-column grid of 100px hexagonal tiles; earned badges are full color with a mood-gradient rim, locked ones are grayscale at 30% with a Fragment Mono progress line (`3/5 recipes`). Badge examples: *first cook*, *mood explorer* (all 5 moods), *night owl*, *spice demon*, *zero waste*, *week warrior*, *forged it* (first AI recipe). Tapping a badge opens a sheet with the story, the date earned, and a `share` button. A `freeze` token row lets the user protect a streak — 1 free per month, 3/month on Plus.
**Motion:** the flame flickers continuously on `simmer` with a soft glow that breathes; earning a badge triggers a full-screen takeover — the badge spins in on the Y axis, a light ray sweeps behind it, confetti bursts, and a success haptic fires; locked badges have a subtle grayscale shimmer.
> **STITCH BLOCK:** Mobile streaks and achievements screen, 393×852, cream background. A large dark rounded card containing a big glowing orange-and-yellow flame illustration with the number 7 in large monospace inside it, and the label "day streak". Below, a row of seven small circles for the week, five filled with different mood colors and today's pulsing. Then a bold uppercase "BADGES" label and a 3-column grid of hexagonal badge tiles — some in full color with gradient rims and icons, others grayscale and locked with a small monospace progress label like "3/5". Warm, game-like, celebratory.

---

### 21 · PAYWALL / PRICING `[NEW]`
**Purpose:** convert without shame. Shown after the 3rd AI generation, from any locked feature, and from Settings.
**Layout:**
1. A close `×` top-left (**always visible, never delayed** — no dark patterns).
2. A 200px hero: a looping illustration of a pan with sparkles rising out of it.
3. Display headline **"cook without limits"**, one line of Body L beneath.
4. **Three plan cards** in a vertical stack (not a cramped horizontal row):

| Plan | Price | Positioning |
|---|---|---|
| **Taste** (free) | `$0` | 5 AI generations/day · 3 pantry scans/week · basic mood recipes · 1 streak freeze/month |
| **Plus** ⭐ | `$4.99/mo` or `$39.99/yr` | Unlimited AI generations · unlimited pantry scans · Sous-Chef voice mode · full insights · offline recipes · 3 streak freezes |
| **Chef's Table** | `$9.99/mo` or `$79.99/yr` | Everything in Plus · family sharing (5 people) · weekly AI meal plans · custom mood creation · early features · a human-curated monthly recipe drop |

  Plus is pre-selected and elevated: mood-accent border 2px, a `MOST POPULAR` ribbon at a −8° rotation in the top-right corner, a subtle animated gradient sheen, and a `save 33%` badge on the annual toggle.
5. **Billing toggle** — a monthly/annual segmented switch; selecting annual slides a `save 33%` pill in and re-rolls all prices on an odometer.
6. **Feature comparison table** — a collapsible 3-column grid with saffron checks and gray dashes.
7. **Social proof** — a 3-avatar stack, `4.8 ★`, `12,400 cooks`.
8. **CTA** — full-width primary `start 7 days free`, with Fragment Mono 11 beneath: `then $4.99/month · cancel anytime`.
9. Footer links: `restore purchases` · `terms` · `privacy`.
**Motion:** plan cards stagger in rising 20px; selecting a card springs it to 1.02 while others recede to 0.98 and desaturate; the price odometer-rolls on billing toggle; the CTA has a slow gradient sheen sweeping every 4s; on success, a full-screen confetti celebration with `welcome to plus` and a success haptic.
> **STITCH BLOCK:** Mobile subscription paywall screen, 393×852, cream background. A close X at the top left. A 200px illustration of a pan with golden sparkles rising. Bold headline "cook without limits" and a line of gray subtext. A monthly/annual toggle with a "save 33%" pill. Three stacked plan cards: "Taste" free with a light border, "Plus" at $4.99/month highlighted with a 2px amber border, a subtle gradient sheen and a rotated "MOST POPULAR" ribbon in the corner, and "Chef's Table" at $9.99/month. Each card lists 3–4 features with small saffron check icons. A wide saffron CTA button reading "start 7 days free" with a black border and hard offset shadow, and small monospace text beneath reading "then $4.99/month · cancel anytime". Footer links: restore purchases, terms, privacy. Warm, generous, non-pushy.

---

### 22 · MANAGE SUBSCRIPTION `[NEW]`
**Layout:** a **status card** at the top — a mood-gradient fill with the plan name in Display, `active` with a pulsing dot, `renews 14 sep 2026` in Fragment Mono, and the price. Below: a **usage panel** with three ring meters (AI generations, pantry scans, meal plans) showing `used / limit` and rendering as a full ring with an infinity glyph when unlimited. Then a `BILLING` section with the payment method row (card brand icon, `•••• 4242`, `change`), billing history rows (date, amount, an invoice download glyph), and a `change plan` secondary button. At the bottom, a quiet danger zone: `pause subscription` (ghost) and `cancel subscription` (a text link in danger red, not a big button).
**Cancel flow:** a bottom sheet asking why, with a retention offer (`take 50% off for 3 months`) and a plain `continue to cancel` link — offer once, never nag.
**Motion:** rings fill on load over 800ms `pour` with odometer numbers; the status card gradient pans on `simmer`; the cancel sheet springs up.
> **STITCH BLOCK:** Mobile subscription management screen, 393×852, cream background. A large rounded card with a yellow-to-orange gradient showing "Plus" in bold white, "active" with a pulsing green dot, "renews 14 sep 2026" in small white monospace, and "$4.99/month". Below, three circular ring meters labeled "ai generations", "pantry scans", "meal plans" with monospace used/limit numbers, one showing an infinity symbol. Then a "BILLING" section with a payment method row showing a card icon and "•••• 4242" with a "change" link, and two billing history rows with dates, amounts and download icons. A secondary "change plan" button. At the bottom, a small red "cancel subscription" text link. Warm, clear, trustworthy.

---

### 23 · PROFILE / ACCOUNT `[EXISTING]`
**Layout:**
1. A 160px **mood-gradient cover** with a 120px avatar overlapping it by −60px; the avatar has a 4px cream ring and a 32px camera button at the bottom-right that opens the camera/gallery sheet.
2. Name in H1, `@handle` in Fragment Mono `charcoal/400`.
3. A **plan badge** pill (`plus ⭐`) that routes to Screen 22, or `upgrade` for free users.
4. A **3-stat row**: recipes cooked, favorites, day streak — Fragment Mono numbers with caption labels, separated by hairlines.
5. **Current mood row** — a large tappable card, not a dropdown: the emoji, the mood name, and `change` — opening the mood sheet.
6. A **menu list** of rows with 24px icons and chevrons: `my favorites`, `shopping list`, `my journal`, `taste profile`, `settings`, `help & support`, `about`.
7. `log out` as a full-width secondary button with a charcoal border.
**Fix from current build:** replace the `email:` / `current mood:` label-plus-field rows and the small colored button cluster with this profile-header pattern; move change-password and delete-account into Screen 25.
**Motion:** the cover gradient pans on `simmer`; the avatar springs in on `wobble`; the stat numbers roll on first view; menu rows slide in staggered 40ms; on scroll the header collapses into a compact saffron bar carrying the name and a mini avatar.
> **STITCH BLOCK:** Mobile profile screen, 393×852, cream background. A 160px cover banner with a yellow-to-orange gradient, and a 120px circular avatar with a thick cream ring overlapping the bottom edge of the banner, with a small camera button attached at its lower right. Below, a bold name "Gilbert" and a monospace handle "@gilbert". A small amber "plus ⭐" pill badge. A row of three stats with large monospace numbers and small caption labels: recipes cooked, favorites, day streak, separated by hairlines. A large tappable card showing 😊 and "happy" with a "change" link. Then a list of menu rows with icons and chevrons: my favorites, shopping list, my journal, taste profile, settings, help & support. A wide outlined "log out" button at the bottom. Warm, personal, clean.

---

### 24 · SETTINGS `[NEW]`
**Layout:** grouped sections with UPPERCASE Montserrat headers and a Fragment Mono description line under each group.
- **NOTIFICATIONS** — master toggle, then `daily mood check-in` with a time picker (default 6:00 pm), `cooking reminders`, `streak at risk`, `weekly recap`, `new recipes for your mood`. Each row is a toggle with a one-line explanation beneath in `charcoal/400`.
- **APPEARANCE** — a theme selector as three visual preview cards (light / dark / system) showing a mini rendering of the app, and a `let mood tint the app` toggle.
- **COOKING** — units (metric / imperial segmented), `keep screen awake while cooking`, `voice guidance`, default servings stepper.
- **AI** — `personalized suggestions` toggle with the explainer *"lets MoodCook learn what you cook"*, `save my scans` toggle, `manage my data` row, and a `reset what AI knows about me` link in danger red with a confirmation.
- **PRIVACY & DATA** — `download my data`, `data sharing`, `privacy policy`.
- **ABOUT** — version `2.0.0` in Fragment Mono, `rate the app`, `share MoodCook`, and the `created by avg` credit.
**Motion:** toggles are custom — the thumb slides with a slight overshoot on `wobble` and the track cross-fades to the mood accent; sections fade and rise on entry; selecting a theme card animates a circular wipe of the new theme across the whole screen from the tap point (a signature moment).
> **STITCH BLOCK:** Mobile settings screen, 393×852, cream background. Grouped sections with bold uppercase headers "NOTIFICATIONS", "APPEARANCE", "COOKING", "AI". Under notifications, toggle rows with a bold label and a small gray explanation line beneath, one row showing a time picker reading "6:00 pm" in monospace. Under appearance, three small preview cards labeled light, dark and system, each showing a miniature rendering of the app, with the light one selected via a 2px amber border. Custom rounded toggles in amber. Under AI, a red text link "reset what AI knows about me". Warm, organized, calm.

---

### 25 · SECURITY & DANGER ZONE `[EXISTING — merges Change Password + Delete Account]`
**Layout:** saffron header with a back arrow and the title `security` (**the current screens have no header — add it**). A 96px avatar with the name beneath, centered. Then:
- **CHANGE PASSWORD** section — a `current password` field (**required — the current build calls `updatePassword` with no re-authentication**), `new password` with a 4-segment strength meter, `confirm new password`. All three use the eye/eye-off **SVG** toggle, never an emoji. A live requirements checklist appears below the new-password field — 4 rows (8+ characters, one number, one uppercase, match) whose bullets animate from a gray dot to a green check as each is satisfied. A primary `update password` button — **use the mood accent, not the current blue** — with a `forgot your current password?` ghost link beneath.
- A **hand-drawn divider** with the Fragment Mono label `danger zone`.
- **DELETE ACCOUNT** panel — a `danger/500` 2px border on a `#FDEEE9` fill, a warning triangle, the heading `delete my account`, a plain-language list of exactly what is lost (recipes, favorites, streak, journal), and a **`export my data first`** secondary button placed *above* the destructive action. Then a `type DELETE to confirm` input (**replace the hardcoded `123456` code in the current build**) and a `delete forever` destructive button that stays disabled until the text matches exactly.
**Motion:** the strength meter segments fill on `swift` with a color shift green→amber→red; requirement bullets pop to checks on `wobble`; the delete button remains at 40% opacity and shakes ±4px if tapped while disabled; a final confirmation modal springs in with a 3-second countdown on its confirm button (Fragment Mono odometer) before it becomes tappable.
> **STITCH BLOCK:** Mobile account security screen, 393×852, cream background with a full-width saffron top bar containing a back arrow and the lowercase title "security". A 96px circular avatar centered with the name "gilbert" beneath. A bold uppercase "CHANGE PASSWORD" section with three password fields — current, new, confirm — each with an eye icon, plus a four-segment strength bar and a checklist of four requirements with small green checks and gray dots. A wide amber "update password" button with a black border and hard offset shadow. Below, a hand-drawn dashed divider labeled "danger zone" in lowercase monospace. Then a panel with a 2px red border on a pale pink fill containing a warning triangle, the heading "delete my account", a bulleted list of what will be lost, an outlined "export my data first" button, a text field with the placeholder "type DELETE to confirm", and a disabled red "delete forever" button. Warm but serious.

---

## 8. CROSS-CUTTING STATES — design each of these once, as shared components

1. **Loading** — skeletons only, never spinners, except the AI thinking state (bubbling dots) and pull-to-refresh (pan flip).
2. **Empty** — every list needs one: riso illustration, H2, one body line, one primary action. Never a dead end — always offer a next step, and where it makes sense that next step is an AI generation.
3. **Error** — inline for form fields, a toast for transient failures, a full screen only for a hard failure. Always name a recovery action. Never surface a raw Firebase error string.
4. **Offline** — a persistent slim charcoal bar reading `offline · showing saved recipes`, with cached tiles carrying a small download glyph.
5. **AI failure** — a distinct, non-alarming voice: `my brain slipped — try again?` with a retry button. Never red, never "error".
6. **Rate limited** — `you've used today's 5 free generations` plus a countdown to reset and an `upgrade` CTA.
7. **Permission denied** (camera/mic) — an illustration explaining why the permission is needed and a button that deep-links to system settings.
8. **First-run coach marks** — three dismissible spotlight tooltips on Today: the mood pencil, the center Cook FAB, and the `why?` chip.

---

## 9. ACCESSIBILITY (non-negotiable)

- Contrast ≥ 4.5:1 for body text, ≥ 3:1 for large text and UI. **Note: charcoal `#16130E` on saffron `#F4C149` passes; white on saffron does not — never put white text on saffron.**
- Minimum touch target 44×44, with 8px between adjacent targets.
- Never encode meaning in color alone: every mood pairs its color with an emoji **and** a text label.
- Support Dynamic Type up to 200% — all cards must grow vertically rather than clip. Design an "XL text" variant of Today and Recipe Detail.
- Every icon-only button gets a label. Full VoiceOver/TalkBack focus order specified per screen.
- Cook Mode must be fully operable by voice alone.
- Respect reduce-motion and reduce-transparency (blur backdrops become 95% solid fills).

---

## 10. VOICE & TONE

Lowercase for system text and micro-labels. Sentence case for body. UPPERCASE only for section headers. Warm, brief, a little funny, never twee and never clinical.

- **Do:** "let's cook something." · "my brain slipped — try again?" · "nothing saved yet." · "you cooked it!"
- **Don't:** "An error has occurred." · "Optimize your nutritional intake." · "Oopsie! Something went wrong!! 😅"
- Never diagnose or use clinical mental-health language. "feeling stressed" is fine; "your anxiety levels" is not.
- The AI speaks in first person, is brief, and admits uncertainty plainly: "not sure, but I'd guess…"

---

## 11. DELIVERABLES CHECKLIST

- [ ] 25 screens at 393×852, light mode
- [ ] Dark-mode variants for at least screens 6, 8, 9, 10, 11, 19, 21
- [ ] All 5 mood themes demonstrated on screens 6, 8, and 16
- [ ] Component library with every variant and state from §5
- [ ] Color, type, spacing, radius, and shadow styles as named tokens
- [ ] Empty, loading, error, and offline states for every list screen
- [ ] A motion spec sheet documenting the 10 signature motions from §4.2
- [ ] Two prototype flows wired end to end: **onboarding → taste profile → mood check-in → today**, and **today → recipe detail → cook mode → finish celebration**
- [ ] An XL-text accessibility variant of screens 8 and 9

---

## 12. ONE-PARAGRAPH VERSION (for tools with a hard input limit)

> Design a 25-screen mobile app called **MoodCook** — a mood-first cooking companion where you pick or AI-detect your mood and get recipes plus an AI sous-chef. Style: "warm kitchen brutalism" — cream `#FFFBF2` backgrounds, saffron `#F4C149` header bars and primary buttons with 2px charcoal `#16130E` borders and hard 2px offset shadows, 24px rounded cards, full-bleed food photography, a 3% grain overlay, and sparse hand-drawn ink accents. Type: Montserrat Bold for headings, Fragment Mono lowercase for all micro-labels, timers, prices and counts. Five mood themes recolor the whole screen: happy `#FFC53D`, sad `#5B7FA8`, bored `#8B5CF6`, stressed `#6FA287`, angry `#E4572E`. Every AI feature is marked with a 4-point sparkle. Motion is cooking-inspired: steam rises, cards bloom staggered, numbers roll on odometers, moods morph through HSL. Screens: splash, 3-slide onboarding, sign up, sign in, taste-profile wizard, mood check-in, AI mood scan, today feed, recipe detail, AI cook mode, sous-chef chat, pantry scan, AI recipe generator, search, browse, mood collection, favorites, shopping list, insights, streaks, paywall, manage subscription, profile, settings, and security.
