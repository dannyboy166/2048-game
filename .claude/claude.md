# 2048 - SASCO Games Edition

## Project Context

This is one of **4 games** being integrated into Victor's **SASCO student/teacher portal platform** for schools.

### Portal Overview
The SASCO portal is a student/teacher platform where:
- **Teachers** can assign homework, set questions, and track student progress
- **Students** complete educational activities and earn "free time" credits
- **Games** are categorized as:
  - **Educational** - Learning games (can be assigned as homework)
  - **Free time rewards** - Games unlocked by completing educational tasks
  - **Time earners** - Games that generate free time credits when played

### The 4 Games

1. **MathCrush2** (Unity WebGL) - **Educational + Time Earner**
   - Equation-based math game
   - Earns students free time credits for solving equations
   - Currently in active integration with Victor (Phase 1: launch testing)
   - Location: Azure DevOps MathGame repo

2. **Wordle** (React) - **Educational**
   - Daily word puzzle for vocabulary/spelling practice
   - Teachers can assign custom word lists as homework
   - Location: `/Users/danielsamus/wordle-game`
   - Live: https://dannyboy166.github.io/wordle-game/

3. **Kangaroo Hop** (Phaser.js) - **Free Time Reward**
   - Endless runner game
   - Students play this after earning free time
   - Location: `/Users/danielsamus/my-kangaroo-game`
   - Live: https://dannyboy166.github.io/my-kangaroo-game/

4. **2048** (Vanilla JS) - **Free Time Reward** ← **THIS GAME**
   - Number puzzle game
   - Students play this after earning free time
   - Location: `/Users/danielsamus/2048-game`
   - Live: https://dannyboy166.github.io/2048-game/

### Central Planning
**All integration planning is coordinated at:**
`/Users/danielsamus/sasco-games-portal/`

This folder contains:
- Overall roadmap and integration plan (README.md)
- Task tracking (TASKS.md)
- Claude context for the full project (.claude/claude.md)

**Always check the central planning folder for:**
- Integration requirements and timeline
- Victor's technical specifications
- Progress tracking across all 4 games

---

## This Game: 2048

### Current Status (2025-11-18)
- ✅ Game is complete and deployed
- ✅ Live on GitHub Pages
- ⏳ Waiting for Mum's approval before Victor integration
- 🔨 Needs optimization/features before portal integration

### Role in Portal
**Free time reward game**

Students can play this game after:
- Completing math equations in MathCrush2
- Finishing homework assignments
- Earning free time credits through educational activities

**Educational Value:**
- Strategic thinking and planning ahead
- Pattern recognition
- Basic math (doubling numbers: 2→4→8→16...)
- Problem-solving skills

### Integration Requirements (from Victor's MathCrush2 pattern)

**Phase 1: Basic Launch** (Recommended for 2048)
- Read URL parameters: `?studentId=X&sessionId=Y&token=Z`
- Embed in iframe within portal
- Add "Return to Portal" button
- Works offline (localStorage for scores)

**Phase 2: Progress Tracking** (Optional)
- JS Interop to Victor's API (Victor provides the code)
- Track: high score, games played, tiles reached
- Store in Victor's database for student profiles
- Not critical for free time games - can add later

### Technical Architecture

**Tech Stack:**
- Pure Vanilla JavaScript (no frameworks)
- HTML5 + CSS3
- No build process - ready to run
- Original 2048 by Gabriele Cirulli (MIT License)

**File Structure:**
```
2048-game/
├── index.html           # Main entry point
├── js/
│   ├── application.js       # Game initialization
│   ├── game_manager.js      # Core game logic
│   ├── grid.js              # Grid data structure
│   ├── tile.js              # Tile objects
│   ├── keyboard_input_manager.js  # Input handling
│   ├── html_actuator.js     # DOM updates
│   ├── local_storage_manager.js   # Score persistence
│   └── *_polyfill.js        # Browser compatibility
├── style/
│   └── main.css            # All styling
├── meta/                   # Mobile icons
├── favicon.ico
├── README.md              # User documentation
└── SASCO-SETUP.md         # Customization notes
```

**How It Works:**
1. `application.js` initializes the game on page load
2. `game_manager.js` contains all game logic (moves, merging, win/lose)
3. `keyboard_input_manager.js` handles arrow keys and touch events
4. `html_actuator.js` updates the DOM when tiles move/merge
5. `local_storage_manager.js` saves/loads best score

**SASCO Customizations Made:**
- Title: "2048 - SASCO Games"
- Background color: lighter blue (#f0f4f8)
- Title color: green (#4CAF50)
- Score boxes: green with rounded corners
- Added SASCO branding footer
- Kept MIT license attribution

### Features Needed Before Portal Integration

**Priority 1: URL Parameter Support**
- Read `studentId`, `sessionId`, `token` from URL on game load
- Parse parameters in `application.js`
- Log parameters for testing (like MathCrush2 does)

**Priority 2: Return to Portal Button**
- Add UI button (top-right or with "New Game" button)
- Use `window.parent.postMessage({ action: 'closeGame' }, '*')` to notify portal
- Style to match existing UI (green theme)

**Priority 3: Progress Tracking** (Optional - can add later)
- Integrate Victor's JS Interop code when provided
- Track: high score, games played, highest tile reached
- Send to Victor's API with token authentication
- Only needed if Victor wants analytics for free time games

### Development Workflow

**To modify the game:**
1. Edit files directly in `/Users/danielsamus/2048-game`
2. Test locally by opening `index.html` in browser
3. Commit changes to git
4. Push to GitHub for GitHub Pages deployment
5. Test at https://dannyboy166.github.io/2048-game/

**To add URL parameter support:**
- Edit `js/application.js`
- Add parameter parsing on `window.addEventListener('load', ...)`
- Store studentId, sessionId, token for later use

**To add Return button:**
- Edit `index.html` (add button HTML)
- Edit `style/main.css` (style the button)
- Edit `js/application.js` (add click handler)

**No build process needed** - all changes are instant!

### Key Contacts

- **Victor** (Victor@eStreet.com.au) - Portal platform developer
- **Julie/Mum** (juliesamus@bigpond.com) - Educational requirements
- **Daniel** (samus.daniel@gmail.com) - Developer

### Next Steps (from central plan)

1. Get Mum's approval for including 2048 in portal
2. Add URL parameter support (studentId, sessionId, token)
3. Add "Return to Portal" button
4. Test iframe embedding
5. Wait for Victor's integration specs (after MathCrush2 launch)
6. Optionally add progress tracking if Victor requests it
7. Test in Victor's staging environment
8. Launch to schools

### Important Notes

- **Keep it simple** - This is a free time game, not educational
- **Low priority for tracking** - Students just want to play and relax
- **Follow MathCrush2 pattern** - Use same URL params and auth approach
- **Don't break the game** - It's perfect as-is, only add portal features
- **MIT License** - Keep Gabriele Cirulli attribution always

### Related Documentation

- **Central plan**: `/Users/danielsamus/sasco-games-portal/README.md`
- **Task tracking**: `/Users/danielsamus/sasco-games-portal/TASKS.md`
- **Victor's emails**: See central `.claude/claude.md` for MathCrush2 integration details
- **This game's README**: `README.md` (user-facing)
- **Setup notes**: `SASCO-SETUP.md` (SASCO branding customizations)
- **Original 2048**: https://github.com/gabrielecirulli/2048

---

**When working on this game, always consider:**
- Will this change break the existing gameplay?
- Is the MIT license attribution still visible?
- Does it align with Victor's integration pattern?
- Is this feature really needed for a free time game?
