# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Planned
- Utility Classes (Display, Position, Flex, etc.)
- Table Component
- Badge/Tag Component
- Pagination Component
- Tooltip Component
- Official Documentation Site
- npm Package Publication

## [0.5.0] - 2026-02-13

### Added - Navigation, Modal, and Dark Mode Theme ✅

#### Navigation Component
- **Navbar**: Complete navigation bar system
  - Logo/brand area
  - Horizontal menu (desktop)
  - Mobile hamburger menu
  - Responsive behavior
  - Sticky and fixed variants
  - Dark variant
- **Dropdown Menus**:
  - Hover and focus triggers
  - Nested menu support
  - Keyboard accessible (Arrow keys, Enter, Esc)
  - Smooth animations
  - Mobile-friendly
- **Breadcrumb**:
  - Hierarchy navigation
  - Multiple separator styles (/, ›, →)
  - Current page indicator
  - Semantic HTML
- **Accessibility**:
  - ARIA labels and roles
  - Keyboard navigation
  - Focus indicators
  - Screen reader support

#### Modal/Dialog Component
- **Complete Modal System**:
  - Overlay with backdrop blur
  - Header, Body, Footer structure
  - Close button with multiple methods
  - Smooth show/hide animations
- **4 Sizes**: Small (400px), Base (600px), Large (800px), Full (90vw)
- **Variants**:
  - Centered (default)
  - Top-aligned
  - Scrollable body
  - No header/footer options
- **Features**:
  - Focus trap (keyboard stays in modal)
  - Escape key to close
  - Overlay click to dismiss
  - Body scroll lock when open
  - Brand color variants
- **Accessibility**:
  - `role="dialog"` and `aria-modal="true"`
  - Focus management
  - Keyboard navigation
  - Screen reader compatible

#### Dark Mode Theme
- **Complete Dark Mode Implementation**:
  - All color tokens redefined for dark mode
  - System preference detection (`prefers-color-scheme`)
  - Manual toggle support
  - LocalStorage persistence
- **Color Tokens**:
  - Background colors (dark grays)
  - Text colors (light grays)
  - Border colors (medium grays)
  - Shadow adjustments (darker)
  - Brand color adjustments
- **All Components Supported**:
  - Buttons (ghost variant adjusted)
  - Forms (input backgrounds darker)
  - Cards (shadow enhancements)
  - Alerts (background opacity)
  - Navigation (dark backgrounds)
  - Modal (darker overlay)
  - Typography (text colors)
  - Grid (no changes needed)
- **Theme Toggle Button**:
  - Icon switch (🌙/☀️)
  - Smooth transitions
  - Accessible
  - Position flexible
- **Smooth Transitions**:
  - 200ms easing for color changes
  - No jarring switches
  - Reduced motion support
- **System Integration**:
  - `color-scheme` meta support
  - Respects user OS preference
  - Can be overridden manually

### Technical Achievements
- Pure CSS3 (minimal JS for theme toggle only)
- Container Queries throughout Navigation
- WCAG 2.1 AAA contrast in both modes
- BEM naming convention
- Focus trap in Modal (CSS-only where possible)
- Smooth theme transitions

### Documentation
- **Comprehensive Specification**: 8.7KB document
  - Navigation patterns
  - Modal best practices
  - Dark mode implementation guide
  - Accessibility requirements

### Statistics
- **New Components**: 3 (Navigation, Modal, Dark Mode)
- **Total Components**: 9 complete
- **CSS Added**: ~25KB uncompressed (~8KB gzipped)
- **Total CSS**: ~75KB uncompressed (~25KB gzipped)
- **Theme Toggle**: Requires <10 lines of JS
- **Files Added**: 4 new CSS files

### Files Changed
- Modified: 4 (README, package.json, CHANGELOG, adlaire-architect.css)
- Added: 4 (navigation.css, modal.css, dark-mode.css, specification.md)
- Total: 8 files

### Browser Support
- Dark Mode: Chrome 76+, Firefox 67+, Safari 12.1+
- All features: Chrome 90+, Firefox 88+, Safari 14+

## [0.4.0] - 2026-02-13

### Added - Alert, Card, and Grid System ✅

#### Alert/Notification Component
- **4 Variants**: Success, Error, Warning, Info
- **3 Styles**: Solid, Outlined, Subtle
- **3 Sizes**: Small, Base, Large
- **Features**:
  - Icon support with semantic icons
  - Dismissible with close button
  - Title and message support
  - Action buttons support
  - WCAG 2.1 AAA compliant
  - Container Queries responsive
  - `role="alert"` for accessibility

#### Card Component
- **Complete Structure**: Header, Body, Footer sections
- **Image Support**:
  - Top image (full width)
  - Horizontal layout (side image)
  - Aspect ratio control (16:9, 4:3, 1:1)
- **3 Variants**: Default, Elevated, Outlined
- **3 Sizes**: Small, Base, Large
- **Interactive Features**:
  - Hover effects (lift + shadow)
  - Focus states
  - Clickable cards
  - Brand color variants
