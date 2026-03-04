# Real-Time Analytics Dashboard

A production-quality analytics dashboard with animated Canvas charts, auto-updating KPIs, and smooth real-time data transitions. Built entirely from scratch with **zero dependencies**.

## Preview

![Dashboard](https://img.shields.io/badge/status-ready-brightgreen) ![Dependencies](https://img.shields.io/badge/dependencies-none-blue) ![License](https://img.shields.io/badge/license-MIT-green)

## Features

- 📊 **Animated Canvas Charts** — Line chart with gradient fill, bar chart with hover effects
- 📈 **Real-Time KPIs** — 4 auto-updating metric cards with sparklines
- 🍩 **Donut Chart** — Traffic source breakdown with animated segments
- 🔄 **Auto-Refresh** — Data updates every 3 seconds with smooth transitions
- 🌗 **Light/Dark Theme** — Toggle with localStorage persistence
- 📱 **Responsive** — Adapts from mobile to desktop
- ⚡ **Zero Dependencies** — Pure HTML, CSS, and JavaScript Canvas API

## Quick Start

```bash
git clone https://github.com/amarojtb/realtime-analytics-dashboard.git
cd realtime-analytics-dashboard
open index.html
```

No build tools, no npm install, no server needed.

## Customization

All configuration lives in the `DASHBOARD_CONFIG` object at the top of `index.html`:

### KPI Cards

```javascript
kpis: [
  { label: 'Active Users', min: 12000, max: 14500, prefix: '', suffix: '', icon: 'users', accentColor: 'cyan' },
  { label: 'Revenue', min: 84000, max: 127000, prefix: '$', suffix: '', icon: 'revenue', accentColor: 'emerald' },
  // Add more KPIs...
]
```

| Property | Description |
|----------|-------------|
| `label` | Display name for the KPI |
| `min`/`max` | Random value range for demo data |
| `prefix`/`suffix` | Format decorators (e.g. `$`, `%`, `s`) |
| `icon` | Icon type: `users`, `revenue`, `conversion`, `session` |
| `accentColor` | Color key: `cyan`, `emerald`, `violet`, `amber`, `rose` |
| `decimals` | Optional decimal places (default: 0) |

### Traffic Sources (Donut Chart)

```javascript
sources: [
  { name: 'Direct', pct: 34, colorKey: 'cyan' },
  { name: 'Organic', pct: 28, colorKey: 'emerald' },
  // Add more sources...
]
```

### Other Options

| Option | Default | Description |
|--------|---------|-------------|
| `title` | `'Real-Time Analytics Dashboard'` | Page title |
| `dataPoints` | `24` | Number of data points in line/bar charts |
| `refreshInterval` | `3000` | Auto-refresh interval in ms |
| `sparklinePoints` | `12` | Data points per sparkline |

## Theming

The dashboard uses CSS custom properties for theming. Override `[data-theme="dark"]` or `[data-theme="light"]` blocks to customize colors:

```css
[data-theme="dark"] {
  --bg-deep: #06080d;
  --accent-cyan: #22d3ee;
  /* ... */
}
```

## Architecture

```
index.html (single file)
├── CSS Custom Properties (theming)
├── HTML Structure (grid layout)
└── JavaScript
    ├── DASHBOARD_CONFIG (customization)
    ├── Canvas Rendering (charts)
    ├── KPI Animation (counters + sparklines)
    ├── Donut Chart (segments + legend)
    └── Auto-refresh Loop (data updates)
```

## Browser Support

Works in all modern browsers (Chrome, Firefox, Safari, Edge).

## License

MIT — free to use in personal and commercial projects.
