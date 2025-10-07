# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Static HTML report showcasing an AI Opportunity Assessment for Integrated ICT. Single-page application using vanilla JavaScript, Chart.js for data visualization, and Tailwind CSS via CDN.

## Architecture

**Single-file application**: `index.html` contains all HTML, CSS, and JavaScript inline
- **No build process**: Runs directly in browser via CDN dependencies
- **Core dependencies**: 
  - Tailwind CSS (CDN)
  - Chart.js (visualization library)
  - Google Fonts (Inter)

**Data structure**: All audit data embedded as JavaScript objects in `<script>` section
- `auditData`: Five dimensional scores (Customer Experience, Operational Processes, Content Management, Data Utilization, Technical Readiness)
- `qnaData`: Q&A pairs for chatbot responses
- `colorPalette`: Design system tokens

**Key features**:
- Radar chart for dimensional comparison (Chart.js)
- Doughnut chart for overall score (Chart.js)
- Tab-based content switching (vanilla JS)
- Floating chatbot UI (bottom-left positioned)

## Development

**Local server**: Use any static file server
```bash
# Python
python -m http.server 8000

# Node.js
npx serve

# VS Code Live Server extension
```

**Asset structure**:
- `/assets/images/` - Logo, profile images
- `/assets/audio/` - Audio overview file
- `/assets/video/` - Video walkthrough
- `/assets/report.pdf` - Downloadable PDF report
- `/assets/iict.zip` - Full asset package

## Configuration

**Autopilot notifications**: `.autopilot.json` configures Telegram/Email/Feishu adapters for deployment notifications

**Cursor rules**: `.cursor/rules/after_each_chat.mdc` enforces chat-end JSON summaries to `./tmp/` directory

## Color Palette

- Primary: `#28AEA7` (teal)
- Secondary: `#E09453` (orange)
- Accent: `#0A4090` (blue)
- Neutral Light: `#f5efe1`
- Neutral Dark: `#343434`

## Chatbot Logic

Pattern-matching chatbot searches `qnaData` array for query matches. Falls back to contact suggestion if no match found. Responses support basic markdown (`**bold**`).

## Key Implementation Notes

- All charts use `maintainAspectRatio: false` with explicit container heights
- Tab content rendered dynamically via `renderTabContent()` function
- No SVG or Mermaid.js used (per design constraints)
- Chatbot anchored bottom-left (not right) per design spec
