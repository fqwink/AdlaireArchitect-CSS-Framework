# Table Component - Technical Specification
**Adlaire Architect CSS Framework v0.7.0**  
**Date**: 2026-02-13  
**Component**: Table Component  
**Priority**: Tier 1 (High)

---

## 📋 Overview

The Table Component provides a comprehensive, accessible, and responsive table system for displaying tabular data. Designed with Container Queries First approach, the table adapts intelligently to its container size.

### Key Features
- **Responsive**: Container Query-based responsive behavior
- **Accessible**: WCAG 2.1 AAA compliant with full keyboard navigation
- **Flexible**: Multiple variants, sizes, and features
- **Dark Mode**: Full dark mode support
- **BEM Naming**: Consistent naming convention
- **8pt Grid**: Spacing aligned to 8pt grid system

---

## 🎯 Design Goals

1. **Data Clarity**: Clear presentation of tabular data
2. **Scanability**: Easy to scan rows and columns
3. **Responsiveness**: Adapts to container size, not just viewport
4. **Accessibility**: Screen reader friendly, keyboard navigable
5. **Flexibility**: Support various data types and layouts
6. **Performance**: Efficient rendering of large datasets

---

## 📦 Component Structure

### Basic Structure
```html
<div class="table-container">
  <table class="table">
    <thead class="table__head">
      <tr class="table__row">
        <th class="table__header-cell">Header 1</th>
        <th class="table__header-cell">Header 2</th>
      </tr>
    </thead>
    <tbody class="table__body">
      <tr class="table__row">
        <td class="table__cell">Data 1</td>
        <td class="table__cell">Data 2</td>
      </tr>
    </tbody>
    <tfoot class="table__foot">
      <tr class="table__row">
        <td class="table__cell">Footer 1</td>
        <td class="table__cell">Footer 2</td>
      </tr>
    </tfoot>
  </table>
</div>
```

---

## 🎨 Variants

### 1. Basic Table
Default table styling with clean borders and spacing.

```css
.table {
  /* Base styles */
}
```

### 2. Striped Table
Alternating row background colors for better readability.

```html
<table class="table table--striped">
  <!-- content -->
</table>
```

### 3. Bordered Table
Full borders around all cells.

```html
<table class="table table--bordered">
  <!-- content -->
</table>
```

### 4. Hover Table
Row highlight on hover.

```html
<table class="table table--hover">
  <!-- content -->
</table>
```

### 5. Borderless Table
No borders, clean minimal look.

```html
<table class="table table--borderless">
  <!-- content -->
</table>
```

---

## 📏 Sizes

### Compact
Reduced padding for dense data display.

```html
<table class="table table--compact">
  <!-- content -->
</table>
```

### Base (Default)
Standard padding for balanced readability.

```html
<table class="table">
  <!-- content -->
</table>
```

### Comfortable
Increased padding for better readability.

```html
<table class="table table--comfortable">
  <!-- content -->
</table>
```

---

## 📱 Responsive Behavior

### 1. Responsive (Stack on Mobile)
On small containers, table stacks vertically.

```html
<table class="table table--responsive">
  <!-- content -->
</table>
```

Behavior:
- **Large containers**: Normal table layout
- **Small containers**: Each row becomes a card, cells stack vertically

### 2. Scrollable
Horizontal scroll on small containers.

```html
<div class="table-container table-container--scrollable">
  <table class="table">
    <!-- content -->
  </table>
</div>
```

### 3. Fixed Layout
Fixed table layout for consistent column widths.

```html
<table class="table table--fixed">
  <!-- content -->
</table>
```

---

## ✨ Features

### 1. Sortable Headers
Visual indicators for sortable columns.

```html
<th class="table__header-cell table__header-cell--sortable">
  Name
  <span class="table__sort-icon" aria-hidden="true">↕</span>
</th>
```

States:
- `.table__header-cell--sort-asc` (↑)
- `.table__header-cell--sort-desc` (↓)

### 2. Fixed Header
Header stays visible while scrolling.

```html
<div class="table-container table-container--fixed-header">
  <table class="table">
    <!-- content -->
  </table>
</div>
```

### 3. Sticky Column
First column stays fixed while scrolling horizontally.

```html
<table class="table table--sticky-column">
  <thead>
    <tr>
      <th class="table__header-cell table__header-cell--sticky">Name</th>
      <th class="table__header-cell">Email</th>
    </tr>
  </thead>
</table>
```

