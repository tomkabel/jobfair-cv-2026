# Plan: JobFair 2026 Custom CV SPA
## Version 2.0 — Corrected for Actual Project State

---

## Overview

Create a single-page application (SPA) that serves as an interactive CV/portfolio for Tom Kristian Abel, tailored to each of the 14 companies attending kood/JobFair 2026. The SPA features a company selector landing page and dynamically themed CV views per company. Alongside, generate a pet project showcase section.

**Current State (as of March 2026):**
- ✅ All 14 pitch files exist in `pitches/`
- ✅ Research files exist in `jobfair-research/`
- ✅ Existing CV files (txt, pdf, LinkedIn export)
- ❌ index.html is currently a static CV (not SPA)
- ❌ No company selector landing page
- ❌ No dynamic per-company theming
- ❌ No pet project section

---

## Step 1: Create the `companies` JavaScript Data Structure

**File:** `index.html` (inline JavaScript)

Create a JavaScript object containing all 14 companies with their branding, customizations, and pitch angles:

```javascript
const companies = {
  bolt: {
    name: "Bolt",
    tagline: "Europe's mobility super-app",
    accent: "#34D186",
    summary: "With 200M+ customers across 50+ countries, Bolt faces a massive attack surface spanning ride-hailing, e-scooter IoT, food delivery, and autonomous vehicles. My offensive security background and CTO experience make me uniquely suited to help secure Bolt's expanding ecosystem.",
    skillPriority: ["DevOps", "Golang", "IoT Security", "Concurrent Systems"],
    pitchAngle: "security + scale + IoT"
  },
  delfi-meedia: {
    name: "Delfi Meedia",
    tagline: "Leading digital media in the Baltics",
    accent: "#E30613",
    summary: "As a leader in digital media serving millions of readers, Delfi Meedia faces unique challenges around content protection, bot traffic, and ad fraud. My experience bypassing complex detection systems gives me insight into both attack and defense strategies.",
    skillPriority: ["Performance Tuning", "JavaScript", "Bot Detection Bypass"],
    pitchAngle: "content protection + traffic analysis"
  },
  swedbank: {
    name: "Swedbank",
    tagline: "One of Europe's largest banks",
    accent: "#FF6B00",
    summary: "Banking security is where theory meets consequence. With 7.7M customers and one of Europe's largest SIEM platforms, Swedbank demands security leaders who understand both compliance and operational reality. I bring the offensive mindset needed to find vulnerabilities before attackers do.",
    skillPriority: ["Security Architecture", "DevSecOps", "API Security"],
    pitchAngle: "banking security + compliance"
  },
  pactum-ai: {
    name: "Pactum AI",
    tagline: "AI-powered negotiation platform",
    accent: "#6C5CE7",
    summary: "AI introduces new attack surfaces that traditional security teams struggle to address. My background in adversarial robustness and understanding of AI model vulnerabilities positions me to help Pactum build security into their AI-powered negotiation engine from the ground up.",
    skillPriority: ["AI Security", "Python", "API Security"],
    pitchAngle: "AI safety + adversarial robustness"
  },
  helmes: {
    name: "Helmes",
    tagline: "Enterprise software since 1991",
    accent: "#0066CC",
    summary: "With 30 years of building software that matters, Helmes has security embedded in every project team — not bolted on. My offensive security consulting experience through ProksiAbel aligns perfectly with Helmes' security-first approach to enterprise software.",
    skillPriority: ["Security Architecture", "Penetration Testing", "ISO 27001"],
    pitchAngle: "consulting security + regulated environments"
  },
  genius-sports: {
    name: "Genius Sports",
    tagline: "Data-driven sports technology",
    accent: "#00D4AA",
    summary: "In the high-stakes world of sports betting and live data, data integrity isn't just important — it's everything. My experience with database optimization and performance tuning at scale, combined with security research, helps protect the data that drives billion-dollar decisions.",
    skillPriority: ["Database Optimization", "Performance Tuning", "Data Security"],
    pitchAngle: "sports data integrity + real-time systems"
  },
  remitk: {
    name: "REMITK",
    tagline: "Estonian real estate platform",
    accent: "#005AA0",
    summary: "As Estonia's leading real estate platform, REMITK handles sensitive property data and financial transactions. I bring the security expertise needed to protect user trust while maintaining the seamless experience that drives real estate success.",
    skillPriority: ["Full-Stack", "Security", "Database Optimization"],
    pitchAngle: "platform security + user trust"
  },
  ericsson: {
    name: "Ericsson",
    tagline: "5G and IoT infrastructure",
    accent: "#00830D",
    summary: "Ericsson powers the telecommunications infrastructure that connects billions of devices. With 5G and IoT expanding the attack surface exponentially, my IoT security expertise and understanding of telecom protocols can help secure the networks of tomorrow.",
    skillPriority: ["IoT Security", "Telecom Protocols", "Network Security"],
    pitchAngle: "5G infrastructure security + scale"
  },
  smit: {
    name: "SMIT",
    tagline: "Software innovation and consulting",
    accent: "#1A237E",
    summary: "SMIT's focus on innovation requires security research that pushes boundaries. My track record in vulnerability research, reverse engineering, and offensive security consulting directly supports SMIT's mission to deliver cutting-edge solutions.",
    skillPriority: ["Security Research", "Reverse Engineering", "Vulnerability Research"],
    pitchAngle: "offensive security + consulting"
  },
  seb: {
    name: "SEB",
    tagline: "Nordic banking group",
    accent: "#107772",
    summary: "As part of the Nordic banking group, SEB operates in one of the world's most sophisticated financial markets. My security architecture background and understanding of fintech regulations position me to contribute to SEB's security excellence.",
    skillPriority: ["Financial Security", "DevSecOps", "Compliance"],
    pitchAngle: "Nordic banking security + fintech"
  },
  finest: {
    name: "Finest",
    tagline: "Fintech and payment solutions",
    accent: "#2D8C3C",
    summary: "Finest operates at the intersection of finance and technology, where payment security is paramount. My experience building secure APIs and understanding of financial attack vectors makes me a strong fit for your security team.",
    skillPriority: ["Payment Security", "API Security", "Golang"],
    pitchAngle: "payment systems + transaction security"
  },
  ida-hub: {
    name: "IDA Hub",
    tagline: "Innovation platform for developers",
    accent: "#8B5CF6",
    summary: "IDA Hub empowers developers to build the future. My background in security tooling and developer-focused engineering aligns with your mission to provide a secure, productive platform for the developer community.",
    skillPriority: ["Developer Tools", "Security", "DevOps"],
    pitchAngle: "developer ecosystem + security tooling"
  },
  vkg: {
    name: "VKG",
    tagline: "Estonian oil shale energy",
    accent: "#D32F2F",
    summary: "Operating critical industrial infrastructure requires security that understands operational technology. My experience with infrastructure security and understanding of industrial systems positions me to help VKG protect their operations.",
    skillPriority: ["OT Security", "Industrial Systems", "Infrastructure"],
    pitchAngle: "operational technology + industrial security"
  }
};
```

