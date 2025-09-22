# REFLECTION.md

## Code Review Process

This explains what my code does, how I worked, what was hard, and what I would change.

**Starting Idea:** I built a single‑page resume site. It uses semantic HTML sections and a small CSS file. The page is clean, readable, and works on phones, tablets, and desktops.

**Main parts and how they work together:**

- **HTML structure**
  - `<header role="banner">` shows my name, a short line about me, and my email. It holds my photo so the page has a clear identity.
  - `<nav role="navigation">` gives quick links to each section on the page. This helps keyboard users and makes moving around easy.
  - `<main role="main">` is the core content. It holds five sections:
    - **About** explains who I am in two short paragraphs.
    - **Education** is a simple list of highlights.
    - **Experience** has a job “card” with a title, dates, and bullet points.
    - **Skills** is a short bullet list.
    - **Projects** has a title, one‑line summary, and bullet points.
  - `<footer role="contentinfo">` repeats my email and the copyright line.
  - Every section has an **`id`** and **`aria-labelledby`** that points to its own `<h2>`. This improves screen reader navigation.

- **CSS**
  - A small set of **variables** controls colors: background, text, muted text, accent (link color), surfaces, borders.
  - I use **CSS Grid** for the header and main area, and **Flexbox** for the job header row. This keeps layout stable.
  - I added a **skip link** and **focus outlines** for keyboard users.
  - I added **media queries** for tablet and desktop so the layout adapts.
  - I added **print styles** so “Save as PDF” is a clean single column.

Together, these parts meet the goal: a simple resume site that looks neat, reads well, and works for many users.

---

## What was my coding process?

I followed the assignment steps and worked in small chunks. After each chunk I tested the page and wrote a short, meaningful commit message.

- **Plan**: I started with the Module 1 HTML and made a basic style file. 
- **Build**: I added layout with Grid and Flex, then fonts, then responsive rules, then accessibility, then testing and small polish.
- **Test**: I opened the page at phone width, tablet width, and desktop width. I also used print preview.
- **Adjust**: I fixed spacing and made sure links and focus rings were easy to see.

I kept each commit focused on **one change** so the history is easy to read.

---

## What challenges did I have?

- **Layout choices**: Deciding when to use Grid vs Flex. I solved this by using **Grid** for big page layout (header/main) and **Flex** inside small rows (job header).  
- **Responsive spacing**: On smaller screens things felt tight. I added gaps and padding in the media queries.  
- **Keyboard support**: I wanted keyboard users to move quickly. I added a **skip link**, made sure **focus outlines** are strong, and created an in‑page **nav** with anchors.  
- **Accessibility**: I reviewed color contrast. The accent link color `#2563eb` on white has a contrast ratio that passes WCAG AA for normal text. The muted text `#6b7280` on white also passes AA.  
- **Print/PDF**: Boxes looked heavy in print at first. I removed borders/shadows in the print stylesheet and forced a single column.

---

## What would I do differently now?

- **Start mobile-first**: Begin with the smallest layout and add up, so spacing and order are perfect on phones first.  
- **Design tokens first**: Lock colors, spacing scale, and typography at the start. It speeds up later steps.  
- **Accessibility checklist**: Run through headings, landmarks, focus order, and color contrast earlier.  

## How each assignment step is met

### 1 Design Principles
- I picked a small color set: text `#111827`, accent `#2563eb`, muted `#6b7280`, surfaces `#ffffff` / `#f8fafc`, borders `#e5e7eb`.
- I documented the choices in `DESIGN_GUIDELINES.md`.
- Typography uses Inter with safe fallbacks.

### 2 Layout & Positioning
- The header uses **Grid** (`.header-inner`) for photo + identity.
- The main area uses **Grid**, and each job row uses **Flex** for title/date layout.
- Sections and the job card use soft borders and rounded corners.

### 3 Custom Fonts
- I loaded **Inter** from Google Fonts and set it on `body` with a fallback stack.

### 4 Responsive Design
- I added media queries at **600px**, **900px**, and **1200px**.
- The main area becomes **two columns** at desktop width.
- Navigation is simple and easy to tap: I added a small **in‑page nav** with anchor links under the header.

### 5 Accessibility
- I used **landmark roles** (`banner`, `navigation`, `main`, `contentinfo`).
- I added **`aria-labelledby`** for each section so screen readers can jump by headings.
- I added a **skip link** and strong **focus outlines**.
- I checked **color contrast** (AA pass as noted above).

### 6) Testing and Refinement
- I checked typography, spacing, hover, focus, and mobile behavior.
- I created **print styles** so PDF export looks clean and single‑column.

### 7) Final Review
- I normalized heading spacing and link hover underline.
- I cleaned up CSS groupings and kept variable names consistent.