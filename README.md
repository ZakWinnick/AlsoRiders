# Also Riders Club

The website for Also Riders Club — an independent owners' community for the ALSO TM-B and TM-Q.

Built with [Jekyll](https://jekyllrb.com/), hosted on [GitHub Pages](https://pages.github.com/), membership powered by [Heylo](https://heylo.com/).

---

## Quick setup (10 minutes)

### 1. Create the GitHub repo

```bash
# In this folder
git init
git add .
git commit -m "Initial commit: Also Riders Club website"

# Create a new repo on github.com (e.g. alsoridersclub/alsoridersclub.github.io
# or your-org/website), then:
git branch -M main
git remote add origin git@github.com:YOUR_ORG/YOUR_REPO.git
git push -u origin main
```

### 2. Turn on GitHub Pages

In the repo on GitHub:

1. **Settings → Pages**
2. **Source**: Deploy from a branch
3. **Branch**: `main` / `(root)`
4. Save.

GitHub will give you a URL like `https://YOUR_ORG.github.io/YOUR_REPO/`. The site will build in about a minute.

### 3. Hook up a custom domain

1. Buy a domain (suggested: `alsoridersclub.org`, `alsoridersclub.com`, or `alsoriders.club`).
2. Create a file at the repo root named **`CNAME`** containing just your domain on one line. Example:
   ```
   alsoridersclub.org
   ```
3. In your domain registrar's DNS settings, add:

   **For an apex domain** (e.g. `alsoridersclub.org`) — four A records:
   ```
   A    @    185.199.108.153
   A    @    185.199.109.153
   A    @    185.199.110.153
   A    @    185.199.111.153
   ```
   **For www** — one CNAME:
   ```
   CNAME    www    YOUR_ORG.github.io
   ```

4. Back in **Settings → Pages**, enter the custom domain and check **Enforce HTTPS** (after the cert provisions, usually within an hour).

### 4. Update `_config.yml`

Open `_config.yml` and replace:

- `url:` → your custom domain
- `heylo_url:` → your real Heylo group link (created in step 5)
- `social:` → your real handles when they exist
- `contact_email:` → a real email address

Commit and push. GitHub Pages rebuilds automatically.

### 5. Create the Heylo group

1. Sign up at [heylo.com](https://www.heylo.com/) and create a new group.
2. Group name: **Also Riders Club**.
3. Set the custom URL to `alsoriders` so your join link is `heylo.group/alsoriders` (or whatever's available).
4. Upload a cover image, write a welcome message, and create a couple of starter chats (`#welcome`, `#general`, `#tech-and-firmware`, `#regions`).
5. Set the group to **Public** so events can be embedded later via Heylo Pro.

Drop the final Heylo URL into `_config.yml` and push.

---

## Editing content

### Adding events (static, free Heylo tier)

Edit `_data/events.yml`:

```yaml
events:
  - date: "Jun 8"
    title: "First Ride — Bay Area Kickoff"
    location: "Crissy Field, San Francisco, CA"
    region: "NorCal"
    url: "https://heylo.group/alsoriders/event/abc123"
  - date: "Jun 22"
    title: "Saturday Coffee Meetup"
    location: "Blue Bottle, Palo Alto, CA"
    region: "NorCal"
```

Commit and push — the homepage and events page update automatically.

### Heylo live event embed

The site uses Heylo's live event feed in `_includes/heylo-events.html`.
The homepage and `/events/` page include that shared snippet, so updating the
API key or community ID there updates both surfaces.

If you ever need to return to a static fallback, use `_data/events.yml` as the
source of truth and replace the include in `index.html` and `events.md`.

### Editing pages

- `index.html` — homepage
- `about.md` — About page
- `join.md` — Join page
- `events.md` — Events page
- `_includes/header.html`, `_includes/footer.html` — nav and footer
- `assets/css/main.css` — all styles

Markdown files use [front matter](https://jekyllrb.com/docs/front-matter/) at the top to set title, lede, etc.

---

## Local development (optional)

If you want to preview changes locally before pushing:

```bash
# Install Ruby (3.1+ recommended) and Bundler, then:
bundle install
bundle exec jekyll serve

# Open http://localhost:4000
```

If you're not comfortable with Ruby, **skip this entirely** — just edit files and push to GitHub. The live site rebuilds in ~1 minute.

---

## Design system

- **Typography**: Archivo for display/body and IBM Plex Mono for nav, labels, and controls.
- **Color**: industrial graphite (`#17171b`), black (`#060608`), warm paper (`#ebe4d7`), warm white (`#fffaf1`), with purple and signal-yellow accents.
- **Theme**: light/dark mode follows the visitor's system setting via `prefers-color-scheme`.
- **Visual language**: graphite technical field, measurement lines, stamped panels, oval CTAs, and the ARC logo as the main brand asset.
- **Tokens**: all colors and fonts in `:root` CSS variables in `assets/css/main.css`. Change one, change everywhere.

---

## License & trademarks

Site code is free for the club to use and adapt.

Also Riders Club is independent and not affiliated with ALSO, Inc. ALSO™, TM-B™, TM-Q™ and related marks belong to their respective owners.
