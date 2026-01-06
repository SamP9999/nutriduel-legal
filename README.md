# NutriDuel Legal & Callback Pages

This folder contains static HTML pages for:
- Legal documents (Privacy Policy, Terms of Service)
- Email confirmation callback bridge page

## Deployment to Vercel

### Quick Deploy

1. **Install Vercel CLI** (if not already installed):
   ```bash
   npm i -g vercel
   ```

2. **Deploy from this folder**:
   ```bash
   cd nutriduel-legal
   vercel --prod
   ```

3. **Configure custom domain** (if using `nutriduel.app`):
   - Go to Vercel Dashboard → Your Project → Settings → Domains
   - Add `nutriduel.app` as a custom domain
   - Update DNS records as instructed by Vercel

### File Structure

```
nutriduel-legal/
├── index.html          # Legal docs index
├── privacy.html        # Privacy Policy
├── terms.html          # Terms of Service
├── auth/
│   └── callback.html  # Email confirmation callback bridge
└── vercel.json        # Vercel routing configuration
```

### URLs After Deployment

- **If using Vercel default domain:**
  - `https://nutriduel-legal.vercel.app/auth/callback`
  
- **If using custom domain `nutriduel.app`:**
  - `https://nutriduel.app/auth/callback`

### Testing

After deployment, test the callback page:
```
https://[your-domain]/auth/callback?code=test123&type=signup
```

You should see the "Email Confirmed" page with "Open NutriDuel" button.

### Update Supabase Redirect URLs

After deployment, add the callback URL to Supabase:
- Go to Supabase Dashboard → Authentication → URL Configuration
- Add to Redirect URLs: `https://nutriduel.app/auth/callback` (or your Vercel domain)

