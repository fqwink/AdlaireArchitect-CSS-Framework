# Utility Classes System - Technical Specification
**Adlaire Architect CSS Framework v0.6.0**  
**Date**: 2026-02-13  
**Component**: Utility Classes System  
**Priority**: Tier 1 (Highest)

---

## 📋 Overview

The Utility Classes System provides a comprehensive set of atomic CSS classes for rapid UI development. This system enables developers to build layouts and style components using utility classes without writing custom CSS.

### Key Features
- **200+ utility classes**
- **Container Queries responsive variants**
- **8pt Grid System compliance**
- **BEM naming convention**
- **WCAG 2.1 AAA compliant**
- **Dark mode support**

---

## 🎯 Design Principles

1. **Atomic Design**: Each class does one thing well
2. **Consistent Naming**: Predictable, intuitive class names
3. **Container Queries First**: Responsive to container size, not viewport
4. **8pt Grid**: All spacing values follow 8pt grid
5. **Performance**: Minimal CSS, maximum reusability
6. **Accessibility**: All utilities maintain WCAG compliance

---

## 📦 Utility Categories

### 1. Display Utilities

**Classes**: 16+  
**File**: `src/utilities/display.css`

```css
/* Display Types */
.d-none          /* display: none */
.d-block         /* display: block */
.d-inline        /* display: inline */
.d-inline-block  /* display: inline-block */
.d-flex          /* display: flex */
.d-inline-flex   /* display: inline-flex */
.d-grid          /* display: grid */
.d-inline-grid   /* display: inline-grid */

/* Container Query Variants */
@container (min-width: 640px) {
  .d-sm-none, .d-sm-block, .d-sm-flex, .d-sm-grid
}
@container (min-width: 768px) {
  .d-md-none, .d-md-block, .d-md-flex, .d-md-grid
}
@container (min-width: 1024px) {
  .d-lg-none, .d-lg-block, .d-lg-flex, .d-lg-grid
}
```

---

### 2. Flexbox Utilities

**Classes**: 50+  
**File**: `src/utilities/flexbox.css`

#### Flex Direction
```css
.flex-row            /* flex-direction: row */
.flex-row-reverse    /* flex-direction: row-reverse */
.flex-col            /* flex-direction: column */
.flex-col-reverse    /* flex-direction: column-reverse */
```

#### Flex Wrap
```css
.flex-wrap           /* flex-wrap: wrap */
.flex-nowrap         /* flex-wrap: nowrap */
.flex-wrap-reverse   /* flex-wrap: wrap-reverse */
```

#### Justify Content
```css
.justify-start       /* justify-content: flex-start */
.justify-end         /* justify-content: flex-end */
.justify-center      /* justify-content: center */
.justify-between     /* justify-content: space-between */
.justify-around      /* justify-content: space-around */
.justify-evenly      /* justify-content: space-evenly */
```

#### Align Items
```css
.items-start         /* align-items: flex-start */
.items-end           /* align-items: flex-end */
.items-center        /* align-items: center */
.items-baseline      /* align-items: baseline */
.items-stretch       /* align-items: stretch */
```

#### Align Self
```css
.self-auto           /* align-self: auto */
.self-start          /* align-self: flex-start */
.self-end            /* align-self: flex-end */
.self-center         /* align-self: center */
.self-stretch        /* align-self: stretch */
```

#### Flex Grow/Shrink
```css
.flex-1              /* flex: 1 1 0% */
.flex-auto           /* flex: 1 1 auto */
.flex-initial        /* flex: 0 1 auto */
.flex-none           /* flex: none */
```

#### Gap (8pt Grid)
```css
.gap-0               /* gap: 0 */
.gap-1               /* gap: 4px */
.gap-2               /* gap: 8px */
.gap-3               /* gap: 12px */
.gap-4               /* gap: 16px */
.gap-5               /* gap: 20px */
.gap-6               /* gap: 24px */
.gap-8               /* gap: 32px */
.gap-10              /* gap: 40px */
.gap-12              /* gap: 48px */
.gap-16              /* gap: 64px */

/* Row/Column Gap */
.gap-x-0 through .gap-x-16
.gap-y-0 through .gap-y-16
```

---

### 3. Grid Utilities

**Classes**: 30+  
**File**: `src/utilities/grid.css`

