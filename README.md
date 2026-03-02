# protein-pricer-site
# Protein Pricer — Website

Landing page, privacy policy, terms of service, and email confirmation page for [proteinpricer.com](https://proteinpricer.com).

Hosted on GitHub Pages. Operated by Hira Kashta, LLC.

---

## Setup Checklist

### 1. Push these files to your `protein-pricer-site` repo
```bash
git add .
git commit -m "Add landing page, privacy policy, terms, and email confirmation"
git push origin main
```

### 2. Enable GitHub Pages
- Go to your repo → **Settings** → **Pages**
- Source: **Deploy from a branch**
- Branch: `main` / `/ (root)`
- Save

### 3. Configure custom domain in GitHub
- Still in **Settings** → **Pages**
- Custom domain: `proteinpricer.com`
- Check **Enforce HTTPS** (after DNS propagates)

### 4. Configure Namecheap DNS
Go to **Namecheap** → **Domain List** → `proteinpricer.com` → **Advanced DNS**

Delete any existing A records and CNAME records, then add:

| Type  | Host | Value                    |
|-------|------|--------------------------|
| A     | @    | 185.199.108.153          |
| A     | @    | 185.199.109.153          |
| A     | @    | 185.199.110.153          |
| A     | @    | 185.199.111.153          |
| CNAME | www  | `<your-github-username>.github.io` |

DNS propagation takes 5–30 minutes (sometimes up to 24 hours).

### 5. Set up email forwarding (optional but recommended)
In Namecheap → **Domain List** → `proteinpricer.com` → **Email Forwarding**:
- Add: `support@proteinpricer.com` → your inbox

### 6. Update Supabase settings
In **Supabase Dashboard** → **Authentication** → **URL Configuration**:
- **Site URL**: `https://proteinpricer.com`
- **Redirect URLs**: add `https://proteinpricer.com/confirm`

In **Supabase Dashboard** → **Authentication** → **Email Templates**:
- Update the **Confirm signup** template to use branded wording
- Update the **Change Email Address** template with branded wording
- Make sure the confirmation link points to `https://proteinpricer.com/confirm`

### 7. Re-enable email confirmation
In **Supabase Dashboard** → **Authentication** → **Providers** → **Email**:
- Enable **Confirm email**

---

## File Structure

```
index.html    — Landing page
privacy.html  — Privacy Policy
terms.html    — Terms of Service
confirm.html  — Email confirmation success page
CNAME         — GitHub Pages custom domain config
```

All pages are static HTML with no build step. Edit and push.
