# Social Prompter v2 — Build Spec

## Context
Evolving the existing app (robowers-bit.github.io/social-prompter/) from a teleprompter with AI hook generation into a full script-writing workspace built around the **9-beat structure**, with two distinct recording modes and a live spoken-duration timer.

## The 9-Beat Structure
1. **Hook** — the feeling that stops them
2. **Super Hook** — earn the right to teach
3. **Open Loop** — commit them to the end
4. **Body 1** — deliver real value
5. **Rehook** — "okay, one more"
6. **Body 2** — deliver real value
7. **Rehook** — "okay, one more"
8. **Body N** — deliver real value (repeatable — see below)
9. **Payoff / CTA** — close the loop, better than promised

**Flexibility rule:** Body/Rehook pairs are not capped at 3. The user can add additional Body beats (each followed by a Rehook, except the final Body before Payoff/CTA, which goes straight to Payoff). Minimum viable script is Hook → Super Hook → Open Loop → Body 1 → Payoff/CTA (no rehooks needed if there's only one body).

## New Feature 1: Script Builder
- A structured editor with one input block per beat, labelled with its beat name and one-line job description (as in the reference image).
- "+ Add Body" button inserts a new Body beat plus a Rehook beat before it, above the Payoff/CTA.
- Optional: upload source material — raw copy, a press release, or a video transcript — to ground the script in real content.
- From uploaded source material, the app generates **3 alternative Hook options** for the user to choose from or edit. Super Hook, Open Loop, and Body suggestions can pull facts/quotes from the source material but the Hook suggestions are the primary AI-generated element here.

## New Feature 2: Refinement Scratchpad
- Once a script exists (beats filled in, from scratch or via Script Builder), the app offers a review pass:
  - Format suggestions (e.g. beat too long/short relative to typical pacing, missing a Rehook after a long Body)
  - Wording suggestions (tighter phrasing, stronger verbs, removing filler)
- Suggestions are advisory and inline/non-destructive — user accepts, edits, or dismisses each one individually (matches existing engagement-flagging pattern).

## New Feature 3: Playback / Recording Mode
Two modes, user-selectable per script or per session:

**A. Word-for-word teleprompter**
- Existing scrolling-text behaviour, reads the full script verbatim.

**B. Guided-bullet mode**
- Each beat is condensed into a short prompt/cue rather than full text, so the presenter speaks naturally instead of reading.
- No beat labels shown on screen in this mode — just the bullets themselves, no "BODY 2" tags or similar.

**Both modes add:**
- An on-screen live timer tracking actual recorded/spoken duration (not a countdown — counts up from the point recording starts), so the presenter can gauge how long the video is running versus their target length.

## Resolved Decisions
- **Timer sync:** Auto-syncs to the device's recording start/stop — counts up automatically for the duration of the actual recording, no separate manual trigger.
- **Bullet-mode condensation:** AI auto-condenses the full script into short bullets for guided mode; user can edit the generated bullets.
- **Persistence:** Scripts are saved and versioned, not session-based — users can return to and continue editing previous scripts.
