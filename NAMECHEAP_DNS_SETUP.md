# Namecheap DNS Setup for docs.cloudeval.ai

This guide provides step-by-step instructions for configuring DNS in Namecheap to use `docs.cloudeval.ai` with GitHub Pages.

## Prerequisites

- Domain `cloudeval.ai` registered with Namecheap
- GitHub repository with GitHub Pages enabled
- GitHub Pages base URL: `ganakailabs.github.io` (or your username/organization)

## Step-by-Step Namecheap DNS Configuration

### Step 1: Access Namecheap Domain List

1. Log in to your Namecheap account
2. Go to **Domain List** from the left sidebar
3. Click **Manage** next to `cloudeval.ai`

### Step 2: Navigate to Advanced DNS

1. Click on the **Advanced DNS** tab
2. You'll see a section called **Host Records**

### Step 3: Add CNAME Record

In the **Host Records** section, click **Add New Record** and configure:

**For the CNAME record:**

- **Type:** Select `CNAME Record` from the dropdown
- **Host:** Enter `docs`
- **Value:** Enter `ganakailabs.github.io` (replace with your GitHub username/organization if different)
- **TTL:** Select `Automatic` (or `30 min` if automatic is not available)

**Important Notes:**

- The **Host** field should be just `docs` (not `docs.cloudeval.ai`)
- The **Value** should be your GitHub Pages base URL: `ganakailabs.github.io` (without `https://` or trailing slashes)
- Do NOT include the repository path in the value

### Step 4: Save the Record

1. Click the **Save All Changes** button (green checkmark icon)
2. Wait for the confirmation message

### Step 5: Verify the Record

After saving, you should see a record like this in your Host Records:

```
Type: CNAME Record
Host: docs
Value: ganakailabs.github.io
TTL: Automatic
```

## Complete Configuration Summary

Here's what your Namecheap DNS should have for the main documentation:

| Type  | Host | Value                 | TTL       |
| ----- | ---- | --------------------- | --------- |
| CNAME | docs | ganakailabs.github.io | Automatic |

### Additional: Blog Subdomain (Optional)

If you want to set up `blog.cloudeval.ai` as a separate subdomain, add another CNAME record:

| Type  | Host | Value                 | TTL       |
| ----- | ---- | --------------------- | --------- |
| CNAME | blog | ganakailabs.github.io | Automatic |

**Note:** This requires a separate repository for the blog. See [BLOG_SUBDOMAIN_SETUP.md](BLOG_SUBDOMAIN_SETUP.md) for complete setup instructions.

## Next Steps (After DNS Configuration)

### 1. Configure GitHub Repository

1. Go to your GitHub repository: `https://github.com/ganakailabs/cloudeval`
2. Navigate to **Settings** → **Pages**
3. In the **Custom domain** field, enter: `docs.cloudeval.ai`
4. Click **Save**
5. Wait a few minutes, then check **Enforce HTTPS** and enable it

### 2. Verify CNAME File

The `docs/CNAME` file has been created in the repository. This file will be automatically deployed to the `gh-pages` branch by the GitHub Actions workflow.

The file contains:

```
docs.cloudeval.ai
```

### 3. Wait for DNS Propagation

- **Typical time:** 1-4 hours
- **Maximum time:** Up to 24-48 hours

You can check propagation status at:

- [whatsmydns.net](https://www.whatsmydns.net/#CNAME/docs.cloudeval.ai)
- Or use command line: `dig docs.cloudeval.ai CNAME`

### 4. Wait for SSL Certificate

After DNS propagates, GitHub will automatically provision an SSL certificate:

- Usually takes 10 minutes to 1 hour
- Check status in GitHub Settings → Pages → Custom domain
- Once ready, enable **Enforce HTTPS**

## Verification Commands

After configuring DNS, verify with these commands:

```bash
# Check CNAME record
dig docs.cloudeval.ai CNAME +short

# Expected output:
# ganakailabs.github.io.

# Check if domain resolves
nslookup docs.cloudeval.ai

# Or using dig
dig docs.cloudeval.ai
```

## Troubleshooting

### DNS Not Propagating

1. **Double-check the CNAME record:**

   - Host should be `docs` (not `docs.cloudeval.ai`)
   - Value should be `ganakailabs.github.io` (no `https://`, no trailing slash)

2. **Clear DNS cache:**

   ```bash
   # macOS
   sudo dscacheutil -flushcache; sudo killall -HUP mDNSResponder

   # Windows
   ipconfig /flushdns
   ```

3. **Wait longer:** DNS can take up to 48 hours to fully propagate

### GitHub Pages Not Recognizing Domain

1. Ensure the CNAME file exists in `gh-pages` branch root
2. Verify GitHub Settings → Pages shows the custom domain
3. Check for any error messages in GitHub Pages settings

### SSL Certificate Not Provisioning

1. Wait 24 hours after DNS propagation
2. Ensure DNS is correctly configured
3. Check GitHub Pages settings for error messages
4. Try removing and re-adding the custom domain in GitHub

## Common Namecheap Issues

### Issue: Can't find Advanced DNS tab

- Make sure you're on the domain management page
- Some domains might use Namecheap BasicDNS (free) - you may need to switch to PremiumDNS or use custom nameservers

### Issue: TTL options are limited

- Select the shortest available TTL (usually 30 min or 1 hour)
- This helps with faster propagation

### Issue: Record not saving

- Make sure there are no extra spaces in the Host or Value fields
- Ensure you're clicking "Save All Changes" (green checkmark)

## Expected Timeline

1. **DNS Configuration:** Immediate (after saving in Namecheap)
2. **DNS Propagation:** 1-4 hours (can take up to 48 hours)
3. **GitHub SSL Certificate:** 10 minutes to 1 hour after DNS propagates
4. **Total Setup Time:** Typically 2-6 hours, maximum 48 hours

## Final Checklist

- [ ] CNAME record added in Namecheap (Host: `docs`, Value: `ganakailabs.github.io`)
- [ ] Changes saved in Namecheap
- [ ] Custom domain configured in GitHub Settings → Pages
- [ ] CNAME file exists in repository (`docs/CNAME`)
- [ ] DNS propagated (verified with dig/nslookup)
- [ ] SSL certificate provisioned (check GitHub Pages settings)
- [ ] HTTPS enforced in GitHub Pages settings
- [ ] Site accessible at `https://docs.cloudeval.ai`

## Support

If you encounter issues:

- [Namecheap Support](https://www.namecheap.com/support/)
- [GitHub Pages Documentation](https://docs.github.com/pages)
- [GitHub Community Forum](https://github.community/)