#### Grid Template Columns
```css
.grid-cols-1         /* grid-template-columns: repeat(1, 1fr) */
.grid-cols-2         /* grid-template-columns: repeat(2, 1fr) */
.grid-cols-3         /* grid-template-columns: repeat(3, 1fr) */
.grid-cols-4         /* grid-template-columns: repeat(4, 1fr) */
.grid-cols-6         /* grid-template-columns: repeat(6, 1fr) */
.grid-cols-12        /* grid-template-columns: repeat(12, 1fr) */
.grid-cols-auto      /* grid-template-columns: auto */
```

#### Grid Column Span
```css
.col-span-1          /* grid-column: span 1 / span 1 */
.col-span-2          /* grid-column: span 2 / span 2 */
/* ... through col-span-12 */
.col-span-full       /* grid-column: 1 / -1 */
```

#### Grid Placement
```css
.place-items-center  /* place-items: center */
.place-content-center /* place-content: center */
.grid-flow-row       /* grid-auto-flow: row */
.grid-flow-col       /* grid-auto-flow: column */
```

---

### 4. Spacing Utilities

**Classes**: 120+  
**File**: `src/utilities/spacing.css`

#### 8pt Grid Scale
```
0   = 0px
1   = 4px
2   = 8px
3   = 12px
4   = 16px
5   = 20px
6   = 24px
8   = 32px
10  = 40px
12  = 48px
16  = 64px
20  = 80px
24  = 96px
```

#### Margin
```css
/* All sides */
.m-0, .m-1, .m-2, .m-3, .m-4, .m-6, .m-8, .m-10, .m-12, .m-16

/* Horizontal (left + right) */
.mx-0, .mx-1, .mx-2, .mx-3, .mx-4, .mx-6, .mx-8, .mx-10, .mx-12, .mx-16
.mx-auto

/* Vertical (top + bottom) */
.my-0, .my-1, .my-2, .my-3, .my-4, .my-6, .my-8, .my-10, .my-12, .my-16

/* Individual sides */
.mt-0 through .mt-16  /* margin-top */
.mr-0 through .mr-16  /* margin-right */
.mb-0 through .mb-16  /* margin-bottom */
.ml-0 through .ml-16  /* margin-left */
```

#### Padding
```css
/* All sides */
.p-0, .p-1, .p-2, .p-3, .p-4, .p-6, .p-8, .p-10, .p-12, .p-16

/* Horizontal (left + right) */
.px-0, .px-1, .px-2, .px-3, .px-4, .px-6, .px-8, .px-10, .px-12, .px-16

/* Vertical (top + bottom) */
.py-0, .py-1, .py-2, .py-3, .py-4, .py-6, .py-8, .py-10, .py-12, .py-16

/* Individual sides */
.pt-0 through .pt-16  /* padding-top */
.pr-0 through .pr-16  /* padding-right */
.pb-0 through .pb-16  /* padding-bottom */
.pl-0 through .pl-16  /* padding-left */
```

---

### 5. Position Utilities

**Classes**: 25+  
**File**: `src/utilities/position.css`

#### Position Types
```css
.position-static     /* position: static */
.position-relative   /* position: relative */
.position-absolute   /* position: absolute */
.position-fixed      /* position: fixed */
.position-sticky     /* position: sticky */
```

#### Position Values
```css
/* Top */
.top-0, .top-1, .top-2, .top-4, .top-8, .top-auto

/* Right */
.right-0, .right-1, .right-2, .right-4, .right-8, .right-auto

/* Bottom */
.bottom-0, .bottom-1, .bottom-2, .bottom-4, .bottom-8, .bottom-auto

/* Left */
.left-0, .left-1, .left-2, .left-4, .left-8, .left-auto

/* Inset (all sides) */
.inset-0             /* top, right, bottom, left: 0 */
```

---

### 6. Sizing Utilities

**Classes**: 40+  
**File**: `src/utilities/sizing.css`

#### Width
```css
.w-auto              /* width: auto */
.w-full              /* width: 100% */
.w-screen            /* width: 100vw */
.w-1\/2              /* width: 50% */
.w-1\/3              /* width: 33.333% */
.w-2\/3              /* width: 66.666% */
.w-1\/4              /* width: 25% */
.w-3\/4              /* width: 75% */
.w-1\/5              /* width: 20% */
```

#### Height
```css
.h-auto              /* height: auto */
.h-full              /* height: 100% */
.h-screen            /* height: 100vh */
```

