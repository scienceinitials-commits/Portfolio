# Nishant Kumar Singh — Portfolio

A cinematic, single-page personal portfolio built with pure HTML, CSS, and vanilla JavaScript. No frameworks, no build tools — just hand-crafted code with a focus on visual atmosphere and smooth interaction.

**Live at:** `n2.html` → open directly in any modern browser.

---

## Overview

This portfolio presents Nishant Kumar Singh, a B.Tech Computer Science student at KIIT University and tech startup founder, specialising in Java backend engineering and Spring Boot microservices.

The design aesthetic is dark and editorial — think film titles, not dashboards. Every animation, canvas effect, and typography choice is intentional.

---

## Features

### Cinematic Intro Sequence
On load, a full-screen particle canvas plays an opening sequence that fades in "A Portfolio by → Nishant Kumar Singh → B.Tech Student & Tech Founder" with timed letterbox bars, then dissolves into the main site.

### Interactive Star Field (Hero Canvas)
The hero section renders a live canvas star field with:
- 160 individually animated, twinkling stars across three size/brightness tiers
- Coloured stars (blue-white and warm-gold hues) for variety
- Cursor-proximity lighting — stars near your mouse glow and grow
- Constellation lines that appear between close stars, brightening near the cursor
- Shooting stars that spawn randomly every 3–5 seconds
- Cursor comet trail — a glowing streak that follows fast mouse movement
- Mouse ripple rings triggered by movement speed and clicks

### Custom Cursor
- A 5 px white dot that scales and glows with mouse velocity
- A larger trailing ring that follows with lerp smoothing
- Expands to a hollow 38 px ring when hovering interactive elements

### Multi-Layer Parallax
Mouse movement drives independent depth layers across the entire page: the hero content drifts gently, floating decorative text elements respond at different speeds, and section background numerals float at their own rate.

### Scroll Reveal Animations
All content blocks use an `IntersectionObserver` to fade and slide up into view as you scroll, with staggered delays (`.rd1`–`.rd5`) for sequential reveals within sections.

### Sections
| # | Section | Content |
|---|---------|---------|
| 01 | Hero | Name, title, description, CTAs, live status pill |
| 02 | About | Bio, fact table, key metrics (projects, GFG prize) |
| 03 | Journey | Vertical timeline from 2022 to present |
| 04 | Skills | 6 featured skill cards + full tech stack grid |
| 05 | Work | 4 projects with descriptions and stack tags |
| 06 | Contact | Email CTA, social links, animated particle canvas |

---

## Projects Featured

**ProfMash** — Academic Review Platform  
Side-by-side professor comparison and rating tool for students. Stack: Java, Spring Boot, Microservices.

**Pocket+** — Mental Health App  
A safe-space mental health companion for young adults. Stack: Java, Spring Boot.

**Friends** — Social Networking App  
Full social network backend with communities and feeds. Stack: Java, Microservices.

**Geeks for Geeks Competition** — 2nd Prize  
Algorithm and data structures contest. Stack: C, Java, Algorithms, Data Structures.

---

## Tech Stack

**Languages:** Java 17+, SQL, Bash, C  
**Frameworks:** Spring Boot, Spring MVC, Spring Security, Hibernate, JPA  
**Databases:** MySQL, PostgreSQL, MongoDB, Redis  
**DevOps & Tools:** Git, Docker, Maven, Postman, IntelliJ, Swagger

---

## File Structure

This is a single-file portfolio — everything lives in `n2.html`:

```
n2.html
├── <head>          Google Fonts (Cormorant Garamond, Montserrat, JetBrains Mono)
├── <style>         All CSS — ~200 lines, mobile-responsive
├── <body>
│   ├── #cur / #cur-trail     Custom cursor elements
│   ├── #bar-top / #bar-bot   Cinematic letterbox bars
│   ├── #open-canvas          Intro particle canvas
│   ├── #intro                Intro text overlay
│   └── #site                 Main scrollable site
│       ├── <nav>             Sticky nav with active-link tracking
│       ├── #hero             Star field canvas + hero content
│       ├── #about            Bio + metrics + fact table
│       ├── #timeline         Journey timeline
│       ├── #skills           Skill cards + tech category grid
│       ├── #projects         Project list
│       ├── #contact          Contact CTA + particle canvas
│       └── <footer>
└── <script>        ~500 lines vanilla JS — all engines below
    ├── Opening sequence      Timed intro animation
    ├── Hero canvas           Star field, shooting stars, cursor effects
    ├── Contact canvas        Ambient particle layer
    ├── Cursor                Custom cursor + trail animation
    ├── Nav                   Scroll-based active state + bg opacity
    ├── Scroll reveal         IntersectionObserver reveal system
    ├── Smooth anchors        Smooth-scroll nav links
    └── Parallax              Mouse-driven multi-layer depth system
```

---

## Running Locally

No build step required. Just open the file:

```bash
# Option 1 — direct
open n2.html

# Option 2 — local server (avoids any browser file:// restrictions)
npx serve .
# or
python3 -m http.server 8080
```

Requires a modern browser with Canvas 2D and `IntersectionObserver` support (Chrome 88+, Firefox 78+, Safari 14+).

---

## Customisation

All personal content is in the HTML body. To adapt this portfolio:

| What to change | Where |
|----------------|-------|
| Name & title | `#intro` div + `#hero` `.hero-h1` |
| Bio & facts | `#about` section |
| Timeline entries | `#timeline` `.tl-item` blocks |
| Skill tags | `#skills` `.tc-tag` spans |
| Projects | `#projects` `.proj-item` blocks |
| Contact email | `#contact` `.contact-email-btn` href |
| Social links | `#contact` `.contact-socials` |
| Colour scheme | CSS custom properties at top of `<style>` |
| Star density | `STAR_N` constant in `<script>` |

---

## Browser Notes

- Custom cursor is hidden on touch/mobile (≤900 px breakpoint reverts to `cursor: auto`)
- The `nav-cta` hire button and section numbers are hidden on mobile
- Project stack columns collapse to a two-column grid on small screens
- The `scroll-behavior: smooth` on `#site` handles anchor navigation natively

---

## Contact

**Nishant Kumar Singh**  
B.Tech Computer Science — KIIT University, Bhubaneswar  
GitHub: [scienceinitials-commits](https://github.com/scienceinitials-commits/Portfolio)  
LinkedIn: [nishant-kumar-337b20373](https://www.linkedin.com/in/nishant-kumar-337b20373)