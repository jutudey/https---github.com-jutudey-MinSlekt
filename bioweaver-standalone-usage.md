# BioWeaver Standalone Theme

Use `bioweaver-standalone.css` when another project needs the same visual
language as BioWeaver's HTML book pages: warm paper, Garamond typography,
burgundy accents, the large ghost initial, drop caps, sepia letter cards, and
infoboxes.

## Include The CSS

```html
<link rel="stylesheet" href="/css/bioweaver-standalone.css">
```

The stylesheet imports these Google Fonts:

- `EB Garamond` for body text
- `Cormorant Garamond` for headings and display text
- `Italianno` for letter signatures

## Basic Page

```html
<body class="bw-theme">
  <main class="bw-page bw-prose">
    <h1 class="bw-chapter-title" data-initial="K">Kobenhavn 1903</h1>

    <p>
      First paragraph of the page. The first letter becomes a drop cap, and
      the `data-initial` value on the heading creates the large ghost letter.
    </p>

    <p>Second paragraph. Consecutive paragraphs receive book-style indents.</p>
  </main>
</body>
```

## Letter Transcript

The standalone stylesheet supports both prefixed class names and the original
BioWeaver class names.

```html
<section class="bw-letter">
  <div class="bw-letter-header">
    <p>Kobenhavn, 27. mai 1903</p>
  </div>

  <p>Kjaere mama!</p>
  <p>Brevtekst her...</p>

  <div class="bw-letter-signature">
    <p>Din Anna</p>
  </div>
</section>
```

Original BioWeaver names also work inside `.bw-page`:

```html
<section class="letter-transcript">
  <div class="letter-header"><p>Kobenhavn, 27. mai 1903</p></div>
  <p>Kjaere mama!</p>
  <div class="letter-signature"><p>Din Anna</p></div>
</section>
```

## Infobox

```html
<aside class="bw-infobox">
  <p><strong>Et historisk sideblikk</strong></p>
  <p>Infobox body text goes here.</p>
</aside>
```

The first paragraph becomes the centered title bar automatically.

## Optional Multi-Page Navigation

For a static multi-page site, this gives you the same quiet hamburger menu and
bottom previous/next pager style.

```html
<input class="bw-nav-toggle" type="checkbox" id="bw-nav-toggle">

<label class="bw-nav-button" for="bw-nav-toggle" aria-label="Open chapter menu">
  <span></span>
  <span></span>
  <span></span>
</label>

<nav class="bw-chapter-menu" aria-label="Chapters">
  <ol>
    <li class="current"><a href="/chapter-1.html">Kobenhavn 1903</a></li>
    <li><a href="/chapter-2.html">Hjem til Oslo</a></li>
  </ol>
</nav>

<nav class="bw-pager" aria-label="Page navigation">
  <a class="bw-prev" href="/chapter-1.html">
    <span class="bw-dir">Previous</span>
    <span class="bw-title">Kobenhavn 1903</span>
  </a>
  <a class="bw-next" href="/chapter-3.html">
    <span class="bw-dir">Next</span>
    <span class="bw-title">Neste kapittel</span>
  </a>
</nav>
```

## Customizing

Override the prefixed CSS variables after the stylesheet is loaded:

```css
:root {
  --bw-page-bg: #faf6ee;
  --bw-ink: #1a1612;
  --bw-accent: #6b1f2a;
  --bw-measure: 60ch;
}
```

