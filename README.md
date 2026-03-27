# Professional Portfolio & JobFair 2026

This repository contains Tom Kristian Abel's interactive portfolio and JobFair 2026 materials, featuring a modern single-page application CV and comprehensive company pitches.

## Project Structure

```
├── index.html              # Main CV SPA - Interactive company-focused CV
├── pitches.html            # Unified pitches page - All company pitches in one responsive view
├── pitches/                # Detailed pitch markdown files (reference)
│   ├── bolt.md
│   ├── helmes.md
│   └── ...
├── jobfair-research/       # Company research materials
├── JOBFAIR.md              # Event information and company details
├── PLAN.md                 # Project planning documentation
└── README.md              # This file
```

## Features

### CV Single-Page Application (index.html)
- **Interactive Company Selection**: Click any company to see a customized CV
- **Dynamic Content**: Skills, summaries, and hero titles adapt per company
- **Responsive Design**: Works on desktop, tablet, and mobile
- **Accessibility**: Full keyboard navigation and screen reader support
- **Error Handling**: Robust JavaScript with graceful fallbacks

### Pitches Page (pitches.html)
- **Unified View**: All 14 company pitches in a single responsive interface
- **Advanced Filtering**: Search, priority filtering, and company-specific views
- **Modern Design**: Consistent with CV styling and UX patterns
- **Mobile-First**: Optimized for mobile and touch interactions

## Technologies Used

- **HTML5**: Semantic structure with accessibility features
- **CSS3**: Modern design system with CSS custom properties
- **JavaScript**: Modular, error-resistant vanilla JavaScript
- **Responsive Design**: Mobile-first responsive layouts
- **Performance**: Optimized loading and animations

## Browser Support

- Chrome 80+
- Firefox 75+
- Safari 13+
- Edge 80+

## Development Notes

### Design System
The project uses a unified design system:
- **Colors**: Consistent accent color (#00e5a0) with accessibility considerations
- **Typography**: DM Sans for body, JetBrains Mono for code elements
- **Components**: Reusable card layouts and navigation patterns
- **Responsive**: Breakpoint-based responsive behavior

### JavaScript Architecture
- **Error Handling**: Comprehensive validation and graceful fallbacks
- **State Management**: Centralized state with clear data flow
- **Event Handling**: Proper event delegation and cleanup
- **Performance**: Debounced search and optimized animations

### Accessibility Features
- **Keyboard Navigation**: Full tab navigation and keyboard shortcuts
- **Screen Readers**: ARIA labels and semantic HTML
- **Color Contrast**: WCAG 2.1 AA compliant
- **Reduced Motion**: Respects user motion preferences

## Usage

### CV SPA
1. Open `index.html` in a browser
2. Click any company card to view the customized CV
3. Use browser navigation (back/forward) or the "Back to Companies" button
4. Share specific company views using the URL hash (e.g., `#bolt`)

### Pitches Page
1. Open `pitches.html` in a browser
2. Use the search box to filter pitches
3. Click navigation buttons to filter by priority or company
4. All content is responsive and accessible

## File Organization

- `index.html` - Primary CV application
- `pitches.html` - Main pitches interface  
- `pitches/*.md` - Detailed pitch content (reference/backup)
- Research and planning files are kept for documentation

## Deployment

The main branch is production-ready and can be deployed directly. No build process required.

The project follows semantic HTML standards and uses relative paths for maximum portability.