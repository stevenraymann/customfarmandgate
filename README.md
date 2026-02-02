# Custom Farm and Gate Website

Professional website for Custom Farm and Gate - a custom farm equipment and gate fabrication company based in Citronelle, Alabama.

## Features

- Responsive design optimized for mobile and desktop
- SEO-optimized with sitemap and meta tags
- Traditional Southern aesthetic appealing to farming community
- Click-to-call phone integration
- Progressive Web App (PWA) support
- Azure/IIS ready with web.config

## Files Included

- `customfarmandgate.html` - Main website file (rename to `index.html` for deployment)
- `robots.txt` - Search engine crawler instructions
- `sitemap.xml` - SEO sitemap
- `site.webmanifest` - PWA manifest for mobile devices
- `favicon.svg` - Scalable vector icon
- `web.config` - Azure/IIS configuration
- `.htaccess` - Apache server configuration (alternative)
- `404.html` - Custom error page

## Deployment to Azure

### Option 1: Azure App Service (Recommended)

1. **Rename the main file:**
   ```bash
   mv customfarmandgate.html index.html
   ```

2. **Create Azure App Service:**
   - Log into Azure Portal
   - Create a new App Service (Linux or Windows)
   - Choose "Code" deployment
   - Select runtime: Node.js, .NET, or Static Web App

3. **Deploy via Azure CLI:**
   ```bash
   az webapp up --name customfarmandgate --resource-group YourResourceGroup
   ```

4. **Or deploy via Git:**
   ```bash
   git init
   git add .
   git commit -m "Initial commit"
   az webapp deployment source config-local-git --name customfarmandgate --resource-group YourResourceGroup
   git remote add azure <deployment_url>
   git push azure main
   ```

### Option 2: Azure Static Web Apps

1. **Rename the main file:**
   ```bash
   mv customfarmandgate.html index.html
   ```

2. **Create Static Web App:**
   - Go to Azure Portal → Create Resource → Static Web App
   - Connect to your GitHub repo or upload files directly
   - Build settings: Skip (static HTML)
   - App location: `/`

3. **Deploy:**
   - Push to GitHub, or
   - Use Azure CLI: `az staticwebapp create`

### Option 3: Azure Blob Storage (Budget Option)

1. Create a Storage Account with static website hosting enabled
2. Upload all files to the `$web` container
3. Rename `customfarmandgate.html` to `index.html`
4. Configure custom domain if needed

## Post-Deployment Steps

1. **Update sitemap.xml:**
   - Replace `https://customfarmandgate.com/` with your actual domain

2. **Configure Custom Domain:**
   - Add your domain in Azure
   - Update DNS records (A record or CNAME)
   - Enable HTTPS/SSL certificate (free with Azure)

3. **Test:**
   - Verify all pages load correctly
   - Test mobile responsiveness
   - Check phone click-to-call functionality
   - Validate sitemap at `yourdomain.com/sitemap.xml`

4. **SEO Setup:**
   - Submit sitemap to Google Search Console
   - Submit sitemap to Bing Webmaster Tools
   - Verify robots.txt is accessible

5. **Optional - Add Icons:**
   - Create `icon-192.png` and `icon-512.png` for PWA support
   - Or convert `favicon.svg` to PNG at those sizes

## File Structure for Deployment

```
/
├── index.html (renamed from customfarmandgate.html)
├── robots.txt
├── sitemap.xml
├── site.webmanifest
├── favicon.svg
├── web.config (for Azure/IIS)
├── 404.html
└── (optional) icon-192.png, icon-512.png
```

## Environment Variables (if using App Service)

No environment variables required for this static site.

## Custom Domain Setup

1. In Azure Portal, go to your App Service or Static Web App
2. Navigate to "Custom domains"
3. Click "Add custom domain"
4. Follow instructions to verify domain ownership
5. Add DNS records as specified
6. Enable SSL/TLS certificate (free with Azure)

## Performance Optimization

The site includes:
- Compressed assets via web.config
- Browser caching headers
- Minimal external dependencies
- Optimized images (inline SVG)

## Security Features

- HTTPS redirect enabled in web.config
- Security headers (X-Frame-Options, X-Content-Type-Options, etc.)
- No external scripts or dependencies
- Input validation on phone links

## Support

For website issues, contact your web developer.
For business inquiries: **251-485-5686**

## License

© 2025 Custom Farm and Gate. All rights reserved.
