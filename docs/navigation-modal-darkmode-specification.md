# Navigation, Modal, and Dark Mode Specification

**Version**: 1.0.0  
**Date**: 2026-02-13  
**Components**: Navigation, Modal/Dialog, Dark Mode Theme

---

## 1. Navigation Component

### Overview
Navigation components provide site-wide and contextual navigation patterns with responsive behavior.

### Components

#### 1.1 Navbar (Navigation Bar)
- **Purpose**: Primary site navigation
- **Position**: Fixed top, sticky, or static
- **Features**:
  - Logo/brand area
  - Navigation links
  - Search bar (optional)
  - User menu
  - Mobile hamburger menu
  - Dropdown support

#### 1.2 Dropdown Menu
- **Purpose**: Multi-level navigation
- **Trigger**: Hover or click
- **Features**:
  - Nested menus
  - Icons support
  - Dividers
  - Keyboard accessible

#### 1.3 Breadcrumb
- **Purpose**: Show current location in hierarchy
- **Features**:
  - Home icon
  - Separator (/, >, →)
  - Current page indicator
  - Truncation for long paths

### Navbar Structure

```html
<nav class="navbar">
  <div class="navbar__brand">
    <a href="/" class="navbar__logo">Logo</a>
  </div>
  
  <ul class="navbar__menu">
    <li class="navbar__item">
      <a href="#" class="navbar__link">Home</a>
    </li>
    <li class="navbar__item navbar__item--dropdown">
      <button class="navbar__link">Products ▼</button>
      <ul class="navbar__dropdown">
        <li><a href="#">Product 1</a></li>
        <li><a href="#">Product 2</a></li>
      </ul>
    </li>
  </ul>
  
  <button class="navbar__toggle" aria-label="Menu">☰</button>
</nav>
```

### Features

#### Responsive Behavior
- Desktop: Horizontal menu
- Tablet: Collapsible menu
- Mobile: Hamburger menu with slide-out

#### Variants
- **Default**: Standard navbar
- **Transparent**: Transparent background
- **Dark**: Dark background
- **Sticky**: Stays at top on scroll
- **Fixed**: Always at top

#### Dropdown
- Hover trigger (desktop)
- Click trigger (mobile)
- Keyboard navigation (Arrow keys, Enter, Esc)
- Multi-level support (nested dropdowns)

### Breadcrumb Structure

```html
<nav class="breadcrumb" aria-label="Breadcrumb">
  <ol class="breadcrumb__list">
    <li class="breadcrumb__item">
      <a href="/">Home</a>
    </li>
    <li class="breadcrumb__item">
      <a href="/products">Products</a>
    </li>
    <li class="breadcrumb__item breadcrumb__item--active">
      <span>Product Details</span>
    </li>
  </ol>
</nav>
```

### Accessibility
- `role="navigation"`
- `aria-label` for context
- `aria-current="page"` for current item
- `aria-expanded` for dropdowns
- Keyboard navigation (Tab, Arrow keys, Enter, Esc)
- Focus indicators
- Screen reader support

---

## 2. Modal/Dialog Component

### Overview
Modal dialogs are overlays that require user interaction before dismissing.

### Structure

```html
<div class="modal" role="dialog" aria-modal="true" aria-labelledby="modal-title">
  <div class="modal__overlay" data-dismiss="modal"></div>
  <div class="modal__container">
    <div class="modal__header">
      <h2 id="modal-title" class="modal__title">Modal Title</h2>
      <button class="modal__close" aria-label="Close">×</button>
    </div>
    <div class="modal__body">
      <p>Modal content goes here.</p>
    </div>
    <div class="modal__footer">
      <button class="btn btn--primary">Confirm</button>
      <button class="btn btn--ghost" data-dismiss="modal">Cancel</button>
    </div>
  </div>
</div>
```

### Features

#### Sizes
- **Small**: 400px max width
- **Base**: 600px max width (default)
- **Large**: 800px max width
- **Full**: 90% viewport width

#### Variants
- **Default**: Standard modal
- **Centered**: Vertically centered
- **Scrollable**: Scrollable body
- **No footer**: Header and body only

#### Overlay
- Semi-transparent background
- Click to dismiss (optional)
- Blur effect (optional)
- Animation on show/hide

#### Close Methods
- Close button (×)
- Overlay click
- Escape key
- Cancel button

### Accessibility
- `role="dialog"`
- `aria-modal="true"`
- `aria-labelledby` points to title
- `aria-describedby` for description
- Focus trap (Tab cycles within modal)
- Focus management (return to trigger on close)
- Escape key to close
- Screen reader announcements

### Animation
- Fade in/out
- Slide down/up
- Scale animation
- Smooth transitions (200-300ms)

---

## 3. Dark Mode Theme

