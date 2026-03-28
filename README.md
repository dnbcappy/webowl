# WebOwl — Business Website

Professional website for WebOwl, built with vanilla HTML/CSS/JS. Hosted on Firebase.

## Project Structure

```
webowl/
├── public/              ← Firebase serves this folder
│   ├── index.html       ← Main website
│   ├── 404.html         ← Custom 404 page
│   └── assets/          ← Images, favicons, etc.
├── firebase.json        ← Firebase Hosting config
├── .firebaserc          ← Firebase project link
└── .gitignore
```

## Setup (First Time)

### 1. Create Firebase Project
- Go to [Firebase Console](https://console.firebase.google.com)
- Click **Add project** → name it `webowl-site` (or whatever you like)
- Skip Google Analytics (optional)

### 2. Update `.firebaserc`
Replace the project ID with your actual Firebase project ID:
```json
{
  "projects": {
    "default": "your-actual-project-id"
  }
}
```

### 3. Login & Init (in VS Code terminal)
```bash
# Login to Firebase (one-time)
firebase login

# Verify project is linked
firebase projects:list
```

### 4. Create GitHub Repo
```bash
git init
git add .
git commit -m "Initial commit — WebOwl site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/webowl.git
git push -u origin main
```

## Daily Workflow

### Making changes
1. Open project in VS Code
2. Edit files in `public/`
3. Preview locally:
   ```bash
   firebase serve
   ```
   → Opens at `http://localhost:5000`

### Deploying
```bash
# Stage, commit, push to GitHub
git add .
git commit -m "Update: description of changes"
git push

# Deploy to Firebase
firebase deploy
```

Your site will be live at: `https://your-project-id.web.app`

### Custom Domain (optional)
1. Firebase Console → Hosting → Add custom domain
2. Add the DNS records Firebase gives you to your domain registrar
3. Wait for SSL provisioning (usually < 24 hours)

## Tips
- **Preview before deploy**: Always run `firebase serve` first
- **Rollback**: Firebase Console → Hosting → Release history → Roll back
- **Multiple environments**: Use `firebase use` to switch between staging/production
