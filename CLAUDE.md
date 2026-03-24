# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Website Design & Recreation Rules

### 1. Primary Workflow (Recreation)
When provided with a reference image/screenshot, follow this iterative process:

1. **Generate**: Create a single `index.html` file using Tailwind CSS (via CDN). Include all content inline unless otherwise requested.
2. **Screenshot**: Render the page and take a screenshot using Puppeteer (`npx puppeteer screenshot index.html --fullpage`).
3. **Compare**: Check the screenshot against the reference image for mismatches in:
   - Spacing/Padding (aim for 1:1 match)
   - Font weights, sizes, and line heights
   - Colors (extract exact hex values)
   - Alignment and responsive behavior
4. **Fix**: Edit the code to resolve every mismatch found.
5. **Repeat**: Perform at least **2 comparison rounds**. Only stop when differences are within ~2-3px or the user is satisfied.

### 2. Technical Defaults
- **Styling**: Use Tailwind CSS via CDN (`<script src="https://cdn.tailwindcss.com"></script>`).
- **Icons**: Use **Lucide Icons** or **FontAwesome** for a professional look.
- **Images**:
  - Use `https://source.unsplash.com` for high-quality stock photos.
  - Use `https://placehold.co` only if a specific placeholder is needed.
- **Responsive**: Always use a **Mobile-first** approach (standard Tailwind `sm:`, `md:`, `lg:` breakpoints).

### 3. Interactivity & Functionality
- **JavaScript**: Use modern Vanilla JS (ES6+) for UI logic (e.g., mobile menus, tabs, modals).
- **Feedback**: Add `hover:`, `active:`, and `focus:` states to all interactive elements (buttons, links).
- **Forms**: If a form exists, include basic validation and a "Success" message state.

### 4. Quality & SEO Standards
- **Semantic HTML**: Use proper tags like `<nav>`, `<header>`, `<main>`, `<footer>`, and `<section>`.
- **Accessibility**: Include `alt` text for images and `aria-label` for icon-only buttons.
- **SEO**: Always include:
  - A descriptive `<title>`
  - A `<meta name="description">`
  - A logical heading hierarchy (one `<h1>`, followed by `<h2>`, etc.)

### 5. File Management
- Start with a single `index.html` for speed.
- If the project grows, suggest moving CSS/JS to external files (e.g., `styles.css`, `script.js`).