### 4. Row Selection
Visual feedback for selected rows.

```html
<tr class="table__row table__row--selected">
  <!-- content -->
</tr>
```

### 5. Cell Alignment
Horizontal alignment for cells.

```html
<td class="table__cell table__cell--align-left">Left</td>
<td class="table__cell table__cell--align-center">Center</td>
<td class="table__cell table__cell--align-right">Right</td>
```

### 6. Column Width
Predefined column widths.

```html
<colgroup>
  <col class="table__col table__col--auto">
  <col class="table__col table__col--20">
  <col class="table__col table__col--30">
</colgroup>
```

Widths: 10%, 20%, 30%, 40%, 50%, auto

---

## 🎨 Color Variants

### Brand Colors
```html
<table class="table table--brand-emerald">
  <!-- Emerald header background -->
</table>

<table class="table table--brand-blue">
  <!-- Blue header background -->
</table>
```

### Status Colors
```html
<tr class="table__row table__row--success">
  <!-- Success background -->
</tr>

<tr class="table__row table__row--error">
  <!-- Error background -->
</tr>

<tr class="table__row table__row--warning">
  <!-- Warning background -->
</tr>
```

---

## 📐 Spacing

All spacing follows 8pt Grid System:

- **Compact**: 8px (vertical), 12px (horizontal)
- **Base**: 12px (vertical), 16px (horizontal)
- **Comfortable**: 16px (vertical), 20px (horizontal)

---

## ♿ Accessibility

### ARIA Attributes
```html
<table class="table" role="table" aria-label="User data">
  <thead role="rowgroup">
    <tr role="row">
      <th role="columnheader" scope="col">Name</th>
    </tr>
  </thead>
  <tbody role="rowgroup">
    <tr role="row">
      <td role="cell">John Doe</td>
    </tr>
  </tbody>
</table>
```

### Sortable Tables
```html
<th class="table__header-cell table__header-cell--sortable"
    role="columnheader"
    aria-sort="ascending"
    tabindex="0">
  Name
</th>
```

### Screen Reader Support
- Caption element for table description
- Proper scope attributes on headers
- Row/column spans clearly indicated
- Sort state announced

### Keyboard Navigation
- **Tab**: Navigate between sortable headers
- **Enter/Space**: Trigger sort on header
- **Arrow Keys**: Navigate cells (optional)

---

## 🌙 Dark Mode Support

All table variants adapt to dark mode:

```css
[data-theme="dark"] .table {
  /* Dark background */
  /* Light text */
  /* Adjusted borders */
}
```

- Background: Dark gray
- Text: Light gray
- Borders: Medium gray
- Hover: Lighter dark gray
- Selected: Brand color with opacity

---

## 📊 Container Queries

Tables adapt based on container width:

```css
@container (max-width: 640px) {
  .table--responsive {
    /* Stack layout */
  }
}

@container (min-width: 768px) {
  .table {
    /* Standard layout */
  }
}
```

---

## 💻 Usage Examples

### Example 1: Basic Data Table
```html
<div class="table-container">
  <table class="table table--striped table--hover">
    <caption class="sr-only">User List</caption>
    <thead class="table__head">
      <tr class="table__row">
        <th class="table__header-cell">Name</th>
        <th class="table__header-cell">Email</th>
        <th class="table__header-cell">Role</th>
        <th class="table__header-cell">Status</th>
      </tr>
    </thead>
    <tbody class="table__body">
      <tr class="table__row">
        <td class="table__cell">John Doe</td>
        <td class="table__cell">john@example.com</td>
        <td class="table__cell">Admin</td>
        <td class="table__cell">
          <span class="badge badge--success">Active</span>
        </td>
      </tr>
      <tr class="table__row">
        <td class="table__cell">Jane Smith</td>
        <td class="table__cell">jane@example.com</td>
        <td class="table__cell">User</td>
        <td class="table__cell">
          <span class="badge badge--success">Active</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
```

