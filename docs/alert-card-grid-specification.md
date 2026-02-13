# Alert, Card, and Grid System Specification

**Version**: 1.0.0  
**Date**: 2026-02-13  
**Components**: Alert/Notification, Card, Grid System

---

## 1. Alert/Notification Component

### Overview
Alert components provide contextual feedback messages for typical user actions with a handful of available and flexible alert messages.

### Design Principles
- Clear visual hierarchy
- Appropriate use of color for message types
- Dismissible by default (optional)
- Icon support for quick recognition
- Accessible to screen readers
- Container Query responsive

### Variants

#### By Type (4 variants)
1. **Success** - Green (#58BE89)
   - Use: Successful operations, confirmations
   - Icon: Checkmark ✓
   
2. **Error** - Red
   - Use: Errors, failed operations
   - Icon: Warning ⚠
   
3. **Warning** - Yellow/Orange
   - Use: Warnings, cautions
   - Icon: Alert ⚠
   
4. **Info** - Blue (#3498db)
   - Use: Information, tips
   - Icon: Info ℹ

#### By Style (3 variants)
1. **Solid** - Filled background
2. **Outlined** - Border only
3. **Subtle** - Light background

#### By Size (3 sizes)
1. **Small** - Compact alerts
2. **Base** - Default size
3. **Large** - Prominent alerts

### Features

#### Dismissible Alert
- Close button (×) on the right
- Smooth fade-out animation
- Optional auto-dismiss after N seconds

#### With Icon
- Icon on the left
- SVG or emoji support
- Consistent sizing

#### With Title
- Bold title text
- Body text below
- Optional link/action button

#### With Action
- Action button on the right
- Link support
- Multiple actions support

### Structure

```html
<div class="alert alert--success">
  <span class="alert__icon">✓</span>
  <div class="alert__content">
    <strong class="alert__title">Success!</strong>
    <p class="alert__message">Your changes have been saved.</p>
  </div>
  <button class="alert__close" aria-label="Close">×</button>
</div>
```

### Accessibility
- `role="alert"` for immediate announcements
- `role="status"` for less urgent messages
- `aria-live="polite"` or `"assertive"`
- Close button with `aria-label`
- Sufficient color contrast (WCAG AAA)

---

## 2. Card Component

### Overview
Cards are flexible content containers with multiple variants for different use cases.

### Design Principles
- Flexible layout system
- Consistent spacing and borders
- Image support with proper aspect ratios
- Hover effects (subtle)
- Container Query responsive
- Modular sections (header, body, footer)

### Variants

#### By Style (3 variants)
1. **Default** - With border and shadow
2. **Elevated** - Prominent shadow
3. **Outlined** - Border only, no shadow

#### By Size (3 sizes)
1. **Small** - Compact cards
2. **Base** - Default size
3. **Large** - Prominent cards

### Structure

```html
<div class="card">
  <img src="image.jpg" alt="..." class="card__image">
  <div class="card__header">
    <h3 class="card__title">Card Title</h3>
    <p class="card__subtitle">Subtitle text</p>
  </div>
  <div class="card__body">
    <p>Card content goes here.</p>
  </div>
  <div class="card__footer">
    <button class="btn btn--primary">Action</button>
    <button class="btn btn--ghost">Cancel</button>
  </div>
</div>
```

### Features

#### Image Support
- Top image (full width)
- Side image (left or right)
- Background image
- Aspect ratio control (16:9, 4:3, 1:1)

#### Header Section
- Title
- Subtitle
- Icon/Avatar support
- Action menu (optional)

#### Body Section
- Content area
- Flexible height
- Scrollable (optional)

#### Footer Section
- Actions/buttons
- Metadata
- Links

#### Interactive States
- Hover effect (lift + shadow)
- Focus state
- Active/pressed state
- Disabled state

### Container Queries

```css
@container (max-width: 400px) {
  .card {
    /* Stack layout */
  }
}

@container (min-width: 600px) {
  .card--horizontal {
    /* Side-by-side layout */
  }
}
```

---

## 3. Grid System

### Overview
A flexible, responsive grid system using CSS Grid with Container Queries support.

### Design Principles
- 12-column base grid
- Flexible column spans
- Auto-fit and auto-fill support
- Gap utilities
- Container Query responsive
- No fixed breakpoints

### Grid Types

#### 1. Classic 12-Column Grid
```css
.grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  gap: var(--spacing-md);
}

.col-6 {
  grid-column: span 6;
}
```

#### 2. Auto-Fit Grid
```css
.grid--auto-fit {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-md);
}
```

#### 3. Auto-Fill Grid
```css
.grid--auto-fill {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  gap: var(--spacing-md);
}
```

### Column Spans
- `.col-1` to `.col-12` - Explicit spans
- `.col-auto` - Auto-size based on content
- `.col-full` - Full width (span 12)

### Gap Utilities
- `.gap-0` - No gap
- `.gap-xs` - 0.5rem
- `.gap-sm` - 0.75rem
- `.gap-md` - 1rem (default)
- `.gap-lg` - 1.5rem
- `.gap-xl` - 2rem
- `.gap-2xl` - 3rem
- `.gap-3xl` - 4rem

### Row Gap & Column Gap
- `.gap-x-{size}` - Column gap only
- `.gap-y-{size}` - Row gap only

### Alignment Utilities
- `.items-start`, `.items-center`, `.items-end` - Align items
- `.justify-start`, `.justify-center`, `.justify-end` - Justify content
- `.place-center` - Center both axes

### Container Query Breakpoints

```css
@container (max-width: 400px) {
  .col-sm-12 { grid-column: span 12; }
}

@container (min-width: 768px) {
  .col-md-6 { grid-column: span 6; }
}

@container (min-width: 1024px) {
  .col-lg-4 { grid-column: span 4; }
}
```

### Examples

#### Responsive 3-Column Grid
```html
<div class="grid grid--auto-fit gap-md">
  <div class="card">Card 1</div>
  <div class="card">Card 2</div>
  <div class="card">Card 3</div>
</div>
```

#### 12-Column Layout
```html
<div class="grid gap-md">
  <div class="col-8">Main content</div>
  <div class="col-4">Sidebar</div>
</div>
```

#### Masonry-style Grid
```css
.grid--masonry {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
  grid-auto-rows: 10px;
  gap: var(--spacing-md);
}
```

---

## Accessibility Requirements

### Alert Component
- `role="alert"` for critical messages
- `role="status"` for status updates
- `aria-live="assertive"` or `"polite"`
- Color contrast: 7:1 (AAA)
- Close button: keyboard accessible
- Screen reader announces message

### Card Component
- Semantic HTML (`<article>`, `<section>`)
- Proper heading hierarchy
- Image alt text required
- Interactive elements keyboard accessible
- Focus indicators visible
- Link/button in card accessible

### Grid System
- Logical tab order maintained
- Focus visible on grid items
- No layout shifts on resize
- Content readable at all sizes

---

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

Progressive enhancement for older browsers.

---

## Performance Targets

- CSS Size: < 10KB (gzipped) per component
- Load Time: < 50ms
- Render Time: < 16ms (60fps)
- No layout shift (CLS = 0)

---

## Implementation Checklist

### Alert Component
- [ ] Base alert styles
- [ ] Success, Error, Warning, Info variants
- [ ] Solid, Outlined, Subtle styles
- [ ] Icon support
- [ ] Title support
- [ ] Close button
- [ ] Dismissible functionality (CSS-only)
- [ ] Container Query responsive
- [ ] Accessibility attributes

### Card Component
- [ ] Base card styles
- [ ] Header, Body, Footer sections
- [ ] Image support (top, side, background)
- [ ] Elevated and Outlined variants
- [ ] Hover effects
- [ ] Container Query responsive
- [ ] Aspect ratio utilities
- [ ] Interactive states

### Grid System
- [ ] 12-column grid base
- [ ] Column span utilities (1-12)
- [ ] Auto-fit grid
- [ ] Auto-fill grid
- [ ] Gap utilities (xs, sm, md, lg, xl)
- [ ] Row/column gap utilities
- [ ] Alignment utilities
- [ ] Container Query responsive classes

---

## Testing Strategy

### Visual Testing
- All variants in isolation
- Combination testing
- Responsive behavior
- Dark mode support (future)

### Accessibility Testing
- Keyboard navigation
- Screen reader testing
- Contrast ratio verification
- Focus indicator visibility

### Cross-browser Testing
- Chrome, Firefox, Safari, Edge
- Mobile browsers
- Tablet browsers

---

**Status**: Ready for Implementation  
**Estimated Time**: 4-6 hours total
