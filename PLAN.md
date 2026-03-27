Plan: JobFair 2026 Custom CV SPA
Overview
Create a single-page application (SPA) that serves as an interactive CV/portfolio for Tom Kristian Abel, tailored to each of the 14 companies attending kood/JobFair 2026. The SPA features a company selector landing page and dynamically themed CV views per company. Alongside, generate a pet project showcase section.
---
Step 1: Build the Single-Page Application (index.html)
Architecture
- Single index.html file, fully self-contained (CSS + JS inline)
- Two views controlled by JS:
  1. Landing/Selector View — company grid with stylized branded buttons
  2. CV View — dynamically themed CV tailored to selected company
Landing View (Company Selector)
- Dark, premium grid layout showing 14 company cards
- Each card styled with the company's brand color as accent
- Card includes: company name, brief tagline (from research/JOBFAIR.md), colored border/gradient
- Clicking a card transitions to the CV view with that company's theme
Company brand colors (approximated):
Company	Accent Color
Bolt	#34D186 (green)
Delfi Meedia	#E30613 (red)
Swedbank	#FF6B00 (orange)
Pactum AI	#6C5CE7 (purple)
Helmes	#0066CC (blue)
Genius Sports	#00D4AA (teal)
REMITK	#005AA0 (state blue)
Ericsson	#00830D (Ericsson green)
SMIT	#1A237E (dark blue)
SEB	#107772 (SEB teal)
Finest	#2D8C3C (forest green)
//kood	#FF4500 (orange-red)
IDA Hub	#8B5CF6 (violet)
VKG	#D32F2F (industrial red)
CV View (Per Company)
When a company is selected, the view switches to show:
1. Header — Name, title, contact info (adapted subtitle emphasizing relevance to that company)
2. About — Tailored summary paragraph (reworded per company to highlight the most relevant angle)
3. Experience — Same work history but reordered/emphasized differently per company
4. Skills — Skill cards reordered to surface the most relevant ones first per company
5. Pet Project Section — "Vooglaadija" (YouTube Link Processor) showcase
   - Description of the project
   - Tech stack badges (Python, FastAPI, Docker, PostgreSQL, Redis)
   - Architecture diagram
   - GitHub link
   - Framed as evidence of full-stack engineering capability
6. Education & Languages — Same across all
7. Back button to return to company selector
Theme Adaptation
- CSS variables (--accent, --accent-dim, --accent-glow) update per company
- Accent colors flow through borders, highlights, skill tags, section numbers
- Background remains dark for consistency but accent elements change
Data Structure
A JS object containing per-company customizations:
const companies = {
  bolt: {
    name: "Bolt",
    tagline: "Europe's mobility super-app",
    accent: "#34D186",
    summary: "...", // tailored about text
    skillPriority: ["DevOps", "Golang", ...], // reordered skills
    pitchAngle: "security + scale"
  },
  // ... for all 14
}
---
Step 3: Pet Project Section in CV SPA
Add a dedicated showcase for the Vooglaadija (YouTube Link Processor) project inside each company's CV view:
- Title: "Pet Project: YouTube Link Processor"
- Description: Production-grade REST API for YouTube media extraction. FastAPI async backend, Redis job queue, PostgreSQL, Docker multi-stage builds, JWT auth.
- Tech badges: Python, FastAPI, PostgreSQL, Redis, Docker, JWT, yt-dlp, GitHub Actions
- Architecture diagram: Simple ASCII/SVG showing Client → FastAPI → Redis → Worker → Storage
- GitHub link: https://github.com/tomkabel/team21-vooglaadija
- Framing per company: The description subtly emphasizes what matters most to each company (e.g., for Swedbank: "secure JWT auth, async processing, production-grade"; for Bolt: "high-throughput, containerized, scalable architecture")
---
Step 5: File Structure
Curriculum-Vitae/
├── index.html                    # Main SPA (rewritten)
├── pitches/
│   ├── bolt.md
│   ├── delfi-meedia.md
│   ├── swedbank.md
│   ├── pactum-ai.md
│   ├── helmes.md
│   ├── genius-sports.md
│   ├── remitk.md
│   ├── ericsson.md
│   ├── smit.md
│   ├── seb.md
│   ├── finest.md
│   ├── kood.md
│   ├── ida-hub.md
│   └── vkg.md
├── jobfair-research/             # Existing research files (unchanged)
├── Tom-Kristian-Abel-CV.txt      # Existing (unchanged)
├── Tom-Kristian-Abel-CV.pdf      # Existing (unchanged)
├── LinkedIn-Export.pdf           # Existing (unchanged)
└── liftikõne.md                  # Existing (unchanged)
---
### Execution Order
1. Create `pitches/` directory and all 14 pitch `.md` files (using existing research for 7 companies, JOBFAIR.md context for remaining 7)
2. Build `index.html` SPA with:
   - Company selector landing page with branded cards
   - Per-company themed CV views with tailored content
   - Pet project showcase integrated into each CV view
   - Smooth transitions, responsive design, print support
3. Validate: open in browser, verify all 14 companies load, themes apply correctly, pitches read well
---
This plan produces a single, polished interactive CV that can be shown on a laptop/tablet at the job fair, with company-specific pitches ready to deliver verbally at each booth.
⚙ plan_exit 
The plan covers:
1. 14 company-specific pitches as markdown files in pitches/, each following the liftikõne framework (hook → who I am → why this company → what I bring → closing vision)
2. Single SPA (index.html) with:
   - Landing view: 14 stylized company cards with brand colors and taglines
   - CV view: Dynamically themed per company — adapted summary, reordered skills, company-relevant framing
   - Pet project section: Vooglaadija (YouTube Link Processor) integrated into each CV view, framed differently per company
   - Smooth transitions, responsive design, dark theme with per-company accent colors
3. File structure: index.html (SPA) + pitches/*.md (14 files) + existing research files unchanged
The 14 companies with existing research get deep customization;
