# Complete Brand Guidelines - Knowledge Center Enhanced

**Document:** BY MB Consultancy Brand Guidelines  
**Version:** 2.0 (Knowledge Center Integration)  
**Date:** June 21, 2025  
**Purpose:** Complete brand implementation for www.by-mb.com

---

## ? Brand Identity Overview

### Company Information
- **Company Name:** BY MB Consultancy
- **Founded:** March 2023  
- **Location:** Manama, Bahrain
- **Tagline:** "Success is a Journey, Not a Destination"
- **Industry:** Technology Consultancy & Smart Solutions

### Mission Statement
**"To drive innovation by delivering smart, efficient, and secure solutions for homes and businesses across Bahrain."**

### Vision Statement  
**"To create a world where technology seamlessly integrates into everyday life, empowering individuals and businesses to achieve more with less effort, while prioritizing sustainability and quality."**

---

## ? Brand Positioning

### Core Values
- **Innovation:** Cutting-edge technology solutions
- **Customer-Centric Approach:** Tailored to client needs  
- **Sustainability:** Long-term, environmentally conscious solutions
- **Excellence:** 23+ years of cross-industry expertise
- **Reliability:** 99.5% system uptime guarantee

### Brand Personality
- **Efficient:** Straight to the point, no unnecessary complexity
- **Personable:** Friendly approach, not overly formal
- **Tech-savvy:** Simplifying complex technological concepts
- **Professional:** Enterprise-grade solutions with personal touch
- **Trustworthy:** Proven track record with measurable results

---

## ? Visual Identity System

### Logo Implementation
**Primary Logo:** "BY MB" with tagline integration
- **Usage:** Headers, business cards, official documents
- **Minimum Size:** 120px width for digital, 20mm for print
- **Clear Space:** Minimum 1x logo height on all sides
- **File Formats:** SVG (web), PNG (digital), EPS (print)

### Color Palette

#### Primary Colors
```css
:root {
  /* Primary Brand Color */
  --azure-radiance: #447eff;
  --primary-blue: #447eff;
  
  /* RGB Values */
  --azure-rgb: 68, 126, 255;
  
  /* HSL Values */  
  --azure-hsl: 221, 100%, 63%;
  
  /* CMYK Values */
  --azure-cmyk: 73, 0, 51, 0;
}
```

#### Secondary Colors
```css
:root {
  /* Accent Colors */
  --accent-gold: #ffc554;
  --white: #ffffff;
  --black: #000000;
  
  /* Text Colors */
  --text-primary: #333333;
  --text-secondary: #666666;
  --text-light: #999999;
  
  /* Background Colors */
  --bg-light: #f8f9fa;
  --bg-gray: #e9ecef;
  --border-gray: #dee2e6;
}
```

