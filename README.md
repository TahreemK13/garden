# Garden

> A digital garden — part notebook, part library, part creative studio.  
> Live at [garden.tahreemkarim.xyz](https://www.garden.tahreemkarim.xyz)
> Library at [garden.tahreemkarim.xyz/library](https://www.garden.tahreemkarim.xyz/library)

---

## What is this?

This is the source for Tahreem Karim's digital garden: a personal corner of the internet that sits somewhere between a blog, a commonplace book, and a portfolio annex. It is loosely structured, and perpetually in progress.

The garden is organized around the metaphor of growth: ideas arrive as seeds, develop into seedlings, and occasionally bloom into something finished. Nothing here necessarily has to be final.

---

## Structure

```
garden/
├── index.html              # Garden home — scatter-card layout
├── library.html            # Reading log with filter/sort and drawer
├── posts/
│   └── on-philosophy.html  # Long-form posts / grown seedlings
├── covers/                 # Local book cover screenshots (.png)
├── images/                 # General image assets
└── README.md
```

**No build step. No framework. No dependencies.** Everything is plain HTML, CSS, and vanilla JS. Open any file in a browser and it works.

---

## Pages

### `index.html` — The garden
A scatter card board of current thoughts, seedlings, and links. Cards are positioned by hand using CSS custom properties (`--r`, `--ty`, `--z`) and represent ideas at various stages of development — seed, seedling, sprout, bloom.

### `library.html` — The library
A visual reading log. Each book is a card with a local cover image, genre tag, and year read. Clicking a card opens a slide-in drawer with a personal note and a link to an independent bookstore or the original source. Supports genre filtering and date sorting.

### `posts/` — Long-form writing
Fully developed thoughts that have grown past card size. Currently:
- `on-philosophy.html` — On why philosophy is not "just sitting around thinking"

---

## Adding a book to the library

Each book is a `div.book-card` inside `#gallery` in `library.html`. Copy an existing card and update the `data-*` attributes:

| Attribute | Description |
|---|---|
| `data-year` | Numeric sort key — format `YYYYMMDD` (e.g. `20240000`, `20130400` for spring) |
| `data-genre` | One of: `fiction`, `comics`, `science`, `nonfiction` |
| `data-title` | Full title |
| `data-author` | Author(s) |
| `data-display-year` | Human-readable date shown on the card (e.g. `Spring 2013`) |
| `data-cover` | Path to cover image — `covers/slug.png` |
| `data-link` | Bookstore or source URL |
| `data-link-label` | Link label shown in the drawer (e.g. `Green Apple Books`) |
| `data-note` | Your personal note — shown in the drawer |

Drop the cover image as a `.png` into the `covers/` folder. If the image is missing, a text fallback renders automatically.

---

## Adding a post

1. Create `posts/your-title.html` — use an existing post as a template
2. Link to it from a card on `index.html`:
```html
<a href="posts/your-title.html" style="text-decoration:none; color:inherit; display:block;">
  <div class="pin-card" ...>
    ...
  </div>
</a>
```

---

## Design system

The garden uses a consistent set of CSS custom properties defined in `:root` on each page:

| Variable | Role |
|---|---|
| `--cream` / `--cream-dark` / `--cream-deeper` | Background layers |
| `--ink` / `--ink-mid` / `--ink-light` / `--ink-faint` | Text hierarchy |
| `--green` / `--green-mid` / `--green-faint` / `--green-wash` | Primary accent |
| `--rust` | Comics accent |
| `--gold` | Science accent |
| `--blue` | Nonfiction accent |
| `--rule` | Borders and dividers |
| `--white` | Card and drawer backgrounds |

**Fonts** (loaded from Google Fonts):
- `Playfair Display` — headings and titles
- `Lora` — body text
- `DM Mono` — labels, metadata, UI chrome

---

## Philosophy

The garden is deliberately hand built. There is no CMS, no static site generator, no templating engine. Each page is written directly. This is a feature: every card, every margin, every line of CSS reflects an artistic choice, not a framework.

Independent bookstore links are used wherever possible. Buy local when you can.

---

## License

Content (writing, notes, book selections) © Tahreem Karim, all rights reserved.  
Code (HTML/CSS/JS structure) is available for reference and learning. Please don't lift the design wholesale but if something here is useful, use it.
