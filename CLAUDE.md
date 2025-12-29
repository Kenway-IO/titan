# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **TITAN Framework** - a single-page React application for presenting an enterprise integration methodology. TITAN stands for **Trigger, Ingest, Think, Act, Notify** - a framework for designing event-driven integration architectures in enterprise environments (Dynamics 365, SAP, Salesforce, Azure).

The application is a standalone HTML file with embedded React, serving as a pre-sales and client education tool for Kenway Consulting's integration practice.

## Development Commands

This project has no build system or package manager. It runs entirely in-browser.

- **Run locally**: Open `index.html` directly in a web browser (no server required)
- **Edit**: Modify `index.html` directly - all React code is in `<script type="text/babel">` tags
- **No build, test, or lint commands** - this is a single-file vanilla React app

## Architecture

### Single-File React Application

- **Technology Stack**: React 18 (UMD), Tailwind CSS (CDN), Babel Standalone (in-browser JSX compilation)
- **No bundler**: All dependencies loaded via CDN (unpkg.com)
- **All code in one file**: `index.html` contains HTML, CSS, JavaScript, and React components

### Data Sources

The application loads two JSON data files:

1. **`assets/inventory.json`**: The "Discovery Inventory" table - contains 13 pre-configured TITAN workflow examples
   - Each entry represents a business process automation opportunity
   - Structured as: `{ "id": { title, impact, description, steps[], techStack[], successCriteria } }`
   - Falls back to `MOCK_INVENTORY` constant if file not found

2. **`assets/methodology.json`** (optional): Deep-dive content for each TITAN letter (T, I, T2, A, N)
   - Falls back to `MOCK_METHODOLOGY_DETAILS` constant if file not found

### React Component Structure

The app uses a single-file component hierarchy (no separate files):

```
App (root)
├── Sidebar - Navigation with scroll spy
├── DigitalPulse - Animated EKG visualization
├── TitanCard (5x) - Methodology cards for T-I-T-A-N
├── TitanLoopVisual - Interactive circular diagram
├── InventoryTable - Sortable/filterable data table
├── ROICalc - Interactive calculator
├── MethodologyModal - Deep dive on TITAN letters
└── ArchitectureModal - Flow visualization for inventory items
```

### Key Patterns

1. **Mock Data Fallbacks**: Both external JSON files have embedded mock data constants for offline/preview use
2. **URL-based Deep Linking**: `?flow=returns` opens the architecture modal for that inventory item
3. **Scroll Spy**: IntersectionObserver auto-highlights active section in sidebar
4. **Inline SVG Icons**: All icons are inline functional components (no icon library)
5. **Tailwind Configuration**: Custom color palette defined in `tailwind.config` script block
   - `kenway-navy`: #0f2c52
   - `kenway-blue`: #007cc0
   - `kenway-red`: #D32F2F

## Claude Code Skills

This repository includes a custom skill to streamline adding new TITAN use-cases.

### `/add-titan-usecase` Skill

**Usage**: Run `/add-titan-usecase` to launch an interactive wizard that guides you through adding a new workflow to the inventory.

The skill will prompt you for:
1. Basic info (ID, title, impact, description)
2. Each TITAN stage (Trigger → Ingest → Think → Act → Notify)
   - Event/action label
   - System involved
3. Tech stack (3-5 technologies)
4. Success criteria

The skill automatically applies the correct icons and color scheme, then adds the entry to `assets/inventory.json`.

**Location**: `.claude/skills/add-titan-usecase.md`

## Content Editing Guidance

### Adding New Inventory Items

To add a new workflow example to the Discovery Inventory table:

**Option 1: Use the skill** (recommended)
- Run `/add-titan-usecase` and follow the interactive prompts

**Option 2: Manual editing**
1. Edit `assets/inventory.json`
2. Add a new key with this structure:
```json
"uniqueId": {
  "title": "Process Name",
  "impact": "$XXXk/yr",
  "description": "Brief description",
  "steps": [
    { "id": 1, "stage": "TRIGGER", "label": "Event Name", "system": "Source System", "icon": "Zap", "color": "bg-kenway-navy" },
    { "id": 2, "stage": "INGEST", "label": "Action", "system": "System", "icon": "Database", "color": "bg-kenway-blue" },
    { "id": 3, "stage": "THINK", "label": "Decision", "system": "AI/Logic", "icon": "BrainCircuit", "color": "bg-purple-600", "highlight": true },
    { "id": 4, "stage": "ACT", "label": "Execution", "system": "Target System", "icon": "Activity", "color": "bg-orange-500" },
    { "id": 5, "stage": "NOTIFY", "label": "Notification", "system": "Channel", "icon": "CheckCircle", "color": "bg-green-600" }
  ],
  "techStack": ["Tool 1", "Tool 2", "Tool 3"],
  "successCriteria": "Detailed acceptance criteria"
}
```

3. **Icon Names**: Must match keys in `IconMap` object (line 242): Zap, Database, BrainCircuit, Activity, CheckCircle, Cloud, FileText, Server

### Color System

TITAN stages have standardized colors:
- **Trigger**: `bg-kenway-navy` (dark blue)
- **Ingest**: `bg-kenway-blue` (bright blue)
- **Think**: `bg-purple-600` (purple) - always gets `highlight: true`
- **Act**: `bg-orange-500` (orange)
- **Notify**: `bg-green-600` (green)

### Prompts for AI-Generated Content

The `docs/` folder contains prompt templates used to generate architecture proposals and ROI analyses:
- `architecture_prompt.md`: Template for creating detailed solution architectures
- `roi_prompt.md`: Template for analyzing TITAN opportunities and creating scorecards

These are reference materials, not executable code.

## Important Constraints

1. **No TypeScript**: This is vanilla JavaScript with JSX
2. **No Node.js**: Cannot run `npm install` or build commands
3. **Image Assets**: Logo images in `assets/` and `assets/titanLetters/` have fallback behavior if missing
4. **Browser Compatibility**: Requires modern browser with ES6+ support (uses hooks, arrow functions, etc.)
5. **Kenway Branding**: Color palette and terminology are specific to Kenway Consulting's brand guidelines
