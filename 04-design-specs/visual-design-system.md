# Visual Design Specifications

**Project:** BY MB Consultancy Website Development  
**Document:** Complete Visual Design System  
**Version:** 1.0  
**Date:** June 2, 2025  
**Brand Compliance:** Official Brand Guidelines Implementation

## Design System Overview

This document establishes the complete visual design system for the BY MB Consultancy website, ensuring full compliance with the official brand guidelines while creating a professional, conversion-optimized user experience.

## Brand Identity Implementation

### Logo Usage and Placement

**Primary Logo Configuration:**
```
Header Logo:
- Position: Top left corner
- Size: 180px width (desktop), 120px width (mobile)
- Format: SVG for scalability
- Clear space: 20px minimum on all sides
```

**Logo Variations:**
- Main logo: Full "BY MB" with tagline "Success is a Journey, Not a Destination"
- Compact version: "BY MB" logo only (for mobile/small spaces)
- Dark background version: White text variation
- Light background version: Azure Radiance text

### Typography System

**Font Loading Strategy:**
```html
<link href="https://fonts.googleapis.com/css2?family=Poppins:wght@900&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
```

**Typography Hierarchy:**
```css
/* Heading Styles */
h1, .heading-xl {
  font-family: 'Poppins', sans-serif;
  font-weight: 900; /* Black */
  font-size: 3.5rem;
  line-height: 1.1;
  color: #447eff;
  margin-bottom: 1.5rem;
}

h2, .heading-lg {
  font-family: 'Poppins', sans-serif;
  font-weight: 900;
  font-size: 2.5rem;
  line-height: 1.2;
  color: #000000;
  margin-bottom: 1rem;
}

h3, .heading-md {
  font-family: 'Poppins', sans-serif;
  font-weight: 900;
  font-size: 1.75rem;
  line-height: 1.3;
  color: #333333;
  margin-bottom: 0.75rem;
}

/* Body Text Styles */
.text-xl {
  font-family: 'Roboto', sans-serif;
  font-size: 1.25rem;
  line-height: 1.6;
  color: #333333;
}

.text-lg {
  font-family: 'Roboto', sans-serif;
  font-size: 1.125rem;
  line-height: 1.6;
  color: #333333;
}

.text-base {
  font-family: 'Roboto', sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  color: #666666;
}

.text-sm {
  font-family: 'Roboto', sans-serif;
  font-size: 0.875rem;
  line-height: 1.5;
  color: #666666;
}
```

## Color System Implementation

### Brand Color Variables
```css
:root {
  /* Primary Brand Colors */
  --azure-radiance: #447eff;
  --brand-white: #ffffff;
  --brand-black: #000000;
  --accent-gold: #ffc554;
  
  /* Text Colors */
  --text-primary: #333333;
  --text-secondary: #666666;
  --text-muted: #999999;
  
  /* Background Colors */
  --bg-primary: #ffffff;
  --bg-secondary: #f8fafc;
  --bg-accent: rgba(68, 126, 255, 0.05);
  
  /* Border Colors */
  --border-light: #e2e8f0;
  --border-medium: #cbd5e0;
  --border-dark: #a0aec0;
  
  /* Status Colors */
  --success: #10b981;
  --warning: #f59e0b;
  --error: #ef4444;
}
```

### Color Application Guidelines

