# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a collection of standalone educational quiz web applications designed for elementary school students. Each quiz is a self-contained single HTML file with embedded CSS and JavaScript - no build process, dependencies, or external libraries required.

## Architecture

### File Structure
- **index.html** - Main landing page with minimal, elegant design linking to all quiz applications
- **STYLE_GUIDE.md** - Design system specification for consistent styling across pages
- **multiplication-quiz.html** - Times tables practice (grades 3-5)
- **pythagorean-quiz.html** - Pythagorean theorem problems (grades 5-6)
- **counting-integers-quiz.html** - Integer counting formula practice (grades 5-6)
- **flag-quiz.html** - World geography flag identification game
- **national_flags.csv** - Source data for flag quiz (embedded in flag-quiz.html as JSON)

### Design System

The project uses a **minimal and elegant** design system documented in `STYLE_GUIDE.md`. Key principles:
- Clean, uncluttered interfaces
- System fonts with light weights (300-400)
- Subtle hover effects (no dramatic animations)
- Light gray backgrounds (#fafafa) with white cards
- Consistent spacing and typography scale

**Reference `STYLE_GUIDE.md` when creating new pages or updating existing ones.**

### Common Patterns

All quiz applications follow a similar architecture:

1. **Screen-based navigation**: Each app uses `.screen` divs with `.active` class to show/hide different states (welcome, game, results)
2. **Embedded styles**: All CSS is inline in `<style>` tags
3. **Vanilla JavaScript**: No frameworks - pure DOM manipulation
4. **Game state management**: Single `gameState` object tracks progress, score, and settings
5. **Self-contained data**: All necessary data (like flag URLs) is embedded directly in the HTML
6. **Mobile-responsive design**: Media queries for tablet/mobile breakpoints

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
3. **Follow STYLE_GUIDE.md** for consistent styling (minimal and elegant design)
4. Implement mobile-responsive design with media queries
5. Update index.html to add a card linking to the new quiz

### Code Style
- **Design**: Follow `STYLE_GUIDE.md` for minimal, elegant aesthetics
- **Accessibility**: Ensure large click targets, clear feedback, good color contrast
- **Portability**: Keep everything in one file (HTML/CSS/JS)
- **Semantic HTML**: Use proper heading hierarchy, meaningful elements
- **Progressive enhancement**: Core functionality works without JavaScript where possible

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