**Purpose:** This object drives all dynamic theming and content personalization in the SPA.

**Note on Summary Fields:** Each company's `summary` field should be populated from the pitch files in `pitches/*.md`. Use the "WHY [COMPANY]" section as the primary source, and adapt it to fit the CV format (~2-3 sentences). This ensures consistency between the verbal pitch and the written CV.

---

## Step 2: Build the Landing View (Company Selector)

**File:** `index.html` (inline CSS + HTML)

Add a landing view section with:

- **Dark, premium grid layout** showing 14 company cards
- **Each card styled with company brand color:**
  - Colored border or gradient accent
  - Company name
  - Brief tagline (from `jobfair-research/*.md`)
- **Interactive behavior:**
  - Hover effects with glow effect in company's accent color
  - Click triggers transition to CV view with company's theme applied
- **Visual design:**
  - CSS grid (responsive: 2-4 columns)
  - Card dimensions: ~280px min-width
  - Subtle background pattern
  - Title: "Tom Kristian Abel — JobFair 2026"

**Company brand colors (approximated based on official brand guidelines):**

| Company | Accent Color |
|---------|--------------|
| Bolt | #34D186 |
| Delfi Meedia | #E30613 |
| Swedbank | #FF6B00 |
| Pactum AI | #6C5CE7 |
| Helmes | #0066CC |
| Genius Sports | #00D4AA |
| REMITK | #005AA0 |
| Ericsson | #00830D |
| SMIT | #1A237E |
| SEB | #107772 |
| Finest | #2D8C3C |
| kood/Jõhvi | #FF4500 |
| IDA Hub | #8B5CF6 |
| VKG | #D32F2F |

