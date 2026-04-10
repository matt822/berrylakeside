# Deploy to GitHub Pages with Custom Domain

## Step 1 — Enable GitHub Pages

1. Go to your repo on GitHub
2. Click **Settings** > **Pages** (in the left sidebar)
3. Under **Source**, select **Deploy from a branch**
4. Set branch to `main`, folder to `/ (root)`
5. Click **Save**

## Step 2 — CNAME File

A `CNAME` file already exists in this repo containing:

```
www.berrylakeside.com
```

This tells GitHub Pages which custom domain to use.

## Step 3 — Configure DNS on Squarespace

In your Squarespace domain DNS settings, add these records:

**For `www` subdomain (CNAME record):**

| Type  | Host | Value                  |
|-------|------|------------------------|
| CNAME | www  | `matt822.github.io`    |

**For apex domain (A records, if you also want `berrylakeside.com` without www):**

| Type | Host | Value           |
|------|------|-----------------|
| A    | @    | `185.199.108.153` |
| A    | @    | `185.199.109.153` |
| A    | @    | `185.199.110.153` |
| A    | @    | `185.199.111.153` |

## Step 4 — Set Custom Domain in GitHub Pages Settings

1. Back in **Settings > Pages**, under **Custom domain**, enter `www.berrylakeside.com`
2. Click **Save**
3. Check **Enforce HTTPS** once available (may take a few minutes after DNS propagates)

## Notes

- DNS propagation can take a few minutes to 24 hours
- HTTPS enforcement becomes available once GitHub verifies the domain
