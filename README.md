# Integrated ICT - AI Opportunity Report

Static HTML report showcasing an AI Opportunity Assessment for Integrated ICT. Single-page application using vanilla JavaScript, Chart.js for data visualization, and Tailwind CSS via CDN.

## Quick Start

No build process required. Simply serve the static files:

```bash
# Python
python -m http.server 8000

# Node.js
npx serve

# VS Code Live Server extension
```

Then open `http://localhost:8000` in your browser.

## Project Structure

```
integratedict/
├── index.html           # Main application (all-in-one file)
├── assets/
│   ├── images/         # Logo, profile images
│   ├── audio/          # Audio overview
│   ├── video/          # Video walkthrough
│   ├── report.pdf      # Downloadable PDF report
│   └── iict.zip        # Full asset package
└── .autopilot.json     # Deployment notification config
```

## Architecture

**Single-file application**: `index.html` contains all HTML, CSS, and JavaScript inline

**Dependencies** (loaded via CDN):
- Tailwind CSS
- Chart.js
- Google Fonts (Inter)

**Key Features**:
- 📊 Radar chart for dimensional score comparison
- 🍩 Doughnut chart for overall AI readiness score
- 📑 Tab-based dimensional deep dive
- 💬 Floating chatbot assistant (bottom-left)

## Color Palette

- Primary: `#28AEA7` (teal)
- Secondary: `#E09453` (orange)
- Accent: `#0A4090` (blue)
- Neutral Light: `#f5efe1`
- Neutral Dark: `#343434`

## Data Structure

All audit data embedded as JavaScript objects:
- `auditData`: Five dimensional scores (CX, Ops, Content, Data, Tech)
- `qnaData`: Q&A pairs for chatbot responses
- `colorPalette`: Design system tokens

## Customization

To update scores or content, edit the embedded JavaScript objects in `index.html`:

```javascript
const auditData = {
    cx: { title: "Customer Experience", score: 85, ... },
    // ... modify scores and evidence here
};
```

## License

Proprietary - Good AI Australia
