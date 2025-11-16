# SASCO 2048 - Setup Guide

## What's Been Done

Your 2048 game for the SASCO school portal is ready! Here's what was customized:

### Changes Made:

1. **Branding**
   - Title changed to "2048 - SASCO Games"
   - Added SASCO branding at the bottom
   - Proper attribution to original creator (Gabriele Cirulli)

2. **Visual Updates**
   - Changed background to lighter blue (#f0f4f8) - more modern
   - Title color changed to green (#4CAF50) - kid-friendly
   - Score boxes changed to green with rounded corners
   - Game board updated with rounded corners

3. **Legal/Attribution**
   - Kept original MIT LICENSE.txt file
   - Added attribution in the HTML
   - Created new README.md with full credits
   - Properly documented for school use

## File Structure

```
2048-game/
├── index.html          (Main game file - OPEN THIS!)
├── LICENSE.txt         (Original MIT license - REQUIRED)
├── README.md          (Documentation)
├── SASCO-SETUP.md     (This file)
├── favicon.ico        (Game icon)
├── js/                (Game logic - 7 files)
├── style/             (CSS + fonts)
└── meta/              (Mobile icons)
```

## How to Use

### To Play:
Simply open `index.html` in any web browser!

### To Add to Your Portal:
1. Copy the entire `2048-game` folder to your school portal
2. Link to it from your games menu
3. That's it - it works standalone!

### To Customize Further:
- **Colors**: Edit `style/main.css`
- **Title/Text**: Edit `index.html`
- **Grid Size**: Edit `js/application.js` (currently 4x4)

## What You Can Do (MIT License)

✅ Use in your SASCO school platform
✅ Modify colors, styling, features
✅ Distribute to all schools
✅ Call it a "SASCO Game"
✅ Use commercially (if needed)

## What You Must Do (MIT License)

✅ Keep the LICENSE.txt file
✅ Keep attribution to Gabriele Cirulli

That's it! Very simple.

## Features

- Arrow key controls
- Touch/swipe support for tablets
- Saves high score (localStorage)
- Mobile-friendly
- No internet required
- No build process needed

## Next Steps

1. Test the game (already opened in your browser!)
2. If you like it, integrate into your portal
3. Consider adding more games (Snake, Flappy Bird, etc.)

---

Need help? The game is self-contained and ready to go!