**Primary Azure Radiance (#447eff):**
- Hero section backgrounds
- Primary CTA buttons
- Navigation active states
- Key brand elements
- Section dividers and accents

**Accent Gold (#ffc554):**
- Secondary CTA buttons
- Highlight elements
- Special offers or promotions
- Important icons or badges

**Professional Grays:**
- Body text and descriptions
- Supporting information
- Form elements and inputs
- Footer content

## Button Design System

### Primary Button Styles
```css
.btn-primary {
  background: linear-gradient(135deg, #447eff 0%, #4169e1 100%);
  color: white;
  font-family: 'Poppins', sans-serif;
  font-weight: 900;
  font-size: 1rem;
  padding: 16px 32px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  box-shadow: 0 4px 14px rgba(68, 126, 255, 0.3);
}

.btn-primary:hover {
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(68, 126, 255, 0.4);
}
```

### Secondary Button Styles
```css
.btn-secondary {
  background: white;
  color: #447eff;
  font-family: 'Poppins', sans-serif;
  font-weight: 900;
  font-size: 1rem;
  padding: 16px 32px;
  border-radius: 8px;
  border: 2px solid #447eff;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.btn-secondary:hover {
  background: #447eff;
  color: white;
  transform: translateY(-2px);
}
```

### Accent Button Styles
```css
.btn-accent {
  background: linear-gradient(135deg, #ffc554 0%, #ffb020 100%);
  color: #000000;
  font-family: 'Poppins', sans-serif;
  font-weight: 900;
  font-size: 1rem;
  padding: 16px 32px;
  border-radius: 8px;
  border: none;
  cursor: pointer;
  transition: all 0.3s ease;
  text-transform: uppercase;
  letter-spacing: 0.5px;
  box-shadow: 0 4px 14px rgba(255, 197, 84, 0.3);
}
```

## Layout and Spacing System

### Container and Grid System
```css
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
}

.container-wide {
  max-width: 1400px;
  margin: 0 auto;
  padding: 0 20px;
}

/* Spacing Scale */
.spacing-xs { margin: 8px; }
.spacing-sm { margin: 16px; }
.spacing-md { margin: 24px; }
.spacing-lg { margin: 32px; }
.spacing-xl { margin: 48px; }
.spacing-2xl { margin: 64px; }
.spacing-3xl { margin: 96px; }
```

### Section Spacing
```css
.section {
  padding: 80px 0;
}

.section-sm {
  padding: 60px 0;
}

.section-lg {
  padding: 120px 0;
}
```

## Component Design Specifications

### Hero Section Design
```css
.hero {
  background: linear-gradient(135deg, #447eff 0%, #4169e1 100%);
  min-height: 600px;
  display: flex;
  align-items: center;
  color: white;
  position: relative;
  overflow: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: url('/assets/hero-pattern.svg') no-repeat center;
  background-size: cover;
  opacity: 0.1;
}

.hero-content {
  position: relative;
  z-index: 2;
}
```

### Service Cards Design
```css
.service-card {
  background: white;
  border-radius: 12px;
  padding: 32px;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  border: 1px solid #e2e8f0;
}

.service-card:hover {
  transform: translateY(-8px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.1);
  border-color: #447eff;
}

.service-icon {
  width: 64px;
  height: 64px;
  background: linear-gradient(135deg, #447eff 0%, #4169e1 100%);
  border-radius: 12px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 24px;
}
```

### Form Design
```css
.form-group {
  margin-bottom: 24px;
}

.form-label {
  font-family: 'Poppins', sans-serif;
  font-weight: 900;
  font-size: 0.875rem;
  color: #333333;
  margin-bottom: 8px;
  display: block;
  text-transform: uppercase;
  letter-spacing: 0.5px;
}

.form-input {
  width: 100%;
  padding: 16px;
  border: 2px solid #e2e8f0;
  border-radius: 8px;
  font-family: 'Roboto', sans-serif;
  font-size: 1rem;
  transition: border-color 0.3s ease;
}

.form-input:focus {
  outline: none;
  border-color: #447eff;
  box-shadow: 0 0 0 3px rgba(68, 126, 255, 0.1);
}
```

## Navigation Design

### Header Navigation
```css
.header {
  background: white;
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.05);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
}

.nav-menu {
  display: flex;
  align-items: center;
  gap: 32px;
}

.nav-link {
  font-family: 'Roboto', sans-serif;
  font-weight: 500;
  font-size: 1rem;
  color: #333333;
  text-decoration: none;
  padding: 8px 16px;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.nav-link:hover,
.nav-link.active {
  color: #447eff;
  background: rgba(68, 126, 255, 0.1);
}
```

## Responsive Design Specifications

### Mobile-First Approach
```css
/* Mobile (320px+) */
.hero h1 { font-size: 2.5rem; }
.container { padding: 0 16px; }
.section { padding: 60px 0; }

/* Tablet (768px+) */
@media (min-width: 768px) {
  .hero h1 { font-size: 3rem; }
  .container { padding: 0 24px; }
  .section { padding: 80px 0; }
}

/* Desktop (1024px+) */
@media (min-width: 1024px) {
  .hero h1 { font-size: 3.5rem; }
  .container { padding: 0 32px; }
  .section { padding: 100px 0; }
}

/* Large Desktop (1200px+) */
@media (min-width: 1200px) {
  .container { padding: 0 40px; }
  .section { padding: 120px 0; }
}
```

## Performance Optimization

### CSS Organization
```css
/* Critical CSS - Inline in <head> */
/* Above-the-fold styles, fonts, basic layout */

/* Non-critical CSS - External file */
/* Below-the-fold components, animations, advanced styling */
```

### Image Optimization
- WebP format with JPEG fallback
- Responsive images with srcset
- Lazy loading for below-the-fold images
- Optimized file sizes (<100KB for hero images)

## Accessibility Compliance

### Color Contrast Standards
- Primary text: 7:1 contrast ratio
- Secondary text: 4.5:1 contrast ratio
- Interactive elements: 3:1 contrast ratio

### Focus States
```css
.focusable:focus {
  outline: 2px solid #447eff;
  outline-offset: 2px;
}
```

### Screen Reader Support
- Semantic HTML structure
- Alt text for all images
- ARIA labels for interactive elements
- Skip navigation links

---

**Design System Status:** Complete and Brand Compliant  
**Implementation Ready:** Yes - All specifications provided  
**Quality Assurance:** Regular brand compliance verification required  
**Performance Target:** <3 seconds loading time, 95+ Lighthouse score