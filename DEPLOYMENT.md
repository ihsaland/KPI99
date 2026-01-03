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
   - `https://ihsaland.github.io/KPI99/`

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

## Custom Domain (Optional)

If you want to use a custom domain:

1. Add a `CNAME` file in the root with your domain name
2. Configure DNS settings with your domain provider
3. Update the domain in GitHub Pages settings

## Troubleshooting

- **Images not loading:** Ensure image files are in the same directory as `index.html`
- **404 errors:** Make sure `.nojekyll` file exists in the root
- **Deployment fails:** Check the Actions tab for error messages (if using Actions)
- **GitHub Actions not showing:** Use "Deploy from a branch" method instead