- **Elements**:
  - Title and subtitle
  - Avatar support
  - Badge/tag support
  - Link support
  - Footer actions
- **Container Queries**: Full responsive support

#### Grid System
- **12-Column Base Grid**: Full flexibility
- **Auto-Fit Grid**: `repeat(auto-fit, minmax(250px, 1fr))`
- **Auto-Fill Grid**: `repeat(auto-fill, minmax(250px, 1fr))`
- **Column Spans**: `.col-1` through `.col-12`
- **Column Starts**: `.col-start-1` through `.col-start-12`
- **Row Spans**: `.row-span-1` through `.row-span-6`
- **Gap Utilities**: 8 sizes (0, xs, sm, md, lg, xl, 2xl, 3xl)
- **Row/Column Gaps**: `.gap-x-*` and `.gap-y-*`
- **Alignment Utilities**:
  - Align items (start, center, end, stretch, baseline)
  - Justify items and content
  - Self alignment
  - Place utilities
- **Grid Template Utilities**: `.grid-cols-{1-12}`, `.grid-rows-{1-6}`
- **Grid Flow**: Row, column, dense variants
- **Special Patterns**:
  - Masonry grid
  - Dashboard layout (2 columns, 1st wider)
  - Sidebar layouts
  - Holy Grail layout
- **Container Query Responsive**: Breakpoints for sm, md, lg, xl
- **100+ Utility Classes**

### Documentation
- **Comprehensive Specification**: 8.3KB document covering all three components
  - Design principles
  - Component variants
  - Usage examples
  - Accessibility requirements
  - Browser support

### Statistics
- **New Components**: 3 (Alert, Card, Grid)
- **Total Components**: 6 (Button, Typography, Forms, Alert, Card, Grid)
- **CSS Added**: ~30KB uncompressed (~10KB gzipped)
- **Total CSS**: ~50KB uncompressed (~20KB gzipped)
- **Utility Classes**: 150+ grid utilities
- **Component Variants**: 50+ alert/card variants

### Technical Achievements
- Pure CSS3 (no JavaScript)
- Container Queries throughout
- WCAG 2.1 AAA accessible
- BEM naming convention
- Reduced motion support
- Cross-browser compatible

### Files Changed
- Modified: 3 (README, package.json, adlaire-architect.css)
- Added: 4 (alerts.css, cards.css, grid.css, specification.md)
- Total: 7 files

## [0.3.0] - 2026-02-13
- Utility Classes (Spacing, Colors, Display, etc.)
- Dark Mode Theme
- High Contrast Theme
- Official Documentation Site
- npm Package Publication

## [0.3.0] - 2026-02-13

### Added - Complete Form Components System ✅
- **Form Components** - Comprehensive form system
  - Text Input component with all variants
  - Textarea component with resize controls
  - Select/Dropdown component with custom styling
  - Checkbox component with indeterminate state
  - Radio Button component with full styling
  - Form Labels (required, optional indicators)
  - Form Messages (error, success, warning, info, helper)
  - Form Validation states and styling
  - Form Layouts (stacked, inline, grid)
  
- **Text Input Features**
  - Size variants: small, base, large, xl
  - States: default, focus, hover, disabled, read-only
  - Validation states: error, success, warning
  - Focus indicators with high contrast
  - Placeholder styling
  - Prefix/suffix icon support
  
- **Textarea Features**
  - Size variants: small, base, large, xl
  - Resize control: none, vertical, horizontal, both
  - Same states as Text Input
  - Line height optimization for readability
  
- **Select/Dropdown Features**
  - Custom styled native select
  - Custom dropdown arrow (SVG)
  - Size variants: small, base, large, xl
  - Multiple select support
  - Optgroup support
  - Same validation states
  
- **Checkbox Features**
  - Size variants: small, base, large, xl
  - States: unchecked, checked, indeterminate
  - Custom checkmark icon
  - Disabled state styling
  - Error state variant
  
- **Radio Button Features**
  - Size variants: small, base, large, xl
  - Custom radio dot styling
  - Proper focus indicators
  - Disabled state support
  - Error state variant
  
- **Form Validation & Messages**
  - Error messages with icons
  - Success messages with icons
  - Warning messages with icons
  - Info messages with icons
  - Helper text styling
  - ARIA support for screen readers
  
- **Accessibility (WCAG 2.1 AAA)**
  - Clear focus indicators (2px outline, 2px offset)
  - High contrast ratios (7:1 for normal text)
  - Keyboard navigation support
  - Screen reader compatibility
  - ARIA attributes support
  - Reduced motion support
  
- **Container Queries**
  - Forms adapt to container size
  - Inline forms stack on small containers
  - Font sizes scale appropriately
  - Responsive layout changes
  
### Documentation
- **Forms Specification** - Comprehensive 10KB specification document
  - Design principles and accessibility requirements
  - Component inventory with all variants
  - Technical implementation details
  - ARIA support guidelines
  - Browser support policy
  - Testing strategy
  
