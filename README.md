# Jasper in Belize — Trip Site

Live GPS tracking + daily photo log. Built for GitHub Pages.

---

## One-Time Setup (10 minutes)

### 1. Create the GitHub repo

1. Go to [github.com/new](https://github.com/new)
2. Name it something like `belize-trip`
3. Set it to **Public**
4. **Do not** initialize with README (you'll push these files)

### 2. Upload these files

```bash
cd belize-trip
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/belize-trip.git
git push -u origin main
```

### 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under "Source", select **Deploy from a branch**
3. Branch: `main` / folder: `/ (root)`
4. Save. Your site will be live at:
   `https://YOUR_USERNAME.github.io/belize-trip/`

### 4. Edit `index.html` — add your GitHub info

Open `index.html` and find this block near the bottom:

```javascript
const CONFIG = {
  githubUsername: 'GITHUB_USERNAME_HERE',  // ← your username
  githubRepo:     'REPO_NAME_HERE',         // ← e.g. belize-trip
};
```

Replace with your actual username and repo name, then push again:

```bash
git add index.html
git commit -m "Add GitHub config"
git push
```

---

## Posting from the Field (admin.html)

Open `https://YOUR_USERNAME.github.io/belize-trip/admin.html` on your phone.

**First visit — GitHub setup:**
1. Enter your GitHub username
2. Enter your repo name
3. Paste your Personal Access Token (see below)
4. Tap Save — credentials are stored locally on your device

**Every post:**
1. Select the day
2. Add photos (tap or drag)
3. Write your field notes
4. Tap **Post** — live in ~60 seconds

### Creating a GitHub Personal Access Token

1. Go to github.com → **Settings** → **Developer Settings** → **Personal access tokens** → **Fine-grained tokens**
2. Click **Generate new token**
3. Name: `belize-trip-admin`
4. Expiration: `30 days` (covers the trip + buffer)
5. Repository access: **Only select repositories** → choose `belize-trip`
6. Permissions → **Repository permissions** → **Contents**: `Read and Write`
7. Generate and copy the token — paste it into admin.html on first launch

---

## File Structure

```
belize-trip/
├── index.html      ← public site
├── admin.html      ← posting interface (bookmark on phone)
├── posts.json      ← auto-updated by admin panel
├── photos/         ← auto-created when you post
└── README.md
```

---

## Sharing

Send friends the public URL:
`https://YOUR_USERNAME.github.io/belize-trip/`

The admin panel at `/admin.html` is unlisted but not password-protected — don't share that link.

---

## Notes

- Photos are stored directly in the GitHub repo (free, no third-party services)
- GitHub Pages updates within ~60 seconds of a post
- The Garmin MapShare iframe updates in real-time based on your inReach ping interval
- Up to 4 photos per post; re-posting the same day merges photos and updates the caption
