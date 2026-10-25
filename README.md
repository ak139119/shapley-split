# Shapley Split (live)

Split founder equity fairly with Shapley values, scored by the whole team in real time.

- **Facilitator:** creates the team, lists the founders and their synergies, and shares one team link.
- **Each founder:** opens the link on their own device, chooses their name and scores **in private**.
- **Sealed scores:** nobody, the facilitator included, can see anyone's numbers until the facilitator clicks **Reveal all scores**. The database enforces this, not just the screen.
- **After the reveal:** everyone sees the split, a breakdown of each share, the items where scorers disagreed most, and each scorer's own implied split. The facilitator can **reopen scoring** for a second round after the discussion.
- **Teams of any size:** the app uses the exact Shapley shortcut. For teams of up to 14 it also checks the result against the full textbook formula.

It opens with the **LoopBox example** from the course video (Alex 28.8%, Sam 27.0%, Jordan 14.4%, Casey 11.7%, Taylor 8.1%, pool 10%).

**Files**
- `index.html`: the whole app.
- `firestore.rules`: database rules for **both** this app and the Negotiation Planner.
- `README.md`: these notes.

---

## Without setup
Opened as it is, the app runs in **This device only** mode. Founders take turns on one laptop, and each person's numbers disappear as soon as they submit. This is fine for a small group around one table.

## Live mode: if you already set up the Negotiation Planner
You can use the same Firebase project.
1. Open `index.html` in a text editor and paste the **same four values** (`apiKey`, `authDomain`, `projectId`, `appId`) into the `window.FIREBASE_CONFIG` block near the top.
2. In Firebase, go to **Firestore Database → Rules**. Replace everything with the contents of this folder's `firestore.rules` and click **Publish**. This file covers both apps, so the Negotiation Planner keeps working.
3. Publish on GitHub Pages in a new repository, for example `shapley-split`: upload the three files, then **Settings → Pages → Deploy from a branch → main / (root) → Save**.
4. In Firebase, go to **Authentication → Settings → Authorized domains**. Your `YOUR-USERNAME.github.io` domain is already there from the planner; if not, add it.

## Live mode: setting up Firebase for the first time
Follow steps 1–4 and 7 of the Negotiation Planner README:
1. Create a project.
2. Register a web app and copy its four settings.
3. Turn on **Anonymous** sign-in.
4. Create a Firestore database in a European location and paste in the rules from this folder.
5. Add your GitHub Pages domain to **Authorized domains**.

Then do steps 1 and 3 above.

## Test it before class
1. Open your GitHub Pages address. The badge should say **Live sync on**.
2. Click **Create team**, tick **Start from the LoopBox setup**, then **Copy team link**.
3. Open the link in a **different browser**, or a private window, or on your phone. The same browser shares one identity, so two tabs count as one person.
4. In the second browser, choose a name and submit scores. In the first browser, **Status & reveal** should show that person as **Submitted**, while **Results** stays sealed.
5. Click **Reveal all scores**. Both browsers show the results at the same moment.

---

## Running it in class
1. **Facilitator** (one per team): **Create team** → **Set up the team**. Add the founders and the synergies (pairs, or trios when value only appears with all three), set the option pool, and copy the team link to the team chat.
2. **Each founder**: open the link → **Score privately** → choose your name → score alone → **Submit my scores**. Scores can be changed until the reveal.
3. **Facilitator**: watch **Status & reveal**. When everyone has submitted, click **Reveal all scores**.
4. **Discuss** the items under *Where scorers disagree* first. If the team wants, the facilitator clicks **Hide scores and reopen scoring** for a second round. Everyone keeps their previous numbers and can adjust them.

**Good to know**
- **The facilitator is tied to the browser that created the team.** Use the same browser and device to reveal. If that browser's data is cleared, the facilitator controls are lost, and the simplest fix is to create the team again.
- **Changing the setup after scoring has started** (adding a person or a synergy) means everyone must score again. Old scores are flagged and left out of the results automatically.
- **Results average only what was submitted before the reveal.** Anyone missing is named at the top of the results.
- **Anyone with the team link can join as a team member.** Keep links inside the team.

## Free-tier limits and privacy
- Each team uses a few hundred database reads and writes per session, well within Firebase's free plan for a whole class.
- The database stores the team setup, each founder's chosen name and their scores. There are no emails or passwords.
- Choose a European Firestore location to keep data in the EU.
- The page loads fonts from Google Fonts. A version with bundled fonts is available if your institution prefers no outside requests.
- To delete a team, remove it in the Firebase console under **Firestore Database → Data → shapley**.
