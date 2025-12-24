# Netlify Environment Variables Setup

## How to Set Environment Variables in Netlify

1. Go to your Netlify Dashboard
2. Select your site
3. Go to **Site settings** → **Environment variables**
4. Click **Add variable**
5. Add each variable below

## Required Variables

### API Configuration
```
VITE_API_URL=
```
**Description:** Your Node.js API URL (if deployed separately). Leave empty to use same domain as frontend.

**Example:** `https://your-api.netlify.app/api` or `https://api.yourdomain.com`

---

### Firebase Configuration (if using Firebase)
```
VITE_FIREBASE_API_KEY=your-api-key
VITE_FIREBASE_AUTH_DOMAIN=your-project.firebaseapp.com
VITE_FIREBASE_PROJECT_ID=your-project-id
VITE_FIREBASE_STORAGE_BUCKET=your-project.appspot.com
VITE_FIREBASE_MESSAGING_SENDER_ID=123456789
VITE_FIREBASE_APP_ID=1:123456789:web:abcdef
```

---

### Supabase Configuration (if using Supabase)
```
VITE_SUPABASE_URL=https://your-project.supabase.co
VITE_SUPABASE_ANON_KEY=your-anon-key
```

---

## Current Configuration

Based on your code, you're using:
- ✅ **PostgreSQL** (via Node.js API)
- ❌ Firebase (not active)
- ❌ Supabase (not active)

## Minimum Required Variables

For your current setup, you only need:
```
VITE_API_URL=https://your-api-url.com/api
```

Or leave it empty to use the same domain as your frontend.

---

## Local Development

For local development, create a `.env.local` file in the root directory:

```env
VITE_API_URL=http://localhost:3000/api
```

**Note:** `.env.local` should be in `.gitignore` (never commit secrets!)

---

## After Setting Variables

1. **Redeploy** your site in Netlify
2. Variables are available at build time
3. Check build logs to verify variables are loaded

