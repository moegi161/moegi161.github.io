# DESIGN.md --- Academic Personal Website

> Design specification for Weng Ian Chan's academic personal website.
> Goal: a warm, readable academic homepage that foregrounds research projects, news, publications, and contact information without looking like a dense CV.

---

## 1. Visual Theme & Atmosphere

- **Design direction**: modern academic personal site; clean, warm, research-focused, and easy to update.
- **Tone**: approachable and scholarly rather than corporate or résumé-like.
- **Homepage priority**: give visitors the main information immediately: name, affiliation, bio, news, research interests, projects, and contact.
- **Information density**: medium-low. Prefer title, paragraph, line, and space separators over boxed cards. Use detailed publication records on `publication.html`.
- **Keywords**: academic, research, warm neutral, linear sections, news timeline, readable, accessible, friendly.

---

## 2. Color Palette & Roles

### Brand

- **Brand Yellow** (`#ffd500`): primary accent for active navigation, primary buttons, badges, and highlighted states.
- **Brand Pink** (`#ffa8e2`): decorative secondary accent for selected tags or subtle project labels.
- **Brand Blue** (`#248cff`): external links, paper/code/project-page emphasis, and technical accents.
- **Brand Lime** (`#b2ff53`): playful supporting accent used sparingly.
- **Brand Orange** (`#ffa646`): warm accent for news, talks, or awards.
- **Brand Purple** (`#6c55f0`): research/project-category accent for generative AI and vision topics.

### Neutral

| Token | Hex | Role |
|---|---:|---|
| Text Primary | `#272727` | Headings and main body text |
| Text Secondary | `#585858` | Metadata, captions, affiliations |
| Text Muted | `#77776b` | Dates and subdued notes |
| Page Background | `#ffffff` | Body background |
| Warm Beige | `#f0f0e2` | Alternate section and media-placeholder background |
| Light Gray | `#f8f8f8` | Nav pills and subtle surfaces |
| Border Light | `#e3e3d2` | Row dividers and subtle separators |
| Border Gray | `#b7b7b7` | Stronger separators |
| White | `#ffffff` | Header surface and small media/link surfaces |
| Footer Background | `#272727` | Footer |
| Footer Text | `#ffffff` | Text on dark footer |

### Semantic

- **Success**: `#16a34a`
- **Warning**: `#d97706`
- **Danger**: `#dc2626`
- **Info**: `#248cff`

---

## 3. Typography

Use a modern sans-serif stack with strong readability.

```css
font-family:
  Inter,
  "Noto Sans",
  "Noto Sans JP",
  -apple-system,
  BlinkMacSystemFont,
  "Segoe UI",
  Arial,
  sans-serif;
```

| Role | Size | Weight | Line Height | Color |
|---|---:|---:|---:|---|
| Site Name | 18-22px | 800 | 1.2 | `#272727` |
| Hero Name | 44-58px | 850 | 1.05-1.15 | `#272727` |
| Hero Subtitle | 18-23px | 500-650 | 1.4 | `#585858` |
| Section Heading | 30-40px | 800 | 1.2 | `#272727` |
| Project / item title | 20-24px | 750 | 1.3 | `#272727` |
| Body | 16-18px | 400 | 1.65 | `#272727` |
| Metadata | 14-15px | 500 | 1.5 | `#585858` |
| Button / Nav | 14-15px | 800 | 1.2 | `#272727` |

Guidelines:

- Keep body text spacious and readable.
- Avoid tiny CV-style text.
- Use short homepage paragraphs.
- Use metadata styling for dates, venues, affiliations, and author lists.

---

## 4. Layout Principles

### Container

```css
.container {
  max-width: 1120px;
  margin: 0 auto;
  padding: 0 24px;
}
```

- Desktop section spacing: `72px` to `96px`.
- Mobile section spacing: `48px` to `64px`.
- Use a white page background. The header uses Brand Yellow as the main surface; white is reserved for content background, buttons, tags, and small link surfaces.

### Homepage Sections

