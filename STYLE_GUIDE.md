# Style Guide - Elementary Quizzes

This document defines the minimal and elegant design system for all pages in the Elementary Quizzes project.

## Design Philosophy

**Minimal and Elegant**: Clean, uncluttered interfaces with subtle interactions. Focus on content and usability over decorative elements.

## Color Palette

### Backgrounds
- **Page background**: `#fafafa` (light gray)
- **Card/container background**: `#ffffff` (white)
- **Hover background**: Maintain white, adjust border/shadow only

### Text
- **Primary text**: `#1a1a1a` (near black)
- **Secondary text**: `#666666` (medium gray)
- **Tertiary text**: `#888888` (light gray)

### Borders
- **Default border**: `#e0e0e0` (light gray)
- **Hover border**: `#999999` (medium gray)

### Accents
- Use system colors sparingly for interactive elements
- Avoid bright gradients or multiple accent colors

## Typography

### Font Families
```css
font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Helvetica Neue', Arial, sans-serif;
```
Use system font stack for clean, native appearance across platforms.

### Font Weights
- **Light**: `300` - For large headings
- **Regular**: `400` - For body text, subtitles
- **Medium**: `500` - For card titles, emphasis

### Font Sizes
- **Large heading (h1)**: `2.5em` (desktop), `2em` (mobile)
- **Section heading (h2)**: `1.5em` (desktop), `1.3em` (mobile)
- **Card title (h3)**: `1.3em`
- **Body text**: `0.95em` - `1.1em`
- **Small text**: `0.85em`

### Letter Spacing
- Large headings: `-0.5px`
- Section headings: `-0.3px`
- Body text: default

## Spacing

### Padding
- **Page padding**: `40px 20px` (desktop), `30px 15px` (mobile)
- **Card padding**: `30px`
- **Section spacing**: `50px` - `60px` between sections

### Margins
- **Header bottom**: `60px`
- **Section header bottom**: `25px`

### Grid Gaps
- **Quiz grid gap**: `20px`

## Layout

### Container
```css
max-width: 1000px;
margin: 0 auto;
```

### Grid System
```css
display: grid;
grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
gap: 20px;
```

Use CSS Grid with auto-fit for responsive layouts without media queries.

## Components

### Cards
```css
background: white;
border: 1px solid #e0e0e0;
border-radius: 8px;
padding: 30px;
transition: all 0.2s ease;
```

**Hover state**:
```css
border-color: #999;
box-shadow: 0 2px 8px rgba(0,0,0,0.08);
transform: translateY(-2px);
```

### Buttons
- Use same card styling principles
- Subtle hover effects (no dramatic color changes)
- Clear focus states for accessibility

### Borders
- Use thin borders: `1px solid`
- Border radius: `8px` for cards and interactive elements
- Divider lines: `1px solid #e0e0e0`

## Interactions & Animations

### Transitions
```css
transition: all 0.2s ease;
```
Keep transitions short (0.2s) and smooth.

### Hover Effects
- **Translate**: Maximum `translateY(-2px)` for lift effect
- **Shadow**: Subtle shadows only: `0 2px 8px rgba(0,0,0,0.08)`
- **Border**: Change color from `#e0e0e0` to `#999`
- **NO**: Scale transforms, rotation, color gradients, or dramatic effects

### Animations
**Avoid**: Bouncing, floating, spinning, gradient shifts, confetti, or any continuous animations.

**Exception**: Very subtle fade-ins on page load are acceptable if needed for progressive enhancement.

## What to Avoid

### ❌ Don't Use
- Bright gradient backgrounds
- Multiple competing accent colors
- Comic Sans or playful fonts for main UI (emojis are fine as decorative elements)
- Continuous animations (bouncing, floating, spinning)
- Dramatic hover effects (large scale, rotation, color shifts)
- Drop shadows on non-hover states
- Decorative elements (sparkles, stars, confetti)
- Multiple border colors within one component

### ✅ Do Use
- Subtle shadows on hover only
- Single-color borders
- System fonts
- Ample whitespace
- Clear hierarchy through size and weight
- Consistent spacing scale
- Emoji icons (sparingly, for quiz identification)

## Responsive Design

### Breakpoint
```css
@media (max-width: 768px) {
  /* Mobile adjustments */
}
```

### Mobile Adjustments
- Reduce padding: `30px 15px`
- Reduce font sizes proportionally
- Single column grid: `grid-template-columns: 1fr`
- Maintain visual hierarchy

## Accessibility

- Maintain color contrast ratios (WCAG AA minimum)
- Use semantic HTML elements
- Ensure interactive elements have clear hover/focus states
- Keep text readable (minimum 0.95em for body)
- Use descriptive link text

## Code Organization

### Structure
1. CSS reset (`* { margin: 0; padding: 0; box-sizing: border-box; }`)
2. Base styles (body, typography)
3. Layout (container, grid)
4. Components (header, cards, footer)
5. Responsive styles (media queries at end)

### Consistency
- Use consistent class naming
- Group related styles together
- Comment major sections
- Avoid inline styles in HTML

## Example Implementation

See `index.html` for the reference implementation of this style guide.

### Quick Reference
```css
/* Colors */
--bg-page: #fafafa;
--bg-card: #ffffff;
--text-primary: #1a1a1a;
--text-secondary: #666666;
--border-default: #e0e0e0;
--border-hover: #999999;

/* Typography */
--font-system: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Helvetica Neue', Arial, sans-serif;
--weight-light: 300;
--weight-regular: 400;
--weight-medium: 500;

/* Spacing */
--spacing-sm: 20px;
--spacing-md: 30px;
--spacing-lg: 50px;
--spacing-xl: 60px;

/* Effects */
--transition-default: all 0.2s ease;
--shadow-hover: 0 2px 8px rgba(0,0,0,0.08);
--radius-default: 8px;
```

Note: While CSS custom properties are shown above for clarity, the actual implementation currently uses direct values for broader browser compatibility.