---

## Step 3: Build the CV View (Per-Company Themed)

**File:** `index.html` (inline CSS + HTML + JavaScript)

When a company is selected, render:

### 3.1 Header
- Name: "Tom Kristian Abel"
- Title: Adapt based on company (e.g., for Swedbank: "Security Engineer specialized in banking infrastructure")
- Contact info (email, LinkedIn, location)

### 3.2 About Section
- Tailored summary paragraph highlighting relevance to the selected company
- Use the `pitchAngle` from the `companies` object to frame appropriately

### 3.3 Experience Section
- Same work history (keep chronological order)
- Reorder or emphasize bullet points based on company relevance

### 3.4 Skills Section
- Skill cards reordered based on `skillPriority` array for each company
- Most relevant skills appear first

### 3.5 Pet Project Section — Vooglaadija (YouTube Link Processor)

**Title:** "Pet Project: YouTube Link Processor"

**Description:** Production-grade REST API for YouTube media extraction. FastAPI async backend, Redis job queue, PostgreSQL, Docker multi-stage builds, JWT auth.

**Tech Stack Badges:**
- Python
- FastAPI
- PostgreSQL
- Redis
- Docker
- JWT
- yt-dlp
- GitHub Actions

**Architecture Diagram (ASCII):**
```
┌─────────┐     ┌──────────┐     ┌─────────┐     ┌───────────┐
│  Client │────▶│  FastAPI │────▶│  Redis  │────▶│  Worker   │
└─────────┘     │   API    │     │  Queue  │     │  (yt-dlp) │
                └──────────┘     └─────────┘     └───────────┘
                     │                                    │
                     ▼                                    ▼
                ┌──────────┐                        ┌───────────┐
                │PostgreSQL│                        │  Storage  │
                │   (DB)   │                        │  (Media)  │
                └──────────┘                        └───────────┘
```

**GitHub Link:** https://github.com/tomkabel/team21-vooglaadija

**Framing per company:**
- Bolt: Emphasize high-throughput, containerized, scalable architecture
- Swedbank: Emphasize secure JWT auth, async processing, production-grade
- Helmes: Emphasize full-stack engineering, client-server architecture
- Pactum AI: Emphasize async processing, API design
- Ericsson: Emphasize IoT-like device handling, protocol parsing

### 3.6 Education & Languages
- Same across all companies (no customization needed)

### 3.7 Back Button
- Returns to company selector landing page
- Resets theme to neutral

---

## Step 4: Implement Theme System

**File:** `index.html` (inline CSS + JavaScript)

**CSS Variables:**
```css
:root {
  --accent: #00e5a0;           /* Changes per company */
  --accent-dim: #00e5a015;    /* 15% opacity accent */
  --accent-glow: #00e5a030;   /* 30% opacity accent */
}
```

**JavaScript Theme Application:**
```javascript
function setCompanyTheme(companyKey) {
  const company = companies[companyKey];
  document.documentElement.style.setProperty('--accent', company.accent);
  // Calculate dim/glow variants based on accent color
  // Apply theme throughout the CV view
}
```

**Theme Flow:**
- Accent color applies to: borders, highlights, skill tags, section numbers, links, hover states
- Background remains dark for consistency
- Transition: smooth 0.3s color changes

---

## Step 5: Add JavaScript View Switching

**File:** `index.html` (inline JavaScript)

