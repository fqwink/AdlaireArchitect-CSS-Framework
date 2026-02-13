# Form Components Specification

## Overview

Form components are essential building blocks for user input and interaction. This specification defines the design and implementation of all form-related components for the Adlaire Architect CSS Framework.

**Version**: 1.0.0  
**Date**: 2026-02-13  
**Status**: Implementation Phase

---

## Design Principles

### 1. Accessibility First (WCAG 2.1 AAA)
- Clear focus indicators with high contrast
- Proper ARIA attributes support
- Keyboard navigation (Tab, Shift+Tab, Arrow keys)
- Screen reader compatibility
- Color is not the only indicator of state

### 2. Container Queries First
- All components respond to their container size
- No reliance on viewport media queries
- Fluid typography and spacing

### 3. Brand Color Integration
- Primary: Emerald Green (#00a968)
- Secondary: Blue Sky (#3498db)
- Success: Solitude (#58BE89)
- Error: Red variants
- Neutral: Gray scales

### 4. Progressive Enhancement
- Works without JavaScript
- Native HTML form elements
- Custom styling as enhancement

---

## Component Inventory

### 1. Text Input

#### Sizes
- **Small** (`input--small`): Height 32px, padding 0.375rem 0.75rem
- **Base** (`input`): Height 40px, padding 0.5rem 1rem
- **Large** (`input--large`): Height 48px, padding 0.625rem 1.25rem

#### States
- **Default**: Normal input state
- **Focus**: Active focus with brand color outline
- **Disabled**: Grayed out, not interactive
- **Error**: Red border and text
- **Success**: Green border and icon
- **Read-only**: Similar to disabled but different styling

#### Variants
- **Standard**: Default text input
- **With Icon**: Prefix or suffix icon support
- **With Label**: Floating or fixed label
- **Full Width**: 100% width option

#### Technical Requirements
```css
/* Focus */
- Outline: 2px solid var(--brand-primary-500)
- Outline offset: 2px
- Box-shadow for depth

/* Error */
- Border: 2px solid var(--semantic-error-500)
- Icon: Error icon (optional)
- Message: Error text below input

/* Success */
- Border: 2px solid var(--semantic-success-500)
- Icon: Check icon (optional)

/* Disabled */
- Opacity: 0.6
- Cursor: not-allowed
- Background: var(--neutral-100)
```

---

### 2. Textarea

#### Sizes
- **Small**: Min-height 80px
- **Base**: Min-height 120px
- **Large**: Min-height 160px

#### Features
- Resize control (none, vertical, both)
- Character counter support
- Auto-grow option (via JS, CSS provides base)
- Same states as Text Input

#### Technical Requirements
```css
/* Resize variants */
.textarea--no-resize { resize: none; }
.textarea--vertical { resize: vertical; }
.textarea--both { resize: both; }

/* Min/Max heights */
min-height: 120px;
max-height: 400px;
```

---

### 3. Select / Dropdown

#### Types
- **Native Select**: Styled native `<select>` element
- **Custom Dropdown**: Enhanced with custom styling

#### Sizes
- Small, Base, Large (same as Text Input)

#### States
- Default, Focus, Disabled, Error, Success

#### Features
- Custom arrow icon
- Multi-select support
- Optgroup support
- Search/Filter (via JS, CSS provides base)

#### Technical Requirements
```css
/* Custom arrow */
appearance: none;
background-image: url('data:image/svg+xml,...');
background-position: right 0.75rem center;
background-repeat: no-repeat;
background-size: 1rem;

/* Multi-select */
multiple: true;
size: 5; /* visible options */
```

---

### 4. Checkbox

#### Sizes
- **Small**: 16px × 16px
- **Base**: 20px × 20px
- **Large**: 24px × 24px

#### States
- Unchecked
- Checked
- Indeterminate (partially checked)
- Disabled
- Error
- Focus

#### Variants
- **Standard**: Default checkbox
- **With Label**: Inline label
- **Description**: Additional helper text
- **Switch**: Toggle switch variant

#### Technical Requirements
```css
/* Custom checkbox */
appearance: none;
width: 20px;
height: 20px;
border: 2px solid var(--neutral-400);
border-radius: var(--radius-sm);

/* Checked state */
&:checked {
  background-color: var(--brand-primary-500);
  border-color: var(--brand-primary-500);
  /* Checkmark via background-image or ::after */
}

/* Indeterminate */
&:indeterminate {
  background-color: var(--brand-primary-500);
  /* Dash icon */
}

/* Focus */
&:focus-visible {
  outline: 2px solid var(--brand-primary-500);
  outline-offset: 2px;
}
```

---

### 5. Radio Button

#### Sizes
- **Small**: 16px × 16px
- **Base**: 20px × 20px
- **Large**: 24px × 24px

#### States
- Unchecked
- Checked
- Disabled
- Error
- Focus

#### Variants
- **Standard**: Default radio
- **With Label**: Inline label
- **Group**: Radio button group with border
- **Cards**: Radio as selectable cards

#### Technical Requirements
```css
/* Custom radio */
appearance: none;
width: 20px;
height: 20px;
border: 2px solid var(--neutral-400);
border-radius: 50%; /* Circle */

/* Checked state */
&:checked {
  border-color: var(--brand-primary-500);
  /* Inner dot via ::after */
}

&:checked::after {
  content: '';
  display: block;
  width: 10px;
  height: 10px;
  border-radius: 50%;
  background: var(--brand-primary-500);
  margin: 3px; /* Center the dot */
}
```

---

### 6. Form Validation & Feedback

#### Message Types
- **Error**: Red, with error icon
- **Success**: Green, with success icon
- **Warning**: Yellow/Orange, with warning icon
- **Info**: Blue, with info icon
- **Helper**: Neutral, no icon (default)

#### Components
- **Inline Message**: Below input
- **Tooltip**: Appears on hover/focus
- **Summary**: Form-level validation summary

#### Technical Requirements
```css
/* Error message */
.form-message--error {
  color: var(--semantic-error-700);
  font-size: var(--font-size-sm);
  margin-top: var(--spacing-xs);
  display: flex;
  align-items: center;
  gap: var(--spacing-xs);
}

/* Icon */
.form-message__icon {
  width: 1rem;
  height: 1rem;
  flex-shrink: 0;
}
```

---

## Form Layout Patterns

### 1. Form Group
Standard layout for label + input + message

```html
<div class="form-group">
  <label class="form-label" for="input-id">Label</label>
  <input class="input" id="input-id" type="text">
  <span class="form-message">Helper text</span>
</div>
```

### 2. Inline Form
Horizontal layout with label and input side-by-side

```html
<div class="form-group form-group--inline">
  <label class="form-label" for="input-id">Label</label>
  <input class="input" id="input-id" type="text">
</div>
```

### 3. Stacked Form
Vertical layout (default)

### 4. Grid Form
Using CSS Grid for complex layouts

```css
.form-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: var(--spacing-md);
}
```

---

## Accessibility Requirements

### Keyboard Navigation
- **Tab**: Navigate forward through inputs
- **Shift+Tab**: Navigate backward
- **Space**: Toggle checkbox/radio
- **Arrow keys**: Navigate radio group
- **Enter**: Submit form (when on button)
- **Esc**: Clear/reset (optional)

### Focus Management
- Clear, high-contrast focus indicators
- Focus trap in modals/dialogs
- Skip links for long forms

### ARIA Support
```html
<!-- Required/Optional -->
<input aria-required="true" required>

<!-- Error state -->
<input aria-invalid="true" aria-describedby="error-id">
<span id="error-id" role="alert">Error message</span>

<!-- Disabled -->
<input aria-disabled="true" disabled>

<!-- Helper text -->
<input aria-describedby="helper-id">
<span id="helper-id">Helper text</span>
```

### Screen Reader Support
- Proper label associations (`for` attribute)
- Error announcements with `role="alert"`
- Status messages with `aria-live`
- Field descriptions with `aria-describedby`

---

## Responsive Behavior

### Container Queries
```css
/* Small containers (< 400px) */
@container (max-width: 400px) {
  .form-group--inline {
    flex-direction: column;
  }
  
  .form-label {
    margin-bottom: var(--spacing-xs);
  }
}

/* Medium containers (400px - 768px) */
@container (min-width: 400px) {
  .input {
    /* Adjust sizing */
  }
}
```

### Typography Scaling
- Font sizes scale with container
- Maintain readability at all sizes
- Use relative units (rem, em)

---

## Color Contrast Requirements

### WCAG 2.1 AAA Compliance
- **Normal text**: 7:1 contrast ratio
- **Large text** (18pt+): 4.5:1 contrast ratio
- **UI components**: 3:1 contrast ratio

### Test Cases
All form components must pass:
1. Color contrast analyzer
2. Keyboard-only navigation
3. Screen reader testing
4. Reduced motion support

---

## Browser Support

### Modern Browsers (Full Support)
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Opera 76+

### Progressive Enhancement
- Older browsers get simplified styling
- Core functionality remains intact
- No JavaScript required for basic operation

---

## Implementation Checklist

### Phase 1: Core Components
- [ ] Text Input (all sizes & states)
- [ ] Textarea (all variants)
- [ ] Select (native styling)

### Phase 2: Choice Components
- [ ] Checkbox (all variants)
- [ ] Radio Button (all variants)

### Phase 3: Validation & Feedback
- [ ] Form messages (all types)
- [ ] Validation states
- [ ] Error handling

### Phase 4: Layouts
- [ ] Form group
- [ ] Inline form
- [ ] Grid layouts

### Phase 5: Documentation
- [ ] Usage examples
- [ ] Accessibility guide
- [ ] Code snippets

---

## File Structure

```
src/
  components/
    forms.css           # Main entry point
    forms/
      input.css         # Text input
      textarea.css      # Textarea
      select.css        # Select/Dropdown
      checkbox.css      # Checkbox
      radio.css         # Radio button
      validation.css    # Validation & messages
      layouts.css       # Form layouts
```

---

## Testing Strategy

### Manual Testing
1. Visual regression testing
2. Keyboard navigation testing
3. Screen reader testing
4. Cross-browser testing

### Automated Testing
1. Contrast ratio checks
2. HTML validation
3. CSS validation
4. Accessibility audits (axe, WAVE)

### Test Coverage
- All sizes × all states × all variants
- Minimum 100% visual coverage
- Accessibility: AAA compliance

---

## Performance Targets

- **CSS Size**: < 8KB (gzipped) for all form components
- **Load Time**: < 50ms parse time
- **Render Time**: < 16ms for 60fps interactions
- **Bundle**: Modular imports supported

---

## Future Enhancements

### Phase 2 (Future)
- File upload component
- Date/Time pickers
- Color picker
- Range slider
- Search input with autocomplete
- Multi-select with tags
- Password strength indicator

---

## References

- [MDN: HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms)
- [WCAG 2.1 Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [ARIA Authoring Practices](https://www.w3.org/WAI/ARIA/apg/)
- [Container Queries](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Container_Queries)

---

**Document Status**: ✅ Approved for Implementation  
**Next Step**: Begin implementation of Text Input component
