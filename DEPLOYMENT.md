# GitHub Pages Deployment Guide

## Quick Start

1. **Push your code to GitHub:**
   ```bash
   git add .
   git commit -m "Initial commit for GitHub Pages"
   git push origin main
   ```

2. **Enable GitHub Pages:**
   - Go to your repository: https://github.com/ihsaland/KPI99
   - Click on **Settings**
   - Scroll down to **Pages** in the left sidebar
   - Under **Source**, select **GitHub Actions**
   - Save the settings

3. **Deploy:**
   - The GitHub Actions workflow will automatically run
   - Go to the **Actions** tab to see the deployment progress
   - Once complete, your site will be live at: `https://ihsaland.github.io/KPI99/`

## Files Included

- `.nojekyll` - Prevents Jekyll processing (required for static HTML)
- `.github/workflows/deploy.yml` - Automated deployment workflow
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
- **Deployment fails:** Check the Actions tab for error messages

