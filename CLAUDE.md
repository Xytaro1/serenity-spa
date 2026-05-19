# Serenity Spa Project

## Auto-deploy rule

After ANY task that modifies files in this project, ALWAYS finish with:

```bash
git add . && git commit -m "Update: $(date +%Y-%m-%d_%H-%M)" && git push origin main
```

GitHub Pages auto-deploys from main branch within 2 minutes. Live URL: https://xytaro1.github.io/serenity-spa/

## Stack

HTML + Tailwind CDN, no frameworks. All in single index.html file.

## Design docs (read before changes)

- research.md — market research
- sections.md — section map
- design-system.md — colors, typography, spacing
