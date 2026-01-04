# GitHub Pages Deployment Guide

## Option 1: Deploy from Branch (Recommended if GitHub Actions not available)

1. **Go to repository settings:**
   - Navigate to: https://github.com/ihsaland/KPI99/settings/pages

2. **Configure Pages:**
   - Under **Source**, select **Deploy from a branch**
   - Choose **Branch:** `main`
   - Choose **Folder:** `/ (root)`
   - Click **Save**

3. **Your site will be live at:**
   - `https://kpi99.co/`

## Option 2: GitHub Actions (If available)

If GitHub Actions appears as an option:

1. Go to repository settings
2. Navigate to **Pages**
3. Under **Source**, select **GitHub Actions**
4. The workflow will automatically deploy on push

## Files Included

- `.nojekyll` - Prevents Jekyll processing (required for static HTML)
- `.github/workflows/deploy.yml` - Automated deployment workflow (if using Actions)
- `index.html` - Main website file
- `panAbstract.png` - Header background image

## Custom Domain Setup

The site is configured to use the custom domain `kpi99.co`:

1. **CNAME file:** Already created in the repository root with `kpi99.co`
2. **DNS Configuration:** Configure your DNS settings with your domain provider:
   - Add a CNAME record pointing `kpi99.co` to `ihsaland.github.io`
   - Or add A records pointing to GitHub Pages IP addresses:
     - 185.199.108.153
     - 185.199.109.153
     - 185.199.110.153
     - 185.199.111.153
3. **GitHub Pages Settings:** 
   - Go to repository settings → Pages
   - The custom domain should appear automatically
   - Enable "Enforce HTTPS" once DNS propagates (may take up to 24 hours)
   - GitHub Pages automatically provides SSL/TLS certificates via Let's Encrypt

## HTTPS Configuration

The site is fully configured for HTTPS:

1. **Security Headers:** Added to `index.html`:
   - `Content-Security-Policy: upgrade-insecure-requests` - Automatically upgrades HTTP requests to HTTPS
   - `Referrer-Policy: strict-origin-when-cross-origin` - Secure referrer handling
   - Canonical URL with HTTPS

2. **External Resources:** All external resources use HTTPS:
   - Google Fonts (HTTPS)
   - Google Analytics (HTTPS)
   - WhatsApp links (HTTPS)

3. **GitHub Pages HTTPS:**
   - Once DNS is configured and domain is verified, GitHub Pages automatically enables HTTPS
   - SSL certificate is provided and renewed automatically
   - "Enforce HTTPS" option will appear in Pages settings after domain verification
   - All HTTP traffic will be automatically redirected to HTTPS

## Troubleshooting

- **Images not loading:** Ensure image files are in the same directory as `index.html`
- **404 errors:** Make sure `.nojekyll` file exists in the root
- **Deployment fails:** Check the Actions tab for error messages (if using Actions)
- **GitHub Actions not showing:** Use "Deploy from a branch" method instead
