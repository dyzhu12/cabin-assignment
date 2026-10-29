# Wedding Cabin Planner

A single-page app for deciding which wedding guests sleep in which cabin or room. Add your rooms with their bed and pull-out couch counts, paste in your guest list, then drag guests (or whole families) into rooms. The page tracks open spots and flags rooms that are over capacity.

Everything is in one file, `index.html`. There is no build step and nothing to install.

## Run it locally

Open `index.html` in any modern browser. Double-clicking the file works.

If you'd rather serve it, any static file server is fine, for example:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Host it on GitHub Pages

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. After a minute the site is live at `https://<your-username>.github.io/<repo-name>/`.

Pages on a **private** repo requires a paid GitHub plan (Pro, Team or Enterprise). On a free account the repo has to be public to use Pages. A public Pages site can be opened by anyone who has the link, but your guest list isn't included: the data lives in each visitor's own browser (see below).

## Where your data is saved

Every change is saved automatically to your browser's IndexedDB storage, so the plan is still there when you close the tab or restart. It's saved only on the device and browser you used, and isn't shared with anyone else, even on a hosted copy.

The page also asks the browser to keep its data even when disk space runs low. Browsers decide on their own whether to agree (Chrome usually does for sites you visit often or bookmark), so keep backups anyway.

Plans saved by an earlier version of this page (which used local storage) are moved into IndexedDB the first time you open the new version.

- To move a plan to another device or share it with your partner, use **Backup**: copy the text, then on the other device open the page, choose **Backup**, paste the text over what's there and press **Restore**.
- Clearing your browser's site data erases the plan, so take a backup now and then.

## Starting data

The page comes with the venue's rooms already filled in. The guest list is deliberately not in the code, so the repo can be public without exposing anyone's name. Add guests with **Edit guest list**, or load a saved plan with **Backup → Restore**.

## How to use it

- **Edit guest list:** paste guests one per line. Add a group name after a comma to keep people together, like `Maya Chen, Chen family`.
- **Add room:** cabin name, room name, number of beds and number of pull-out couches.
- **Capacity rules:** each bed and each pull-out sleeps 2 by default; change either number at the top of the page.
- **Assign:** drag a guest onto a room, or tap a guest and then tap a room on a phone. Drag a group's name to move the whole group.
- **Unassign:** press × on a guest in a room, or drag them back to "Still need a bed".
- **Copy room list:** copies a plain-text list of who's in each room.
