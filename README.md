# helpermate.app — Firebase Hosting

HelperMate marketing site + blog CMS, hosted on Firebase Hosting.

## Structure

```
.
├── firebase.json              # Hosting config (cleanUrls, headers, rewrites)
├── .firebaserc                # Firebase project link (helpermate-5637b)
├── index.html                 # Landing page
├── privacy.html               # Privacy Policy
├── terms.html                 # Terms of Service
├── subscription.html          # Subscription Policy
├── images/                    # Static assets
└── blog/
    ├── index.html             # Blog list (Firestore-driven)
    ├── post.html              # Individual post page
    └── admin/
        └── index.html         # Admin editor (Auth-protected)
```

## Local development

```bash
# Install Firebase CLI globally if not already
npm install -g firebase-tools

# Login (first time only)
firebase login

# Serve locally
firebase serve --only hosting
# → http://localhost:5000
```

## Deploy

```bash
firebase deploy --only hosting
```

## Custom domain

helpermate.app is configured via Firebase Hosting → Add custom domain.
DNS managed at Cloudflare → A record points to Firebase Hosting IPs.

## Blog CMS

Posts are stored in Firestore (`blog_posts` collection).
Admin access controlled via Firebase Auth + custom claims (admin: true).
See `blog/admin/index.html` for the editor.
