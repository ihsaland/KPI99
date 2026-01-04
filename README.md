# KPI99

Enterprise Performance & Capacity Engineering Services website.

## About

KPI99 provides enterprise performance and capacity engineering services, focusing on predictive and preventative approaches to system optimization.

## GitHub Pages Deployment

This site is configured to deploy automatically to GitHub Pages when changes are pushed to the `main` branch.

### Manual Setup

1. Go to your repository settings on GitHub
2. Navigate to **Pages** in the left sidebar
3. Under **Source**, select **GitHub Actions**
4. The site will be available at: `https://kpi99.co/`

### Local Development

Simply open `index.html` in your browser or use a local server:

```bash
# Using Python
python -m http.server 8000

# Using Node.js (http-server)
npx http-server

# Using PHP
php -S localhost:8000
```

Then visit `http://localhost:8000` in your browser.

## Files

- `index.html` - Main website file
- `panAbstract.png` - Header background image
- `.nojekyll` - Prevents Jekyll processing
- `.github/workflows/deploy.yml` - GitHub Actions deployment workflow

## License

MIT License
