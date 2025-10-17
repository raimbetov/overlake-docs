# overlake.bio Documentation

Documentation website for overlake.bio, built with Jekyll and the Just the Docs theme.

**Live Site:** [https://docs.overlake.bio](https://docs.overlake.bio)

## Features

- 🎨 Custom "water" color scheme
- 🔍 Built-in search functionality
- 📐 MathJax support for mathematical equations
- 📱 Responsive design
- 🎯 Custom overlake.bio branding

## Local Development

### Prerequisites

- Ruby 3.0+ ([Installation guide](https://www.ruby-lang.org/en/documentation/installation/))
- Bundler gem: `gem install bundler`

### Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/YOUR_USERNAME/overlake-docs.git
   cd overlake-docs
   ```

2. **Install dependencies**
   ```bash
   bundle install
   ```

3. **Run the local server**
   ```bash
   bundle exec jekyll serve
   ```

4. **View the site**

   Open your browser to [http://localhost:4000](http://localhost:4000)

### Live Reloading

The server watches for file changes and rebuilds automatically. Refresh your browser to see updates.

## Project Structure

```
overlake-docs/
├── _config.yml              # Site configuration
├── _includes/
│   ├── head_custom.html     # Custom head content (MathJax + logo)
│   └── mathjax.html         # MathJax script loader
├── _layouts/
│   └── mathjax.html         # Optional MathJax layout
├── _sass/
│   └── color_schemes/
│       └── water.scss       # Custom color scheme
├── assets/
│   └── js/
│       └── mathjax-script-type.js  # MathJax configuration
├── index.md                 # Homepage
├── Gemfile                  # Ruby dependencies
└── README.md               # This file
```

## Adding Content

### Create a New Page

1. Create a new `.md` file in the root directory:

```markdown
---
layout: default
title: Your Page Title
nav_order: 2
description: "Brief description for SEO"
permalink: /your-page-url
---

# Your Page Title

Your content here...
```

2. The page will automatically appear in the navigation sidebar.

### Using MathJax

MathJax is enabled site-wide. Use LaTeX syntax for equations:

**Inline math:**
```markdown
The area of a circle is $$A = \pi r^2$$ where $$r$$ is the radius.
```

**Display math:**
```markdown
$$
E = mc^2
$$
```

### Navigation Order

Control the order of pages in the sidebar with `nav_order`:

```yaml
---
nav_order: 1  # Lower numbers appear first
---
```

## Configuration

Key settings in [`_config.yml`](_config.yml):

```yaml
title: "overlake.bio/documentation"
description: "Documentation"
url: "https://docs.overlake.bio"
theme: just-the-docs
color_scheme: water        # Custom color scheme
search_enabled: true       # Enable search
math: mathjax             # Enable MathJax site-wide
```

## Deployment

The site is automatically deployed to GitHub Pages when you push to the `master` branch.

### Manual Deployment

1. **Commit your changes**
   ```bash
   git add .
   git commit -m "Your commit message"
   ```

2. **Push to GitHub**
   ```bash
   git push origin master
   ```

3. **GitHub Pages builds automatically**

   The site will be live at `https://docs.overlake.bio` within a few minutes.

## Customization

### Color Scheme

The custom "water" theme is defined in [`_sass/color_schemes/water.scss`](_sass/color_schemes/water.scss).

Modify colors by editing the SCSS variables:

```scss
$water-blue: #0969da;
$water-blue-light: #218bff;
$water-gray: #656d76;
```

### Logo

The overlake.bio logo is injected via JavaScript in [`_includes/head_custom.html`](_includes/head_custom.html).

Modify the logo markup in the `<script>` section at the bottom of that file.

## Troubleshooting

### Build Errors

**Problem:** Site won't build
```bash
bundle exec jekyll doctor  # Check for configuration issues
bundle exec jekyll build --verbose  # Verbose build output
```

**Problem:** Missing dependencies
```bash
bundle install  # Reinstall dependencies
```

### Port Already in Use

If port 4000 is occupied:
```bash
bundle exec jekyll serve --port 4001
```

### Clear Cache

If changes aren't appearing:
```bash
rm -rf _site .jekyll-cache
bundle exec jekyll serve
```

## Contributing

1. Create a new branch for your changes
2. Make your edits
3. Test locally with `bundle exec jekyll serve`
4. Commit and push your branch
5. Create a pull request

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [Just the Docs Theme](https://just-the-docs.com/)
- [MathJax Documentation](https://docs.mathjax.org/)
- [Kramdown Syntax](https://kramdown.gettalong.org/syntax.html)

## License

[Add your license here]
