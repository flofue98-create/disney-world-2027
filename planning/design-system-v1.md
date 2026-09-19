# Disney World 2027 — Design System v1

Status: planning prototype only. This does not change the live app.

## Product feel
Premium Disney travel assistant: warm, elegant, immersive, easy to scan, adult-friendly, family-friendly. Avoid scrapbook styling, excessive gradients, emoji clutter, tiny text, and overuse of pills.

## Typography
Use one system stack throughout: `-apple-system, BlinkMacSystemFont, "SF Pro Display", "Segoe UI", sans-serif`.

- Page/day title: 28–30 px, 750–800 weight
- Section title: 18–20 px, 700–750 weight
- Attraction/restaurant/show name: 16–17 px, 650–700 weight
- Body/supporting text: 13–14 px, 400–500 weight
- Minor metadata: 12 px, 500–600 weight
- Tiny labels only when unavoidable: minimum 11 px

## Capitalization
- Title Case: page names and day titles only
- Sentence case: buttons, labels, warnings, assistant language, metadata
- All caps: only very small status tags such as LIVE or ESTIMATE, never normal UI text

## Color roles
Base palette:
- Warm background: #F6F3EE
- Card: #FFFFFF
- Primary ink: #172033
- Secondary text: #667085
- Disney navy: #17385E
- Soft navy: #EAF1F8
- Border: #E1E6EC

Semantic colors:
- Good / fits well: green
- Tradeoff / caution: amber
- Conflict: red
- Information / assistant recommendation: blue

Park accents should be restrained and used mainly in headers:
- Magic Kingdom: royal blue + soft gold
- EPCOT: indigo
- Hollywood Studios: burgundy/coral
- Animal Kingdom: earthy green

## Spacing and shape
- Main page horizontal padding: 16 px mobile
- Card padding: 16 px
- Vertical rhythm: 8 / 12 / 16 / 24 px
- Large card radius: 18 px
- Small control radius: 10–12 px
- Pill shapes only for filters/statuses
- Minimum tap target: 44 px

## Interaction language
Core rule:
- Tap the name = details
- Tap the time = adjust timing
- Tap an assistant recommendation = explanation + options

The user should not manually manage data the app already knows.

## Timeline cards
Every planned experience should answer, at a glance:
1. What is it?
2. Where is it?
3. When should we start?
4. How long will it take?
5. What is the estimated/live wait?
6. When will we be finished?
7. How far is the next move?
8. Why is this a good choice now?

Attraction example:
- 9:05 AM
- Seven Dwarfs Mine Train
- Fantasyland · Map number
- Planning wait: 25–40 min
- Experience: ~3 min
- Walk from previous: ~4 min
- Expected finish: 9:48 AM

Show example:
- 11:35 AM
- Mickey’s Magical Friendship Faire
- Cinderella Castle Forecourt
- Runtime: ~20 min
- Arrive by: 11:20 AM
- Expected finish: 11:55 AM

Dining example:
- 5:30 PM
- Cinderella’s Royal Table
- Cinderella Castle
- Allow ~75–90 min
- Menu · Details · Map

## Assistant cards
Use one visual pattern everywhere.

Recommendation:
- sparkle/star icon
- short headline
- one- or two-sentence reason
- actions: See why / Use suggestion / Keep my plan

Warning:
- caution icon
- exact consequence, not generic language
- suggested fix

Example:
Potential conflict
Moving Bibbidi Bobbidi Boutique to 4:15 PM leaves too little buffer before a 5:30 PM Cinderella’s Royal Table reservation.

## Navigation
Bottom navigation target:
- Today
- Plan
- Explore
- Dining
- Maps
- More

Use consistent line icons. Selected state gets a soft highlighted background rather than a heavy solid pill.

## Detail sheets
Every attraction, show, character experience, restaurant, and appointment is tappable.

Attraction detail sheet:
- description
- park + land
- approximate experience duration
- height requirement
- intensity
- Lightning Lane status
- planning/live wait
- indoor/outdoor
- family split / Rider Switch notes
- map number/location
- Official Disney page
- Open park map

Show detail sheet:
- description
- runtime
- arrive-early recommendation
- planning/current performance times
- location
- weather sensitivity
- Official Disney page
- Open park map

Restaurant detail sheet:
- cuisine
- service type
- approximate meal duration
- reservation status
- current/target time
- party notes
- Menu
- Disney restaurant page
- Map

## Route visualization
Between major timeline items, show compact travel cues:
- ↓ 4 min walk
- ↓ 18 min cross-park walk · caution

Do not require the user to infer geographic efficiency from land names alone.

## Accessibility and readability
- Never rely on color alone for status
- Strong contrast for text
- 44 px minimum controls
- Support Dynamic Type-like scaling where practical
- Avoid excessive thin/light font weights
- Keep important controls reachable on iPhone/iPad

## Build rule
Do not apply this system piecemeal to the current live interface. First approve one complete Magic Kingdom day prototype, then use that as the visual and interaction reference for the rebuild.
