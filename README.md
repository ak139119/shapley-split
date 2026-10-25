# Shapley Split

A one-page web app for splitting founder equity fairly with Shapley values. Each founder privately scores their teammates' solo value and the synergies between them. The app averages the scores, flags disagreements and computes the split. It works for teams of any size.

Built for **Business Modeling · Session 5: Team Architecture & Agentic AI Workflows**. It opens on the LoopBox example from the course video.

- **One file:** `index.html`. No build step, no server, no database.
- **Private by design:** scores stay in each student's browser and leave it only as a "score code" the student chooses to send.

---

## Publish it on GitHub Pages (about 10 minutes, no coding)

### 1. Create a repository
1. Sign in at [github.com](https://github.com), or create a free account.
2. Click **+** (top right) → **New repository**.
3. **Repository name:** `shapley-split`. This becomes part of the web address.
4. Choose **Public**. GitHub Pages is free for public repositories; private ones need a paid plan. The file contains no student or personal data.
5. Click **Create repository**.

### 2. Upload the files
1. On the new repository page, click **uploading an existing file**, or use **Add file → Upload files**.
2. Drag in `index.html` and this `README.md`. Keep the name `index.html` exactly.
3. Click **Commit changes**.

### 3. Turn on GitHub Pages
1. Open the repository's **Settings** tab → **Pages** (left sidebar).
2. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
3. Set **Branch** to `main` and the folder to `/ (root)`, then click **Save**.
4. Wait one to two minutes and refresh the page. The address appears at the top:
   `https://YOUR-USERNAME.github.io/shapley-split/`

### 4. Check it works
Open the address. The page should load the LoopBox example with Alex 28.8%, Sam 27.0%, Jordan 14.4%, Casey 11.7%, Taylor 8.1% and a 10% pool. The **Computation check** panel should say **Verified**.

---

## Link it from Moodle
1. In your course, turn editing on → **Add an activity or resource** → **URL**.
2. Paste the GitHub Pages address.
3. Under **Appearance → Display**, choose **New window**. The copy buttons work more reliably outside an embedded frame.

You can also link straight to a step by adding it to the end of the address:
- `…/shapley-split/#setup` opens **Set up the team**.
- `#score`, `#combine`, `#results` and `#method` open the other tabs.

## How students use it in class
1. **Facilitator** (one per team): clicks **Start a new team** → **Set up the team**, adds the people and synergies, then copies the **setup code** to the team chat.
2. **Each founder**: opens the link → **Score privately** → pastes the setup code → chooses their name → scores alone → **Create my score code** → sends it to the facilitator.
3. **Facilitator**: **Combine scores** → pastes all the score codes → **Results**. Discuss the flagged disagreements before agreeing the split.

Codes are plain text, so any channel works: email, Teams, WhatsApp or the Moodle forum. If the facilitator changes the people or the synergies after scoring has started, the old score codes no longer match. Re-send the setup code and score again.

## Updating the app
Upload a new `index.html` with the same name (**Add file → Upload files** → **Commit changes**). The site updates within a couple of minutes. If you still see the old version, refresh with **Ctrl+Shift+R** (or **⌘+Shift+R** on a Mac).

## Optional: your own domain
In **Settings → Pages → Custom domain**, enter something like `shapley.yourdomain.com` and save. At your domain provider, add a **CNAME** record pointing that name to `YOUR-USERNAME.github.io`. When the check passes, tick **Enforce HTTPS**.

## Privacy notes
- **No accounts, no tracking, no server-side storage.** The team setup and scores are saved only in the browser's local storage on each device. Clearing browser data removes them, so students should keep their codes.
- **Fonts.** The page loads its fonts from Google Fonts (`fonts.googleapis.com`), which shares the visitor's IP address with Google. If your institution's data-protection policy requires it, the fonts can be bundled into the repository instead, or the page can fall back to system fonts with no external requests.
- **Not legal advice.** The output is a structured starting point for a founders' conversation, not a legal allocation. Agree vesting, and have a lawyer draft the shareholders' agreement.