### Example 2: Responsive Table
```html
<div class="table-container table-container--scrollable">
  <table class="table table--responsive table--bordered">
    <thead class="table__head">
      <tr class="table__row">
        <th class="table__header-cell">Product</th>
        <th class="table__header-cell table__cell--align-right">Price</th>
        <th class="table__header-cell table__cell--align-right">Quantity</th>
        <th class="table__header-cell table__cell--align-right">Total</th>
      </tr>
    </thead>
    <tbody class="table__body">
      <tr class="table__row">
        <td class="table__cell" data-label="Product">Widget A</td>
        <td class="table__cell table__cell--align-right" data-label="Price">$19.99</td>
        <td class="table__cell table__cell--align-right" data-label="Quantity">5</td>
        <td class="table__cell table__cell--align-right" data-label="Total">$99.95</td>
      </tr>
    </tbody>
  </table>
</div>
```

### Example 3: Sortable Table with Fixed Header
```html
<div class="table-container table-container--fixed-header" style="max-height: 400px;">
  <table class="table table--striped">
    <thead class="table__head">
      <tr class="table__row">
        <th class="table__header-cell table__header-cell--sortable" 
            aria-sort="none" 
            tabindex="0">
          Name
          <span class="table__sort-icon" aria-hidden="true">↕</span>
        </th>
        <th class="table__header-cell table__header-cell--sortable" 
            aria-sort="ascending" 
            tabindex="0">
          Date
          <span class="table__sort-icon" aria-hidden="true">↑</span>
        </th>
      </tr>
    </thead>
    <tbody class="table__body">
      <!-- Many rows... -->
    </tbody>
  </table>
</div>
```

---

## 🎨 Color Palette

### Header Colors
- Default: `var(--aa-bg-secondary)`
- Brand: `var(--aa-brand-emerald-500)` with white text
- Dark Mode: `var(--aa-bg-tertiary)`

### Row Colors
- Default: `var(--aa-bg-primary)`
- Striped: `var(--aa-bg-secondary)` for odd rows
- Hover: `var(--aa-bg-tertiary)`
- Selected: `var(--aa-brand-emerald-100)`

### Borders
- Default: `var(--aa-border-color)`
- Dark Mode: `rgba(255, 255, 255, 0.1)`

---

## 📦 File Structure

```
src/components/table.css
```

Single file containing all table styles (~600-800 lines).

---

## 🎯 Acceptance Criteria

1. ✅ Basic table structure and styling
2. ✅ 5 variants (striped, bordered, hover, borderless, responsive)
3. ✅ 3 sizes (compact, base, comfortable)
4. ✅ Sortable header support
5. ✅ Fixed header support
6. ✅ Sticky column support
7. ✅ Row selection states
8. ✅ Cell alignment utilities
9. ✅ Container Query responsive
10. ✅ Dark mode support
11. ✅ WCAG 2.1 AAA compliant
12. ✅ Full keyboard navigation
13. ✅ Screen reader accessible
14. ✅ Brand color variants
15. ✅ Complete documentation

---

## 📊 Expected Impact

### Before Table Component
```html
<!-- Custom CSS required for every table -->
<style>
  .my-table { /* 50+ lines of CSS */ }
  .my-table th { /* ... */ }
  .my-table td { /* ... */ }
  /* Responsive behavior */
  /* Dark mode */
  /* Hover effects */
</style>
```

### After Table Component
```html
<!-- Single class, full functionality -->
<table class="table table--striped table--hover table--responsive">
  <!-- content -->
</table>
```

### Benefits
- ✅ **Consistency**: Uniform table styling across applications
- ✅ **Productivity**: No custom CSS needed
- ✅ **Accessibility**: Built-in WCAG compliance
- ✅ **Responsive**: Container Query-based adaptation
- ✅ **Maintainability**: Centralized table styles

---

## 🚀 Implementation Plan

### Phase 1: Core Structure (Day 1)
- Basic table styles
- Table container
- Header, body, footer styling
- Cell and row basics

### Phase 2: Variants (Day 1)
- Striped variant
- Bordered variant
- Hover variant
- Borderless variant

### Phase 3: Responsive (Day 2)
- Container Query breakpoints
- Stack layout for mobile
- Scrollable container
- Fixed layout

### Phase 4: Features (Day 2)
- Sortable headers
- Fixed header
- Sticky column
- Row selection
- Cell alignment

### Phase 5: Polish (Day 2-3)
- Dark mode support
- Brand color variants
- Size variants
- Documentation
- Demo page

---

**End of Specification**  
**Version**: 1.0  
**Status**: Approved ✅  
**Next**: Implementation