1. Header / navigation
2. Hero / about
3. News
4. Research interests
5. Projects
6. Contact
7. Footer

`publication.html` contains the full publication list.

---

## 5. Components

### Header

- Yellow header surface.
- Sticky positioning is allowed.
- Use pill navigation with white hover/active states.

```css
.site-header {
  background: #ffd500;
  border-bottom: 1px solid rgba(39, 39, 39, 0.12);
}
```

### Buttons

```css
.button-primary {
  border-radius: 50px;
  padding: 13px 20px;
  background: #ffd500;
  color: #272727;
  font-weight: 800;
}

.button-secondary {
  border-radius: 50px;
  padding: 12px 18px;
  background: #ffffff;
  color: #272727;
  border: 1px solid #e3e3d2;
  font-weight: 800;
}
```

### Section Separators

Use title, paragraph, line, and whitespace as the default structure. Boxed cards should be avoided unless a media-heavy item truly needs a visual boundary.

```css
.section-rule {
  border-top: 1px solid #e3e3d2;
  padding-top: 28px;
}
```

### Project Rows

Each project should include:

- thumbnail image or embedded video,
- title,
- authors,
- venue/status,
- short description,
- links to paper, code, project page, video, or demo.

Desktop layout:

```text
[ media thumbnail/video ] [ title, authors, venue, description, links ]
```

Projects should be separated by a top/bottom border and generous spacing, not a heavy card shadow.

Mobile layout:

```text
[ media thumbnail/video ]
[ title, authors, venue, description, links ]
```

---

## 6. Media Guidelines

- Project thumbnails should use `16:9` aspect ratio.
- Use real project screenshots, diagrams, or video frames where possible.
- If no image is available, use a warm placeholder with a short project label.
- Every image needs descriptive `alt` text.

---

## 7. Responsive Behavior

| Name | Width |
|---|---:|
| Mobile | `<= 767px` |
| Tablet | `768px-1023px` |
| Desktop | `>= 1024px` |

Mobile rules:

- Stack hero content and project rows vertically.
- Keep body text at least `16px`.
- Make pill buttons wrap naturally.
- Reduce hero name to around `38px`.

---

## 8. Accessibility

- Use `#272727` for text instead of pure black.
- Do not put yellow text on white/beige backgrounds.
- Use yellow backgrounds only with dark text.
- Provide visible focus states.
- Use descriptive link labels such as `Paper`, `Code`, `Project page`, and `Video`.

---

## 9. Do's and Don'ts

### Do

- Keep the homepage concise and research-oriented.
- Put projects before CV-like details.
- Use project rows, thumbnails, clear titles, short paragraphs, and links to make work scannable.
- Keep news easy to update.
- Use `publication.html` for the full publication list.

### Don't

- Do not make the homepage a full CV.
- Do not overuse all accent colors at once.
- Do not use red as the primary color.
- Do not hide important project links.
- Do not require the CV to understand the research.

---

## 10. Quick Reference

```text
Theme: Warm academic personal website
Background: #ffffff
White surfaces: #ffffff
Primary text: #272727
Secondary text: #585858
Primary accent: #ffd500
Link accent: #248cff
Secondary accents: #ffa8e2, #b2ff53, #ffa646, #6c55f0
Font: Inter / Noto Sans / system sans-serif
Rows: top/bottom borders, generous spacing, minimal shadows
Buttons: pill shape, 50px radius
Projects: media left + content right on desktop, stacked on mobile
```


## 11. Updated Layout Preference

- Do not overuse card components.
- Prefer a simple editorial rhythm: title, paragraph, line, space.
- Use borders and whitespace for separation.
- Keep boxed surfaces and shadows minimal; the current implementation uses linear project rows and publication rows.
- The color palette remains the warm yellow-based palette defined above.


## 12. File Organization

- Keep website content in HTML files.
- Keep styles in external CSS files under `assets/css/`.
- The current homepage uses `assets/css/style.css`.
- The publications page uses `assets/css/publication.css`.
