# cloudeval Docs

Documentation for cloudeval built with MkDocs and Material theme, following the same deployment pattern as [PSRule.Rules.Azure](https://github.com/Azure/PSRule.Rules.Azure).

## Setup

1. Install dependencies:

   ```bash
   pip install -r requirements.txt
   ```

2. Serve documentation locally:

   ```bash
   mkdocs serve
   ```

   Visit `http://127.0.0.1:8000` to view the site.

3. Build documentation:
   ```bash
   mkdocs build
   ```

## Structure

- `docs/` - Documentation source files
- `mkdocs.yml` - MkDocs configuration
- `requirements.txt` - Python dependencies
- `.github/workflows/docs.yaml` - GitHub Actions workflow for deployment

## Deployment

The documentation is automatically deployed to GitHub Pages using GitHub Actions, following the same pattern as PSRule.Rules.Azure:

1. **Automatic Deployment**: On every push to `main` branch
2. **Manual Deployment**: Use workflow dispatch in GitHub Actions
3. **Deployment Process**:
   - Builds MkDocs site
   - Pushes to `gh-pages` branch
   - Deploys via GitHub Pages Actions

### Initial Setup

Before the first deployment:

1. Enable GitHub Pages in repository Settings → Pages (Source: GitHub Actions)
2. Create `gh-pages` branch (see [DEPLOYMENT.md](DEPLOYMENT.md))
3. Push the workflow file to trigger deployment

### Site URL

Once deployed, the site will be available at:

- Custom domain: `https://docs.cloudeval.ai/` (after DNS configuration)
- GitHub Pages: `https://ganakailabs.github.io/cloudeval/`

### Custom Domain

This repository is configured to use the custom domain `docs.cloudeval.ai`.

**For Namecheap DNS setup**, see [NAMECHEAP_DNS_SETUP.md](NAMECHEAP_DNS_SETUP.md) for step-by-step instructions.

For general custom domain information, see [docs/CUSTOM_DOMAIN.md](docs/CUSTOM_DOMAIN.md).

## Documentation

- [Deployment Guide](DEPLOYMENT.md) - Detailed deployment information
- [Custom Domain Setup](docs/CUSTOM_DOMAIN.md) - How to configure a custom domain
