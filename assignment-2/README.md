# Assignment 2 – Cursor.com Clone

A static HTML/CSS clone of [cursor.com](https://cursor.com/), including hero, trusted-by logos, feature sections (Agent, Tab, Ecosystem), testimonials, Stay on the frontier cards, changelog, recent highlights, join us, and footer.

## Live demo

**[View live site →](https://cursor-clone-assignment2.surge.sh)**

## Setup

1. **Clone the repo**
   ```bash
   git clone <repository-url>
   cd Co-Hort/assignment-2
   ```

2. **Open locally**  
   No build step. Open `index.html` in a browser or run:
   ```bash
   npx serve .
   ```
   Then visit **http://localhost:3000**.

## Tech stack

- **HTML5**
- **CSS3** (custom properties, Grid, Flexbox)
- **Font:** [Cursor Gothic](https://github.com/imjac0b/CursorGothic) (loaded via jsDelivr)

## Project structure

```
assignment-2/
├── index.html          # Single-page clone
├── style.css           # All styles
├── README.md           # This file
└── assets/             # Images and logo
    ├── logo-image.svg
    ├── hero.png
    ├── agent-image.png
    ├── autocomplete-image.png
    ├── github-image.png
    ├── jointeam.png
    ├── best_model.png
    ├── complete_understanding.png
    └── develop_enduring_software.png
```

## Deploy (Surge)

To update the live site:

```bash
cd assignment-2
npx surge . --domain cursor-clone-assignment2.surge.sh
```
