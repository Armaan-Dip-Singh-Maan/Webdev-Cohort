# Assignment 1 – Resume

A static HTML resume page with sections for About, Skills, Experience, Projects, Education, and Contact.

---

## Setup

1. **Clone or download** the project:
   ```bash
   git clone <repository-url>
   cd Co-Hort/assignment-1
   ```

2. **No build step** – the project is plain HTML. No npm install or build is required.

3. **(Optional) Run locally** with a simple static server:
   ```bash
   npx serve .
   ```
   Then open **http://localhost:3000** in your browser.

---

## Usage

- **View locally:** Open `index.html` in a browser, or use `npx serve .` and visit the URL shown.
- **Deploy to Surge (free):**
  ```bash
  npx surge . --domain <your-subdomain>.surge.sh
  ```
  First time: Surge will prompt for signup/login. Example live URL: [armaandip-resume.surge.sh](https://armaandip-resume.surge.sh).

---

## Screenshots

*(Recommended: add one or more screenshots of the resume page for evaluation.)*

| Page / Section | Screenshot |
|----------------|------------|
| Full resume (desktop) | ![Resume – full page](screenshots/resume-full.png) |
| Mobile view (optional) | ![Resume – mobile](screenshots/resume-mobile.png) |

**How to add screenshots:**

1. Create a `screenshots` folder in `assignment-1` if it doesn’t exist.
2. Capture the live page (e.g. [armaandip-resume.surge.sh](https://armaandip-resume.surge.sh)) or local view.
3. Save as `screenshots/resume-full.png` (and optionally `screenshots/resume-mobile.png`).
4. Commit and push so the images appear in the README.

---

## Project structure

```
assignment-1/
├── index.html    # Single-page resume
├── README.md     # This file
└── screenshots/  # (optional) Add PNG/JPG for evaluation
```

---

## Tech stack

- **HTML5** only – no CSS framework or JavaScript.
