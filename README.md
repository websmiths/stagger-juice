# Stagger Juice EPK

A single self-contained HTML page. Images and styles are embedded, so there are no
other files to upload and nothing to build.

- `index.html` — the press kit
- `.nojekyll` — tells GitHub Pages to serve the file as-is instead of running Jekyll over it

## Publishing to GitHub Pages

### Option A — no terminal

1. Go to <https://github.com/new>. Name the repo `staggerjuice`. Public. Create it.
2. On the empty repo page, click **uploading an existing file**.
3. Drag in `index.html` and `.nojekyll`, then **Commit changes**.
4. **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**,
   branch **main**, folder **/ (root)**. Save.
5. Wait a minute or two. The page appears at:

       https://YOUR-USERNAME.github.io/staggerjuice/

### Option B — terminal

From this folder:

    git init -b main
    git add .
    git commit -m "Stagger Juice EPK"
    git remote add origin https://github.com/YOUR-USERNAME/staggerjuice.git
    git push -u origin main

Then do step 4 above to switch Pages on.

## Updating it later

Replace `index.html` and commit again — or drag the new file into the repo on
github.com and commit. Pages redeploys within a minute or two.

## Using your own domain

If you'd rather the link read `staggerjuice.com` than `github.io`:

1. Add a file named `CNAME` to the repo containing just your domain, e.g. `staggerjuice.com`
2. At your domain registrar, add these DNS records:

   | Type  | Name | Value                                                    |
   |-------|------|----------------------------------------------------------|
   | A     | @    | 185.199.108.153                                          |
   | A     | @    | 185.199.109.153                                          |
   | A     | @    | 185.199.110.153                                          |
   | A     | @    | 185.199.111.153                                          |
   | CNAME | www  | YOUR-USERNAME.github.io                                  |

3. In **Settings → Pages**, enter the domain under *Custom domain*, then tick
   **Enforce HTTPS** once the certificate has been issued.

Check the current GitHub Pages IPs at
<https://docs.github.com/pages/configuring-a-custom-domain-for-your-github-pages-site>
before relying on the table above — they change occasionally.

## One thing to test after publishing

Click a track title. The video should open inline. If you get a short message in the
frame instead of a player, the host is blocking third-party embeds — the
"Open on YouTube" link below each player still works, but tell Claude and the section
can be switched to click-through thumbnails.