### Overview
Complete dark mode theme with automatic and manual toggle support.

### Design Principles
- WCAG AAA contrast in both modes
- Smooth transitions between themes
- System preference detection
- User preference persistence
- All components supported

### Color Token Strategy

#### Light Mode (Current)
```css
:root {
  --bg-primary: #ffffff;
  --bg-secondary: #f9fafb;
  --text-primary: #111827;
  --text-secondary: #6b7280;
  --border-base: #e5e7eb;
}
```

#### Dark Mode
```css
:root[data-theme="dark"] {
  --bg-primary: #111827;
  --bg-secondary: #1f2937;
  --text-primary: #f9fafb;
  --text-secondary: #9ca3af;
  --border-base: #374151;
}
```

### Theme Structure

```css
/* Base tokens (light mode) */
:root { ... }

/* Dark mode override */
:root[data-theme="dark"] { ... }

/* System preference */
@media (prefers-color-scheme: dark) {
  :root:not([data-theme]) { ... }
}
```

### Theme Toggle

```html
<button class="theme-toggle" aria-label="Toggle theme">
  <span class="theme-toggle__icon">🌙</span>
</button>
```

```javascript
// JavaScript for theme toggle (minimal)
document.querySelector('.theme-toggle').addEventListener('click', () => {
  const root = document.documentElement;
  const current = root.getAttribute('data-theme');
  const next = current === 'dark' ? 'light' : 'dark';
  root.setAttribute('data-theme', next);
  localStorage.setItem('theme', next);
});
```

### Color Adjustments

#### Backgrounds
- Light: #ffffff → Dark: #111827
- Secondary: #f9fafb → Dark: #1f2937
- Tertiary: #f3f4f6 → Dark: #374151

#### Text
- Primary: #111827 → Dark: #f9fafb
- Secondary: #6b7280 → Dark: #9ca3af
- Tertiary: #9ca3af → Dark: #6b7280

#### Borders
- Base: #e5e7eb → Dark: #374151
- Strong: #d1d5db → Dark: #4b5563

#### Shadows
- Light: rgba(0,0,0,0.1) → Dark: rgba(0,0,0,0.5)
- Strong: rgba(0,0,0,0.2) → Dark: rgba(0,0,0,0.8)

### Brand Colors (Same in Both Modes)
Brand colors remain consistent but may need slight adjustments:
- Primary (Emerald Green): #00a968 - works in both
- Secondary (Blue Sky): #3498db - works in both
- Adjust hover/active states for dark bg

### Component Adjustments

All components need dark mode variants:
- Buttons: Adjust shadows and borders
- Forms: Input backgrounds darker
- Cards: Background and shadow adjustments
- Alerts: Background opacity changes
- Navigation: Dark backgrounds
- Modal: Overlay darker

### Transition
```css
* {
  transition: background-color 200ms ease, color 200ms ease, border-color 200ms ease;
}
```

### Persistence
- Use `localStorage` to save preference
- Check on page load
- Respect system preference if no user choice

### Testing
- Test all components in both modes
- Verify contrast ratios (WCAG AAA)
- Check for any hard-coded colors
- Test transitions smoothness
- Validate focus indicators visibility

---

## Implementation Priority

### Phase 1: Navigation (2-3 days)
1. Navbar base structure
2. Dropdown menus
3. Responsive mobile menu
4. Breadcrumb component
5. Accessibility features

### Phase 2: Modal (1-2 days)
1. Modal structure
2. Overlay and backdrop
3. Close functionality
4. Size variants
5. Accessibility and focus trap

### Phase 3: Dark Mode (2-3 days)
1. Dark mode color tokens
2. System preference detection
3. Toggle implementation
4. All components adaptation
5. Transition animations
6. Testing and refinement

---

## Accessibility Requirements

### Navigation
- Semantic HTML (`<nav>`, `<ul>`, `<li>`)
- ARIA labels and roles
- Keyboard navigation
- Focus indicators
- Screen reader support
- Skip links

### Modal
- Focus trap (Tab cycles within)
- Focus management (return on close)
- ARIA attributes (`role`, `aria-modal`, `aria-labelledby`)
- Escape key to close
- No background scroll
- Screen reader announcements

### Dark Mode
- Sufficient contrast (WCAG AAA)
- Smooth transitions (no flash)
- Respect `prefers-reduced-motion`
- System preference detection
- User preference persistence
- No loss of information

---

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

All features use standard CSS with progressive enhancement.

---

## Performance Targets

- Navigation: < 2KB (gzipped)
- Modal: < 2KB (gzipped)
- Dark Mode: < 3KB (gzipped)
- Total: < 7KB additional
- Transitions: 60fps smooth
- No layout shift

---

**Status**: Ready for Implementation  
**Estimated Time**: 5-8 days total
