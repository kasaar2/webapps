# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a collection of standalone educational quiz web applications designed for elementary school students. Each quiz is a self-contained single HTML file with embedded CSS and JavaScript - no build process, dependencies, or external libraries required.

## Architecture

### File Structure
- **index.html** - Main landing page with animated cards linking to all quiz applications
- **multiplication-quiz.html** - Times tables practice (grades 3-5)
- **pythagorean-quiz.html** - Pythagorean theorem problems (grades 5-6)
- **flag-quiz.html** - World geography flag identification game
- **national_flags.csv** - Source data for flag quiz (embedded in flag-quiz.html as JSON)

### Common Patterns

All quiz applications follow a similar architecture:

1. **Screen-based navigation**: Each app uses `.screen` divs with `.active` class to show/hide different states (welcome, game, results)
2. **Embedded styles**: All CSS is inline in `<style>` tags, typically featuring:
   - Gradient backgrounds
   - Card-based layouts with animations
   - Mobile-responsive design with media queries
3. **Vanilla JavaScript**: No frameworks - pure DOM manipulation
4. **Game state management**: Single `gameState` object tracks progress, score, and settings
5. **Self-contained data**: All necessary data (like flag URLs) is embedded directly in the HTML

### Quiz-Specific Features

**Multiplication Quiz**:
- Configurable difficulty (1-12 times tables)
- Timed mode with countdown
- Visual feedback for correct/incorrect answers

**Pythagorean Quiz**:
- Generated right triangle problems
- Visual triangle diagrams with SVG
- Hint system showing the formula
- Multiple difficulty levels with different number ranges

**Flag Quiz**:
- Three difficulty levels (30/80/201 countries)
- Three game modes: Multiple Choice, Type Answer, Match Pairs
- Practice vs Challenge modes (with lives system)
- Embedded flag data from Wikipedia URLs

## Development Workflow

### Testing
Simply open any HTML file directly in a web browser - no server required. All applications are fully client-side.

### Making Changes
1. Edit the HTML file directly
2. Refresh browser to see changes
3. No build step or compilation needed

### Adding New Quizzes
Follow the established pattern:
1. Create self-contained HTML file with embedded CSS/JS
2. Use screen-based navigation (welcome → game → results)
3. Implement mobile-responsive design
4. Add colorful gradients and animations for kid-friendly appeal
5. Update index.html to add a card linking to the new quiz

### Code Style
- Kid-friendly design: bright colors, large fonts, animations
- Accessibility: ensure large click targets, clear feedback
- Keep everything in one file for portability
- Use semantic HTML
- Graceful degradation (works without JavaScript for static content)

## Data Management

**Flag Quiz Data**: The `FLAGS_DATA` array in flag-quiz.html contains 201+ countries with Wikipedia flag URLs. To update:
1. Modify the embedded JSON array directly
2. Ensure flag URLs are valid and publicly accessible
3. Update `EASY_COUNTRIES` array if changing beginner-friendly countries

## Browser Compatibility

These apps use modern JavaScript (ES6+) and CSS features:
- CSS Grid and Flexbox for layouts
- Arrow functions and template literals
- `const`/`let` declarations
- Array methods like `.map()`, `.filter()`, `.reduce()`

Target: Modern evergreen browsers (Chrome, Firefox, Safari, Edge). No IE support needed.
