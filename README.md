# GAIR Lab Website

Welcome to the official website for **GAIR Lab** (Generative AI Research Laboratory) at BITS Pilani, in collaboration with Skillplot.

**Live Site:** https://gairlab.skillplot.org

## About GAIR Lab

GAIR Lab is a research initiative focused on advancing the frontiers of **Generative AI and Agentic Intelligence**. We conduct rigorous academic research while creating practical, open-source tools and frameworks.

### Current Projects

- **Kali**: Agentic Cyber-Defense - Building autonomous AI for security operations
- **Vaani**: Hindi Audiobook Creator - Voice synthesis with emotion control
- **Drishti**: Multimodal Intelligence - Vision-Language models for surveillance analysis
- **Jigyasa**: AlphaFold Interface - Agentic systems for scientific discovery

Learn more: [gairlab.skillplot.org/projects](https://gairlab.skillplot.org/projects)

## Project Structure

```
jekyll-gairlab/
├── index.md                 # Homepage
├── _config.yml              # Jekyll configuration
├── _layouts/                # Page templates
│   ├── default.html         # Base template
│   ├── page.html            # Regular pages
│   ├── project.html         # Project pages
│   └── person.html          # Profile pages
├── _includes/               # Shared components
│   ├── header.html          # Navigation
│   └── footer.html          # Footer
├── _projects/               # Research projects
│   ├── kali.md
│   ├── vaani.md
│   ├── drishti.md
│   └── jigyasa.md
├── _people/                 # Lab members
│   └── ashutosh-bhatia.md
├── pages/                   # Regular pages
│   ├── projects.md
│   ├── people.md
│   ├── about.md
│   └── contact.md
├── assets/
│   └── css/
│       └── style.scss       # Main stylesheet
└── Gemfile                  # Ruby dependencies
```

## Local Development

### Prerequisites

- **Ruby** 2.7+ ([install guide](https://www.ruby-lang.org/en/documentation/installation/))
- **Bundler** (install with `gem install bundler`)

### Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/skillplot/gairlab-www.git
   cd gairlab-www
   ```

2. **Install dependencies:**
   ```bash
   bundle install
   ```

3. **Run the development server:**
   ```bash
   bundle exec jekyll serve
   ```

   The site will be available at: `http://localhost:4000`

4. **Make changes** and watch the site rebuild automatically!

## Deployment

### GitHub Pages (Automatic)

This repository is configured for **automatic GitHub Pages deployment**. Simply push to `main` branch:

```bash
git add .
git commit -m "Update GAIR Lab website"
git push origin main
```

GitHub will automatically:
1. Detect the Jekyll site
2. Build it using their Jekyll environment
3. Deploy to GitHub Pages

**DNS Configuration (Cloudflare):**

Point your domain to GitHub Pages using:
- **CNAME:** `github_username.github.io`
- Or use **A records** (see [GitHub Pages docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site))

### Manual Build & Deploy

To build the site locally for deployment:

```bash
bundle exec jekyll build
```

This creates a `_site/` folder with the complete static site. Upload this to your hosting platform.

## Branding & Customization

### Colors

Edit `_config.yml` and `assets/css/style.scss`:

```yaml
# _config.yml
brand:
  colors:
    midnight: "#0F1B3C"  # Primary text
    gold: "#D4A574"      # Accents
    cyan: "#00D9FF"      # Highlights
    cream: "#F5F1E8"     # Light background
    gray: "#6B7280"      # Secondary text
```

### Fonts

- **Headings:** Libre Baskerville (serif)
- **Body:** Inter (sans-serif)

Both are loaded from Google Fonts CDN.

### Logo

Replace the logo file:
```
assets/img/gair-logo.png        # Header logo
assets/img/gair-logo-white.png  # Hero section
assets/img/gair-logo-social.png # Social media
```

## Adding Content

### New Project

1. Create `_projects/project-name.md`
2. Add YAML front matter:
   ```yaml
   ---
   name: project-name
   title: "Project Title"
   brief_description: "Short description"
   status: Active
   disciplines:
     - "Field 1"
     - "Field 2"
   ---
   ```
3. Write content in Markdown
4. Automatically appears on `/projects/` page

### New Team Member

1. Create `_people/firstname-lastname.md`
2. Add YAML front matter with bio, links, etc.
3. Automatically appears on `/people/` page

### New Page

1. Create `pages/page-name.md`
2. Add YAML front matter with `layout: page` and `permalink`
3. Edit `_includes/header.html` to add navigation link

## Form Handling

The contact form needs a backend service. Options:

### Option 1: Formspree (Recommended)

1. Go to [formspree.io](https://formspree.io)
2. Create free account
3. Create a new form and get the form ID
4. Update `pages/contact.md`:
   ```html
   <form action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```

### Option 2: Netlify Forms

If deploying to Netlify instead of GitHub Pages:

1. Add `netlify-form` attribute to form
2. Netlify automatically handles submissions

### Option 3: External Service

Use Typeform, Google Forms, or similar embedded services.

## Analytics (Optional)

Add tracking code to `_layouts/default.html` before `</body>`:

```html
<!-- Google Analytics 4 -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## FAQ

**Q: How do I add a new navigation link?**  
A: Edit `_includes/header.html` and add to the `.site-nav` list.

**Q: Can I use plugins beyond the GitHub-supported ones?**  
A: GitHub Pages only supports [specific plugins](https://pages.github.com/versions/). Use local builds if you need others.

**Q: How often does the site rebuild?**  
A: Automatically on every push to `main`. Usually takes 30-60 seconds.

**Q: How do I add images?**  
A: Place images in `assets/img/` and reference with: `{{ '/assets/img/filename.png' | relative_url }}`

## Troubleshooting

### Site not updating after push
- Check repository settings: Settings → Pages → Source should be `main` branch
- Wait 1-2 minutes for GitHub to rebuild
- Check [Actions tab](https://github.com/skillplot/gairlab-www/actions) for build errors

### Local build issues
```bash
# Clear cache
rm -rf .jekyll-cache _site

# Reinstall gems
bundle install --redownload

# Rebuild
bundle exec jekyll serve
```

### Styling not applying
- Clear browser cache (Ctrl+Shift+Del)
- Make sure `assets/css/style.scss` is being compiled
- Check browser dev tools for CSS errors

## Contributing

We welcome contributions! If you find issues or want to improve the site:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/improvement`
3. Make changes and test locally
4. Push and create a Pull Request

## Support

Questions about the website? [Contact GAIR Lab](https://gairlab.skillplot.org/contact)

## License

This website and its content are part of the GAIR Lab initiative.

- **Code:** MIT License (see LICENSE file)
- **Content:** Creative Commons Attribution 4.0

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Guide](https://pages.github.com/)
- [Markdown Reference](https://commonmark.org/help/)
- [GAIR Lab Website](https://gairlab.skillplot.org)

---

**Lab Director:** Prof. Ashutosh Bhatia  
**Institution:** BITS Pilani  
**Collaboration:** Skillplot × BITS Pilani  
**Last Updated:** 2024