- **Forms Demo Page** - Complete showcase (28KB)
  - All input sizes and states
  - Textarea variations
  - Select/dropdown examples
  - Checkbox demonstrations
  - Radio button groups
  - Complete contact form example
  - Over 50 live examples
  
### License
- **Apache License 2.0** - Added official open-source license
  - LICENSE file with full Apache 2.0 text
  - NOTICE file with copyright information
  - Updated all file headers with license
  
### Changed
- Updated `src/adlaire-architect.css`
  - Added import for `forms.css`
  - Updated version to 0.3.0
  - Updated license information to Apache 2.0
- Updated `README.md`
  - Version bump to 0.3.0
  - License changed to Apache 2.0
  - Status updated to "Form Components Complete"
- Updated `package.json`
  - Version 0.3.0
  - License field updated to Apache-2.0

### Statistics
- **Total Components**: 3 (Button, Typography, Forms)
- **Form Variants**: 100+ combinations
- **CSS Size**: ~20KB (uncompressed), ~6KB (gzipped)
- **Demo Examples**: 50+ live examples
- **Code Lines**: ~600 lines of CSS
- **Documentation**: 38KB total

### Technical Achievements
- Pure CSS3 implementation (no JavaScript required)
- Container Queries First architecture
- BEM naming convention throughout
- Full keyboard accessibility
- Screen reader support
- Progressive enhancement
- Reduced motion support

## [0.2.0] - 2026-02-13

### Added - Adlaire Brand Colors Integration ✅
- **Adlaire Brand Color System**
  - Official Adlaire Group brand colors fully integrated
  - Emerald Green (#00a968) as primary brand color
  - Blue Sky (#3498db) as secondary color
  - Summer Sky (#40AAEF) as accent color
  - Solitude (#58BE89) as success color
  - White Rat (#ecf0f1) and Silver Tree (#ECEEF1) as neutral colors
- New file: `src/tokens/adlaire-brand.css`
  - Complete color scales for all brand colors (50-900)
  - 5 full color scales (Emerald Green, Blue Sky, Summer Sky, Solitude, Neutral)
- Brand Color Guide documentation
  - Comprehensive guide: `docs/brand-colors.md`
  - Usage guidelines and best practices
  - Accessibility contrast ratios
  - CSS Variables reference
  - Color palette examples

### Changed
- Updated `src/tokens/root.css`
  - Replaced placeholder colors with official Adlaire brand colors
  - Primary color: #2196F3 → #00a968 (Emerald Green)
  - Secondary color: #00BCD4 → #3498db (Blue Sky)
  - Accent color: #FF5722 → #40AAEF (Summer Sky)
  - Success color: #00C853 → #58BE89 (Solitude)
  - Info color: Updated to Blue Sky
  - Neutral colors: Updated to White Rat / Silver Tree base
  - Focus ring color: Updated to match Emerald Green
- Updated `examples/demo.html`
  - Background gradient now uses Adlaire brand colors
  - Section headings use Emerald Green
  - Added Brand Colors showcase section
  - Updated color swatches and examples
  - Feature badges use brand colors
- Updated `src/adlaire-architect.css`
  - Added import for `adlaire-brand.css`

### Brand Identity
- ✅ **Differentiation Pillar #1 Complete**: Adlaire Group design token system
- All components now reflect official brand identity
- Consistent brand experience across the framework
- Ready for production use with official colors

### Documentation
- Added comprehensive Brand Color Guide (7.8KB)
- Updated all color references in documentation
- Added accessibility contrast information
- Included usage examples and guidelines

## [0.1.0] - 2026-02-13

### Added
- Initial project structure
- CSS Framework trend research report (2026)
- Detailed specification document
- Core CSS implementation
  - Modern CSS Reset
  - CSS Layers system (@layer)
  - Design Tokens (Root Variables)
- Container System
  - Container Query support
  - Max-width containers (xs, sm, md, lg, xl, 2xl, 3xl, 4xl, 5xl)
  - Fluid container
- Button Component
  - Size variants (xs, small, base, large, xl)
  - Color variants (primary, secondary, success, warning, error, info, neutral)
  - Style variants (solid, outline, ghost, link)
  - State modifiers (loading, active, disabled)
  - Layout modifiers (block, icon-only)
  - Button Group
  - Container Query responsive support
  - Full accessibility support (WCAG 2.1 AAA)
- Demo page with comprehensive examples
- Project documentation (README, specification)

### Technical Details
- Pure CSS3 only (no preprocessors)
- BEM naming convention
- Container Queries First approach
- Accessibility First design
- 8pt Grid System
- Comprehensive design token system
- Progressive enhancement support

### Documentation
- README.md with project overview and roadmap
- Research document: CSS Framework Trends 2026
- Specification document with detailed architecture
- Demo HTML page with live examples

### Development
- Git repository initialization
- Project structure setup
- Package.json configuration
- .gitignore setup

### Notes
- This is a development version, not production-ready

---

## Legend

- `Added` for new features
- `Changed` for changes in existing functionality
- `Deprecated` for soon-to-be removed features
- `Removed` for now removed features
- `Fixed` for any bug fixes
- `Security` in case of vulnerabilities
