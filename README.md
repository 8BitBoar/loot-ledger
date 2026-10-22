# Loot Ledger

A personal link-collection page. Make collections with a name, description and a [game-icons.net](https://game-icons.net) icon, then add links from any website.

- **This repo (`loot-ledger`, public):** just the page. It contains no data.
- **Data repo (`loot-ledger-data`, private):** holds `collections.json`. Every change you make on the page is saved there as a commit, so you get full history for free.
- **Your token:** lets the page read and write the private data repo. It is stored only in the browser you paste it into.

Live page (after setup): **https://8bitboar.github.io/loot-ledger/**

---

## One-time setup

### 1. Create the private data repo
1. Go to https://github.com/new
2. Repository name: `loot-ledger-data`
3. Choose **Private**.
4. Tick **Add a README file** (the repo needs at least one commit).
5. Click **Create repository**. You don't need to add anything else; the page creates `collections.json` on your first save.

### 2. Create the public app repo and upload the page
1. Go to https://github.com/new
2. Repository name: `loot-ledger`
3. Choose **Public** (free GitHub Pages only works from public repos; there's no data in it).
4. Click **Create repository**.
5. Click **uploading an existing file**, drag in `index.html` and this `README.md`, then **Commit changes**.

### 3. Turn on GitHub Pages for the app repo
1. In `loot-ledger`, open **Settings → Pages**.
2. Under **Build and deployment → Source**, pick **Deploy from a branch**.
3. Branch: **main**, folder: **/ (root)**. Click **Save**.
4. Wait a minute or two. The page appears at https://8bitboar.github.io/loot-ledger/

### 4. Create a token for the data repo
1. Go to https://github.com/settings/personal-access-tokens/new (Settings → Developer settings → Personal access tokens → Fine-grained tokens).
2. **Token name:** `Loot Ledger`
3. **Expiration:** your choice. When it expires, make a new one and paste it in again.
4. **Repository access:** **Only select repositories** → choose `loot-ledger-data` only.
5. **Permissions → Repository permissions → Contents:** **Read and write**. (Metadata: Read-only is added automatically.) Leave everything else as No access.
6. Click **Generate token** and copy it. GitHub only shows it once.

### 5. Connect
Open https://8bitboar.github.io/loot-ledger/, paste the token, and click **Connect**. Done.

On each new computer, open the same address and paste the token once. If you lose the token, generate a new one; your data is unaffected.

---

## Using it

- **New collection:** name, description, icon and icon color.
- **Icons:** on game-icons.net open an icon, click **Download SVG**, then **Upload .svg** in the collection editor (or paste the SVG code). The default black background is removed automatically.
- **Add links:** paste a URL into the collection, with an optional title and note. Or paste anywhere on the page outside a text box.
- **Add from any website:** open **Settings** and drag the **+ Loot Ledger** button to your bookmarks bar. On any page, click it; Loot Ledger opens with that page ready to add. Pick a collection and click **Add to collection**.
- **Saving:** automatic. The dot next to the title shows the state. Changes are batched into one commit about a second after you stop editing.
- **Another computer:** switching back to the tab picks up changes made elsewhere. If two computers edit at the same moment, the last save wins.
- **Backups:** every save is a commit in `loot-ledger-data`, so you can restore any old version from its history on GitHub. **Settings → Download backup** also saves a JSON copy, and **Import backup** loads one.

## Safety notes

- The token only works on `loot-ledger-data`, so even if it leaked, it couldn't touch your other repos or your account.
- Use **Settings → Forget token on this computer** on shared or public computers.
- To revoke access everywhere, delete the token at https://github.com/settings/personal-access-tokens

## Changing names

If you rename the data repo or your username changes, type the new names on the connect screen. To change the defaults, edit `DEFAULTS` near the top of the script in `index.html`.
