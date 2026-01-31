# Mohammadreza Hendiani - Personal Portfolio & Blog

A multilingual Hugo-based personal website with portfolio, blog, and about sections.

**Languages**: English (default) | Deutsch

## Quick Start

### 1. Prerequisites

Install Hugo (extended version):

```bash
# Fedora
sudo dnf install hugo

# macOS
brew install hugo

# Or download from https://gohugo.io/installation/
```

### 2. Clone and Setup Theme

```bash
# Clone this repo
git clone https://github.com/Man2Dev/Man2Dev.github.io.git
cd Man2Dev.github.io

# Add PaperMod theme as submodule
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

### 3. Local Development

```bash
hugo server -D
# Visit http://localhost:1313
```

### 4. Deploy to GitHub Pages

1. Push to your `Man2Dev.github.io` repository
2. Go to **Settings → Pages → Source: GitHub Actions**
3. The site will auto-deploy on every push to `main`

## Structure

```
.
├── content/
│   ├── about.md              # English About page
│   ├── about.de.md           # German About page
│   ├── blog/
│   │   ├── _index.md         # English blog index
│   │   ├── _index.de.md      # German blog index
│   │   ├── *.md              # English posts
│   │   └── *.de.md           # German posts
│   └── portfolio/
│       ├── _index.md         # English portfolio index
│       ├── _index.de.md      # German portfolio index
│       ├── *.md              # English projects
│       └── *.de.md           # German projects
├── hugo.toml                  # Site configuration
└── .github/workflows/         # Auto-deployment
```

## Adding Content

### New Blog Post (English)

```bash
hugo new blog/my-new-post.md
```

For German version, create `content/blog/my-new-post.de.md`

### New Portfolio Project

```bash
hugo new portfolio/my-project.md
```

For German version, create `content/portfolio/my-project.de.md`

## Multilingual Support

- English is the default language (no URL prefix)
- German pages are available at `/de/...`
- A language switcher is available in the navigation

### Adding Translations

For any content file `example.md`, create `example.de.md` in the same directory with translated content.

## Customization

Edit `hugo.toml` to change:

- Site title and description (per language)
- Social links
- Menu items (per language)
- Theme settings
- Home page content (per language)

## Theme

Using [PaperMod](https://github.com/adityatelange/hugo-PaperMod) - a fast, clean Hugo theme.

See [PaperMod documentation](https://adityatelange.github.io/hugo-PaperMod/) for more customization options.

## License

Content © Mohammadreza Hendiani. Theme: GPL-3.0-or-later License.