#### Min/Max Width
```css
.min-w-0             /* min-width: 0 */
.min-w-full          /* min-width: 100% */

.max-w-xs            /* max-width: 20rem (320px) */
.max-w-sm            /* max-width: 24rem (384px) */
.max-w-md            /* max-width: 28rem (448px) */
.max-w-lg            /* max-width: 32rem (512px) */
.max-w-xl            /* max-width: 36rem (576px) */
.max-w-2xl           /* max-width: 42rem (672px) */
.max-w-3xl           /* max-width: 48rem (768px) */
.max-w-4xl           /* max-width: 56rem (896px) */
.max-w-5xl           /* max-width: 64rem (1024px) */
.max-w-full          /* max-width: 100% */
```

#### Min/Max Height
```css
.min-h-0             /* min-height: 0 */
.min-h-full          /* min-height: 100% */
.min-h-screen        /* min-height: 100vh */

.max-h-full          /* max-height: 100% */
.max-h-screen        /* max-height: 100vh */
```

---

### 7. Overflow Utilities

**Classes**: 12+  
**File**: `src/utilities/overflow.css`

```css
.overflow-auto       /* overflow: auto */
.overflow-hidden     /* overflow: hidden */
.overflow-visible    /* overflow: visible */
.overflow-scroll     /* overflow: scroll */

.overflow-x-auto     /* overflow-x: auto */
.overflow-x-hidden   /* overflow-x: hidden */
.overflow-x-scroll   /* overflow-x: scroll */

.overflow-y-auto     /* overflow-y: auto */
.overflow-y-hidden   /* overflow-y: hidden */
.overflow-y-scroll   /* overflow-y: scroll */
```

---

### 8. Z-Index Utilities

**Classes**: 7  
**File**: `src/utilities/z-index.css`

```css
.z-0                 /* z-index: 0 */
.z-10                /* z-index: 10 */
.z-20                /* z-index: 20 */
.z-30                /* z-index: 30 */
.z-40                /* z-index: 40 */
.z-50                /* z-index: 50 */
.z-auto              /* z-index: auto */
```

---

### 9. Visibility Utilities

**Classes**: 10+  
**File**: `src/utilities/visibility.css`

```css
.visible             /* visibility: visible */
.invisible           /* visibility: hidden */

.opacity-0           /* opacity: 0 */
.opacity-25          /* opacity: 0.25 */
.opacity-50          /* opacity: 0.5 */
.opacity-75          /* opacity: 0.75 */
.opacity-100         /* opacity: 1 */

.sr-only             /* Screen reader only (visually hidden) */
```

---

### 10. Border Utilities

**Classes**: 30+  
**File**: `src/utilities/borders.css`

#### Border Width
```css
.border              /* border-width: 1px */
.border-0            /* border-width: 0 */
.border-2            /* border-width: 2px */
.border-4            /* border-width: 4px */

.border-t            /* border-top-width: 1px */
.border-r            /* border-right-width: 1px */
.border-b            /* border-bottom-width: 1px */
.border-l            /* border-left-width: 1px */
```

#### Border Radius
```css
.rounded-none        /* border-radius: 0 */
.rounded-sm          /* border-radius: 2px */
.rounded             /* border-radius: 4px */
.rounded-md          /* border-radius: 6px */
.rounded-lg          /* border-radius: 8px */
.rounded-xl          /* border-radius: 12px */
.rounded-2xl         /* border-radius: 16px */
.rounded-full        /* border-radius: 9999px */

/* Individual corners */
.rounded-t-{size}    /* top corners */
.rounded-r-{size}    /* right corners */
.rounded-b-{size}    /* bottom corners */
.rounded-l-{size}    /* left corners */
```

---

### 11. Shadow Utilities

**Classes**: 7  
**File**: `src/utilities/shadows.css`

```css
.shadow-none         /* box-shadow: none */
.shadow-sm           /* box-shadow: 0 1px 2px rgba(0,0,0,0.05) */
.shadow              /* box-shadow: 0 1px 3px rgba(0,0,0,0.1) */
.shadow-md           /* box-shadow: 0 4px 6px rgba(0,0,0,0.1) */
.shadow-lg           /* box-shadow: 0 10px 15px rgba(0,0,0,0.1) */
.shadow-xl           /* box-shadow: 0 20px 25px rgba(0,0,0,0.15) */
.shadow-2xl          /* box-shadow: 0 25px 50px rgba(0,0,0,0.25) */
```

---

### 12. Text Alignment Utilities

**Classes**: 4  
**File**: `src/utilities/text.css`

```css
.text-left           /* text-align: left */
.text-center         /* text-align: center */
.text-right          /* text-align: right */
.text-justify        /* text-align: justify */
```

---

## 🎨 Container Query Responsive System

All utilities support Container Query responsive variants:

