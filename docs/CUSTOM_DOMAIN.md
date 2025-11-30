# Setting Up a Custom Domain for GitHub Pages

This guide explains how to configure a custom domain for your GitHub Pages documentation site, similar to how PSRule.Rules.Azure uses `azure.github.io/PSRule.Rules.Azure`.

## Overview

GitHub Pages supports custom domains. You can use either:

- A subdomain (e.g., `docs.yourdomain.com`)
- An apex domain (e.g., `yourdomain.com`)
- Both

## Step 1: Add CNAME File (for subdomain)

If you want to use a subdomain (e.g., `docs.yourdomain.com`):

1. Create a file named `CNAME` (no extension) in the `docs/` directory
2. Add your custom domain name inside:
   ```
   docs.yourdomain.com
   ```
3. Commit and push the file to the `main` branch

**Note:** The CNAME file should be placed in the `docs/` directory. The GitHub Actions workflow will automatically copy it to the `gh-pages` branch root during deployment. For this repository, the CNAME file is already configured for `docs.cloudeval.ai`.

## Step 2: Configure GitHub Repository Settings

1. Go to your repository on GitHub
2. Navigate to **Settings** → **Pages**
3. In the **Custom domain** field, enter your custom domain (e.g., `docs.yourdomain.com`)
4. Click **Save**
5. Enable **Enforce HTTPS** (recommended)

## Step 3: Configure DNS Records

### For Subdomain (e.g., `docs.yourdomain.com`)

Add a **CNAME record** in your DNS provider:

- **Type:** CNAME
- **Name:** `docs` (or your subdomain)
- **Value:** `ganakailabs.github.io` (or `yourusername.github.io`)
- **TTL:** 3600 (or default)

### For Apex Domain (e.g., `yourdomain.com`)

Add **A records** pointing to GitHub's IP addresses:

- **Type:** A
- **Name:** `@` (or leave blank for apex)
- **Value:** One of these IPs:
  - `185.199.108.153`
  - `185.199.109.153`
  - `185.199.110.153`
  - `185.199.111.153`
- **TTL:** 3600 (or default)

You need to add **all four A records** for redundancy.

### For Both Apex and WWW

If you want both `yourdomain.com` and `www.yourdomain.com`:

1. Add the four A records for the apex domain (as above)
2. Add a CNAME record:
   - **Type:** CNAME
   - **Name:** `www`
   - **Value:** `yourusername.github.io`
   - **TTL:** 3600

## Step 4: Update mkdocs.yml

Update the `site_url` in your `mkdocs.yml` to match your custom domain:

```yaml
site_url: https://docs.yourdomain.com/
```

## Step 5: Wait for DNS Propagation

DNS changes can take:

- **Minimum:** A few minutes
- **Typical:** 1-4 hours
- **Maximum:** Up to 24-48 hours

You can check DNS propagation using tools like:

- [whatsmydns.net](https://www.whatsmydns.net/)
- `dig` or `nslookup` commands

## Step 6: Verify SSL Certificate

After DNS propagates, GitHub will automatically provision an SSL certificate for your custom domain. This usually takes a few minutes to a few hours.

You can check the certificate status in:

- **Settings** → **Pages** → **Custom domain**

Once the certificate is ready, enable **Enforce HTTPS**.

## Troubleshooting

### Domain not resolving

1. Verify DNS records are correct
2. Wait for DNS propagation
3. Check DNS using `dig docs.yourdomain.com` or online tools

### SSL certificate not provisioning

1. Ensure DNS is correctly configured
2. Wait up to 24 hours for automatic provisioning
3. Check GitHub Pages settings for any error messages

### Mixed content warnings

- Ensure all links use HTTPS
- Update `site_url` in `mkdocs.yml` to use HTTPS

## Example: PSRule.Rules.Azure Setup

PSRule.Rules.Azure uses:

- **GitHub Pages URL:** `https://azure.github.io/PSRule.Rules.Azure/`
- **Organization:** `Azure`
- **Repository:** `PSRule.Rules.Azure`

They use the default GitHub Pages subdomain pattern (`organization.github.io/repository`), which doesn't require a custom domain but follows the same deployment process.

## References

- [GitHub Pages Custom Domain Documentation](https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site)
- [GitHub Pages Documentation](https://docs.github.com/pages)
