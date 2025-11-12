# Kerido Website

This is the official website for Kerido, hosted on GitHub Pages.

## Pages

- **Homepage** (`index.html`) - Main landing page
- **Privacy Policy** (`privacy-policy.pdf`) - Privacy policy for app store submissions
- **Terms of Service** (`terms-of-service.pdf`) - Terms of service for app store submissions
- **Request Data Deletion** (`request-deletion.html`) - Page for users to request data deletion

## Setting Up GitHub Pages

### 1. Create GitHub Repository

1. Go to GitHub and create a new repository named `kerido-website`
2. Make sure it's set to **Public** (required for free GitHub Pages)
3. Initialize it with a README (optional)

### 2. Push This Code to GitHub

```bash
# If you haven't already, initialize git
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: Kerido website"

# Add your GitHub repository as remote (replace YOUR_USERNAME)
git remote add origin https://github.com/YOUR_USERNAME/kerido-website.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repository on GitHub
2. Click on **Settings** tab
3. Scroll down to **Pages** section (in the left sidebar)
4. Under **Source**, select **Deploy from a branch**
5. Choose **main** branch and **/ (root)** folder
6. Click **Save**
7. Your site will be available at: `https://YOUR_USERNAME.github.io/kerido-website/`

## Connecting GoDaddy Domain to GitHub Pages

### Step 1: Configure GitHub Pages Custom Domain

1. In your GitHub repository, go to **Settings** → **Pages**
2. Under **Custom domain**, enter: `kerido.co`
3. Check **Enforce HTTPS** (this may take a few minutes to become available)
4. Click **Save**

### Step 2: Create CNAME File (Optional but Recommended)

Create a file named `CNAME` (no extension) in the root of your repository with just:
```
kerido.co
```

Then commit and push:
```bash
git add CNAME
git commit -m "Add CNAME for custom domain"
git push
```

### Step 3: Configure DNS in GoDaddy

1. Log in to your GoDaddy account
2. Go to **My Products** → **Domains** → Click **DNS** next to `kerido.co`
3. You'll need to add/update DNS records:

#### Option A: Using A Records (Recommended for root domain)
Add or update these A records (pointing to GitHub Pages IPs):
- **Type:** A
- **Name:** @ (or leave blank)
- **Value:** `185.199.108.153`
- **TTL:** 600

- **Type:** A
- **Name:** @ (or leave blank)
- **Value:** `185.199.109.153`
- **TTL:** 600

- **Type:** A
- **Name:** @ (or leave blank)
- **Value:** `185.199.110.153`
- **TTL:** 600

- **Type:** A
- **Name:** @ (or leave blank)
- **Value:** `185.199.111.153`
- **TTL:** 600

#### Option B: Using CNAME (For www subdomain)
If you want `www.kerido.co` to work:
- **Type:** CNAME
- **Name:** www
- **Value:** `YOUR_USERNAME.github.io`
- **TTL:** 600

### Step 4: Wait for DNS Propagation

- DNS changes can take 24-48 hours to propagate, though often it's much faster
- You can check propagation status using tools like [whatsmydns.net](https://www.whatsmydns.net)

### Step 5: Verify

Once DNS has propagated:
- Visit `https://kerido.co` - it should show your website
- The site should automatically redirect to HTTPS

## Important Notes

1. **Update Contact Information**: Make sure to replace `[Your Contact Email]` and `[Date]` placeholders in:
   - `privacy-policy.html`
   - `terms-of-service.html`
   - `request-deletion.html`

2. **Customize Content**: Review and customize the privacy policy and terms of service to match your app's actual data practices and legal requirements.

3. **HTTPS**: GitHub Pages automatically provides SSL certificates for custom domains. Make sure "Enforce HTTPS" is enabled in your repository settings.

4. **Testing**: After setup, test all pages:
   - `https://kerido.co`
   - `https://kerido.co/privacy-policy.html`
   - `https://kerido.co/terms-of-service.html`
   - `https://kerido.co/request-deletion.html`

## URLs for App Store Submissions

When submitting to Google Play and iOS App Store, you can use:
- **Privacy Policy:** `https://kerido.co/privacy-policy.html`
- **Terms of Service:** `https://kerido.co/terms-of-service.html`
- **Data Deletion:** `https://kerido.co/request-deletion.html`

## Troubleshooting

- **Domain not working?** Check DNS propagation and ensure you've added the CNAME file or A records correctly
- **HTTPS not working?** Wait a few hours after adding the custom domain, then enable "Enforce HTTPS"
- **404 errors?** Make sure your files are in the root directory and committed to the main branch