#### Color Usage Guidelines
- **Azure Radiance (#447eff):** Headers, buttons, links, brand elements
- **Gold (#ffc554):** Call-to-action buttons, highlights, success indicators
- **White (#ffffff):** Clean backgrounds, contrast elements
- **Black (#000000):** Primary text, high contrast needs
- **Gray Tones:** Secondary text, borders, subtle backgrounds

### Typography System

#### Primary Font: Poppins Black
```css
.brand-heading {
  font-family: 'Poppins', sans-serif;
  font-weight: 900; /* Black */
  line-height: 1.2;
}
```
**Usage:** Main headlines, logo, brand elements, section headers
**Character Set:** Full Latin extended, supports Bahrain Arabic transliteration

#### Secondary Font: Roboto  
```css
.brand-body {
  font-family: 'Roboto', sans-serif;
  font-weight: 400; /* Regular */
  line-height: 1.6;
}
```
**Usage:** Body text, descriptions, navigation, forms
**Weights Available:** 300 (Light), 400 (Regular), 500 (Medium), 700 (Bold)

#### Typography Hierarchy
```css
/* Headings */
h1 { font: 900 2.5rem/1.2 'Poppins', sans-serif; color: var(--azure-radiance); }
h2 { font: 900 2rem/1.2 'Poppins', sans-serif; color: var(--text-primary); }  
h3 { font: 900 1.5rem/1.2 'Poppins', sans-serif; color: var(--text-primary); }
h4 { font: 700 1.25rem/1.3 'Roboto', sans-serif; color: var(--text-primary); }

/* Body Text */
.body-large { font: 400 1.125rem/1.6 'Roboto', sans-serif; }
.body-regular { font: 400 1rem/1.6 'Roboto', sans-serif; }
.body-small { font: 400 0.875rem/1.5 'Roboto', sans-serif; }

/* Special Text */
.tagline { font: 500 1.1rem/1.4 'Roboto', sans-serif; color: var(--text-secondary); }
.button-text { font: 700 1rem/1 'Poppins', sans-serif; }
```

---

## ? Website Design Implementation

### Header & Navigation
```css
.header {
  background: var(--white);
  border-bottom: 1px solid var(--border-gray);
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.logo {
  font: 900 1.8rem/1 'Poppins', sans-serif;
  color: var(--azure-radiance);
}

.nav-link {
  font: 500 1rem/1 'Roboto', sans-serif;
  color: var(--text-primary);
  transition: color 0.3s ease;
}

.nav-link:hover {
  color: var(--azure-radiance);
}
```

### Button System
```css
/* Primary CTA Button */
.btn-primary {
  background: var(--azure-radiance);
  color: var(--white);
  font: 700 1rem/1 'Poppins', sans-serif;
  padding: 1rem 2rem;
  border-radius: 6px;
  border: none;
  transition: all 0.3s ease;
}

.btn-primary:hover {
  background: #3366e6;
  transform: translateY(-2px);
}

/* Secondary CTA Button */
.btn-secondary {
  background: transparent;
  color: var(--azure-radiance);
  border: 2px solid var(--azure-radiance);
  font: 700 1rem/1 'Poppins', sans-serif;
  padding: 1rem 2rem;
  border-radius: 6px;
  transition: all 0.3s ease;
}

.btn-secondary:hover {
  background: var(--azure-radiance);
  color: var(--white);
}

/* Accent Button (Gold) */
.btn-accent {
  background: var(--accent-gold);
  color: var(--black);
  font: 700 1rem/1 'Poppins', sans-serif;
  padding: 1rem 2rem;
  border-radius: 6px;
  border: none;
  transition: all 0.3s ease;
}

.btn-accent:hover {
  background: #e6b04a;
  transform: translateY(-2px);
}
```

### Content Sections
```css
.hero-section {
  background: linear-gradient(135deg, var(--azure-radiance), #3366e6);
  color: var(--white);
  padding: 120px 0 80px;
}

.service-card {
  background: var(--white);
  border: 1px solid var(--border-gray);
  border-radius: 8px;
  padding: 2rem;
  transition: all 0.3s ease;
}

.service-card:hover {
  border-color: var(--azure-radiance);
  transform: translateY(-4px);
  box-shadow: 0 8px 25px rgba(68, 126, 255, 0.15);
}

.section-title {
  font: 900 2rem/1.2 'Poppins', sans-serif;
  color: var(--text-primary);
  text-align: center;
  margin-bottom: 3rem;
}
```

---

## ? Brand Voice & Messaging

### Tone Characteristics

#### Efficient Communication
- **Do:** Get straight to the point with clear, actionable language
- **Example:** "Transform your space with smart technology solutions"
- **Avoid:** Verbose explanations or unnecessary technical jargon

#### Personable Approach  
- **Do:** Use friendly, approachable language while maintaining professionalism
- **Example:** "We'll work with you to design the perfect solution"
- **Avoid:** Overly formal corporate speak or cold technical language

#### Tech-Savvy Simplification
- **Do:** Explain complex concepts in accessible terms
- **Example:** "Home Assistant automates your daily routines"
- **Avoid:** Assuming all readers understand technical terminology

### Key Messaging Framework

#### Core Value Propositions
1. **23+ Years Experience** - "Cross-industry expertise you can trust"
2. **Systematic Excellence** - "Professional methodology with proven results"  
3. **Local Expertise** - "Deep understanding of Bahrain's technology needs"
4. **Comprehensive Solutions** - "End-to-end technology transformation"

#### Service Messaging
- **Smart Solutions:** "Intelligent automation for modern living"
- **Analytics:** "Transform data into strategic insights"  
- **Digital Transformation:** "Streamline operations with enterprise technology"
- **Networking:** "Reliable connectivity for business success"

#### Call-to-Action Language
- Primary: "Schedule Free Consultation"
- Secondary: "Explore Our Solutions"
- Emergency: "Call Now for Immediate Support"
- Information: "Learn More About Our Services"

---

## ? Brand Application Guidelines

### Contact Information Display
```
BY MB Consultancy
Manama, Bahrain

Phone: +973-66300033
Email: info@by-mb.com
Website: www.by-mb.com

Hours: Sunday-Thursday, 9am-6pm
```

### Social Media Integration
- **LinkedIn:** Professional content, thought leadership
- **Facebook:** Community engagement, project showcases  
- **Instagram:** Visual content, behind-the-scenes

### Professional Photography
- **Style:** Clean, modern, technology-focused
- **Color Treatment:** Subtle Azure Radiance overlays where appropriate
- **Subjects:** Modern buildings, technology equipment, professional environments
- **Avoid:** Stock photography that appears generic or outdated

---

## ? Odoo Website Implementation

### Theme Configuration
```
Primary Color: #447eff (Azure Radiance)
Secondary Color: #ffc554 (Accent Gold)
Success Color: #28a745
Warning Color: #ffc107
Danger Color: #dc3545
```

### Font Integration
```
Primary Font: Poppins (Google Fonts)
- Import URL: https://fonts.googleapis.com/css2?family=Poppins:wght@400;700;900&display=swap
- Usage: All headings, buttons, brand elements

Secondary Font: Roboto (Google Fonts) 
- Import URL: https://fonts.googleapis.com/css2?family=Roboto:wght@300;400;500;700&display=swap
- Usage: Body text, navigation, forms
```

### Custom CSS Variables
```css
:root {
  --odoo-brand-primary: #447eff;
  --odoo-brand-secondary: #ffc554;
  --odoo-text-primary: #333333;
  --odoo-text-secondary: #666666;
  --odoo-bg-light: #f8f9fa;
  --odoo-border: #dee2e6;
}
```

---

## ? Brand Compliance Checklist

### Visual Elements
- [ ] Azure Radiance (#447eff) used consistently for primary brand elements
- [ ] Gold (#ffc554) used for call-to-action and accent elements
- [ ] Poppins Black used for all headings and brand elements
- [ ] Roboto used for all body text and secondary content
- [ ] Proper logo placement with adequate clear space

### Content & Messaging
- [ ] "Success is a Journey, Not a Destination" tagline included
- [ ] Brand voice (Efficient, Personable, Tech-savvy) maintained
- [ ] Mission and vision statements properly integrated
- [ ] 23+ years experience prominently featured
- [ ] All contact information accurate and current

### Technical Implementation
- [ ] Mobile-responsive design with brand consistency
- [ ] Proper font loading and fallbacks
- [ ] Color contrast ratios meet accessibility standards
- [ ] Brand colors consistent across all page elements
- [ ] Professional photography aligns with brand aesthetic

---

## ? Brand Contact Standards

### Professional Contact Presentation
**Phone:** +973-66300033 (Always include country code)
**Email:** info@by-mb.com (Professional domain consistency)
**Location:** Manama, Bahrain (Clear geographic identifier)
**Hours:** Sunday-Thursday, 9am-6pm (Local business hours)

### Emergency Contact Branding
**24/7 Emergency Support:** +973-66300033 (Press 0)
**Email:** emergency@by-mb.com
**Response Time:** Within 2 hours for enterprise customers

---

**Status:** ? Ready for Implementation  
**Next Step:** Apply guidelines to www.by-mb.com  
**Contact:** info@by-mb.com for brand approval

*Complete brand guidelines enhanced with Knowledge Center integration for professional implementation across all digital touchpoints.*