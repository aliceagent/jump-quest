# Jump Quest - Platform Game Specification

## Project Overview
- **Name:** Jump Quest
- **Type:** Mobile-first endless platformer game
- **Core Functionality:** Tap left/right to jump between falling platforms, climb as high as possible
- **Target Users:** Mobile gamers (iPhone optimized)

## UI/UX Specification

### Layout Structure
- Full viewport canvas (100vw x 100vh)
- Touch zones: left 50% = jump left, right 50% = jump right
- Score display: top-center
- Game over overlay: centered modal

### Visual Design
- **Background:** Deep space gradient (#0a0a1a → #1a1a3a) with twinkling stars
- **Character:** Cute cartoon robot (circle body, antenna, big eyes)
- **Platforms:** Rounded rectangles with gradient (candy colors: pink #ff6b9d, cyan #4ecdc4, yellow #ffe66d, purple #a855f7)
- **Typography:** "Fredoka One" (playful, rounded)
- **Colors:**
  - Robot: #3b82f6 (blue) with #60a5fa highlights
  - Score: #ffffff with text shadow
  - Game Over: dark overlay rgba(0,0,0,0.85)

### Animations
- Character: slight bounce idle, squash/stretch on jump
- Platforms: gentle floating bob
- Score: pop effect on increment
- Game over: fade in overlay

## Functionality Specification

### Core Mechanics
1. **Character:**
   - Starts at bottom-center
   - Affected by gravity (falls down)
   - Jumps when tapping screen

2. **Controls:**
   - Tap LEFT half → jump diagonally left-up
   - Tap RIGHT half → jump diagonally right-up
   - Jump velocity: upward + horizontal component

3. **Platforms:**
   - Generate randomly above viewport
   - Fall downward at constant speed (increases with score)
   - Horizontal position randomized
   - Width: 80-120px, Height: 15px
   - Must land ON platform (not through from below)

4. **Scoring:**
   - +1 point per successful landing on a NEW platform
   - Score displayed continuously

5. **Game Over:**
   - Triggered when character falls below viewport bottom
   - Show final score
   - "Tap to Restart" button

6. **Difficulty Scaling:**
   - Platform fall speed increases every 10 points
   - Platform spacing decreases slightly

### Edge Cases
- Character cannot jump while in air (single jump only)
- Platforms recycle when below viewport (move to top)
- Minimum 1 platform always reachable

## Acceptance Criteria
- [ ] Game loads on mobile browser
- [ ] Tapping left side makes character jump left
- [ ] Tapping right side makes character jump right
- [ ] Character lands on platforms realistically
- [ ] Platforms continuously fall
- [ ] Score increments on successful landings
- [ ] Game ends when falling off bottom
- [ ] Restart functionality works
- [ ] Deployed on Vercel and accessible from iPhone