```javascript
// State
let currentView = 'landing'; // 'landing' or 'cv'
let selectedCompany = null;

// Functions
function showLandingView() {
  currentView = 'landing';
  // Hide CV section, show landing grid
}

function showCVView(companyKey) {
  selectedCompany = companyKey;
  currentView = 'cv';
  // Populate CV with company-specific data
  // Apply company theme
  // Hide landing, show CV
}

function goBack() {
  // Reset theme to default
  // Show landing view
}
```

**Navigation:**
- URL hash: `#bolt`, `#swedbank`, etc. (for direct linking)
- Browser back button support

---

## Step 6: Responsive Design & Print Support

**File:** `index.html` (inline CSS)

**Responsive Breakpoints:**
- Desktop: 3-4 column grid (>1024px)
- Tablet: 2 column grid (768px-1024px)
- Mobile: single column (<768px)

**Print Styles:**
- Convert to clean black/white layout
- Hide interactive elements (company grid, buttons)
- Show all company information
- Single page when possible

---

## File Structure

```
Curriculum-Vitae/
├── index.html                    # Main SPA (REPLACE existing static CV)
├── pitches/
│   ├── bolt.md                   # ✓ Already exists
│   ├── delfi-meedia.md           # ✓ Already exists
│   ├── swedbank.md               # ✓ Already exists
│   ├── pactum-ai.md              # ✓ Already exists
│   ├── helmes.md                 # ✓ Already exists
│   ├── genius-sports.md          # ✓ Already exists
│   ├── remitk.md                 # ✓ Already exists
│   ├── ericsson.md               # ✓ Already exists
│   ├── smit.md                   # ✓ Already exists
│   ├── seb.md                    # ✓ Already exists
│   ├── finest.md                 # ✓ Already exists
│   ├── kood.md                   # ✓ Already exists
│   ├── ida-hub.md                # ✓ Already exists
│   └── vkg.md                    # ✓ Already exists
├── jobfair-research/             # Existing research files (unchanged)
├── Tom-Kristian-Abel-CV.txt      # Existing (unchanged)
├── Tom-Kristian-Abel-CV.pdf      # Existing (unchanged)
├── LinkedIn-Export.pdf            # Existing (unchanged)
├── liftikõne.md                  # Existing (unchanged)
├── PLAN.md                       # Original plan (keep for reference)
└── PLAN_2.md                     # This plan (active)
```

---

## Execution Order

### Phase 1: Preparation (Completed)
- ✅ All 14 pitch files in `pitches/`
- ✅ Research files in `jobfair-research/`

### Phase 2: Build the SPA

**Action 1:** Create the `companies` JavaScript data structure with all 14 companies (Step 1)

**Action 2:** Build the landing view HTML/CSS with company grid (Step 2)

**Action 3:** Build the CV view with all sections (Step 3)

**Action 4:** Implement theme system with CSS variables (Step 4)

**Action 5:** Add JavaScript view switching functionality (Step 5)

**Action 6:** Add responsive design and print styles (Step 6)

**Action 7:** Populate summary fields — extract from pitch files in `pitches/*.md` (see "WHY [COMPANY]" sections)

### Phase 3: Validation

- [ ] Open `index.html` in browser
- [ ] Verify landing view shows all 14 companies
- [ ] Click each company card
- [ ] Verify theme changes (accent color)
- [ ] Verify content is personalized per company
- [ ] Verify pet project section appears
- [ ] Test back button navigation
- [ ] Test responsive layout on mobile
- [ ] Test print view

---

## Summary

This plan produces a single, polished interactive CV that can be shown on a laptop/tablet at the job fair, with company-specific pitches ready to deliver verbally at each booth.

**The 14 companies with existing research get deep customization:**
- Bolt, Delfi Meedia, Swedbank, Pactum AI, Helmes, Genius Sports, REMITK, Ericsson, SMIT, SEB, Finest, kood/Jõhvi, IDA Hub, VKG

**Each company receives:**
1. Branded card on landing page with correct accent color
2. Personalized summary paragraph
3. Reordered skills highlighting most relevant ones
4. Pet project framed to match company interests
5. Full SPA theming throughout

---

*plan_exit*