### Breakpoints
```css
/* Small */
@container (min-width: 640px) {
  .d-sm-*, .flex-sm-*, .m-sm-*, etc.
}

/* Medium */
@container (min-width: 768px) {
  .d-md-*, .flex-md-*, .m-md-*, etc.
}

/* Large */
@container (min-width: 1024px) {
  .d-lg-*, .flex-lg-*, .m-lg-*, etc.
}

/* Extra Large */
@container (min-width: 1280px) {
  .d-xl-*, .flex-xl-*, .m-xl-*, etc.
}
```

### Naming Convention
```
{utility}-{breakpoint}-{value}

Examples:
.d-md-flex           /* display: flex at medium+ */
.flex-lg-row         /* flex-direction: row at large+ */
.m-sm-4              /* margin: 16px at small+ */
```

---

## 📂 File Structure

```
src/utilities/
├── _index.css           # Main utilities entry point
├── display.css          # Display utilities
├── flexbox.css          # Flexbox utilities
├── grid.css             # Grid utilities
├── spacing.css          # Margin & padding utilities
├── position.css         # Position utilities
├── sizing.css           # Width & height utilities
├── overflow.css         # Overflow utilities
├── z-index.css          # Z-index utilities
├── visibility.css       # Visibility & opacity utilities
├── borders.css          # Border & border-radius utilities
├── shadows.css          # Box-shadow utilities
└── text.css             # Text alignment utilities
```

---

## 🎯 Usage Examples

### Layout Example
```html
<div class="d-flex flex-col gap-4 p-6">
  <div class="d-flex justify-between items-center">
    <h1>Title</h1>
    <button>Action</button>
  </div>
  <div class="grid-cols-3 gap-4 d-md-grid d-sm-block">
    <div>Column 1</div>
    <div>Column 2</div>
    <div>Column 3</div>
  </div>
</div>
```

### Responsive Card
```html
<div class="p-4 p-md-6 rounded-lg shadow-md">
  <h2 class="mb-2 text-lg">Card Title</h2>
  <p class="mb-4">Card content</p>
  <div class="d-flex flex-col flex-md-row gap-2">
    <button>Primary</button>
    <button>Secondary</button>
  </div>
</div>
```

---

## ♿ Accessibility Considerations

1. **Screen Reader Only**: `.sr-only` class for visually hidden but accessible content
2. **Focus States**: All interactive elements maintain visible focus indicators
3. **Color Independence**: Utilities don't rely solely on color for meaning
4. **Semantic HTML**: Utilities complement, not replace, semantic HTML

---

## 🎨 Dark Mode Support

All utilities work seamlessly with dark mode:
- Shadow utilities use theme-aware colors
- Border utilities use theme variables
- No color-specific utilities (use theme variables)

---

## 📊 Expected Impact

### Before Utilities
```css
/* Custom CSS required */
.custom-card {
  display: flex;
  padding: 24px;
  border-radius: 8px;
  /* ... 10+ lines */
}
```

### After Utilities
```html
<!-- No custom CSS needed -->
<div class="d-flex p-6 rounded-lg shadow-md">
  <!-- Content -->
</div>
```

### Benefits
- ✅ **Development Speed**: 3-5x faster
- ✅ **Code Reduction**: 70% less custom CSS
- ✅ **Consistency**: 100% design system compliance
- ✅ **Maintainability**: Easier to update and refactor

---

## 🚀 Implementation Plan

### Phase 1: Core Utilities (Day 1-2)
- Display utilities
- Flexbox utilities
- Spacing utilities

### Phase 2: Layout Utilities (Day 2-3)
- Grid utilities
- Position utilities
- Sizing utilities

### Phase 3: Enhancement Utilities (Day 3)
- Overflow utilities
- Z-index utilities
- Visibility utilities
- Border utilities
- Shadow utilities
- Text utilities

### Phase 4: Responsive System (Day 3)
- Container Query variants
- Testing & optimization

### Phase 5: Documentation (Day 3)
- Usage documentation
- Demo page
- Code examples

---

## ✅ Acceptance Criteria

1. ✅ 200+ utility classes implemented
2. ✅ Container Query responsive variants working
3. ✅ 8pt Grid System compliance
4. ✅ BEM naming convention
5. ✅ Dark mode support
6. ✅ WCAG 2.1 AAA compliant
7. ✅ Complete documentation
8. ✅ Interactive demo page
9. ✅ All tests passing
10. ✅ Bundle size < 10 KB (utilities only)

---

**End of Specification**  
**Version**: 1.0  
**Status**: Approved ✅  
**Next**: Implementation
