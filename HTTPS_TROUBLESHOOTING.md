# HTTPS Troubleshooting Guide

If your site shows as "not secure" even though it's using HTTPS, check the following:

## 1. GitHub Pages HTTPS Settings

1. Go to your repository: https://github.com/ihsaland/KPI99/settings/pages
2. Scroll down to the "Custom domain" section
3. Ensure **"Enforce HTTPS"** is checked/enabled
4. If it's grayed out, wait 24-48 hours for DNS to fully propagate and SSL certificate to be issued

## 2. DNS Configuration

Verify your DNS is correctly configured:

**Option A - CNAME (Recommended):**
- Type: CNAME
- Name: @ or kpi99.co
- Value: ihsaland.github.io

**Option B - A Records:**
- Type: A
- Name: @ or kpi99.co
- Values:
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153

## 3. SSL Certificate Status

GitHub Pages automatically provisions SSL certificates via Let's Encrypt. This can take:
- 24-48 hours after DNS is configured
- Up to 72 hours in some cases

Check certificate status:
- Visit: https://www.ssllabs.com/ssltest/analyze.html?d=kpi99.co
- Look for a valid certificate

## 4. Browser Cache

Clear your browser cache or try:
- Incognito/Private mode
- Different browser
- Hard refresh: Ctrl+F5 (Windows) or Cmd+Shift+R (Mac)

## 5. Mixed Content

The site is configured to:
- Upgrade all HTTP requests to HTTPS
- Use strict transport security (HSTS)
- Only load resources from secure sources

## 6. Force HTTPS Redirect

If HTTP is still accessible, add this to your `.htaccess` (if using Apache) or ensure GitHub Pages redirects are working.

## Common Issues

- **"Enforce HTTPS" not available**: DNS hasn't fully propagated yet
- **Certificate not trusted**: Wait for Let's Encrypt certificate issuance
- **Mixed content warnings**: All resources should be HTTPS (already configured)
- **Redirect loops**: Check CNAME file is correct

## Verification

Once HTTPS is properly configured, you should see:
- Green padlock in browser address bar
- "Secure" or "Connection is secure" message
- Valid SSL certificate in browser developer tools

