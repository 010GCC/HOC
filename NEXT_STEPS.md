# Next Steps

## 1. Set Up JSONBin Leaderboard (do this first)

1. Go to [jsonbin.io](https://jsonbin.io) and create a free account.
2. Click **Bins** → **+ New Bin**, paste `{ "scores": [] }` as content, click **Create**.
3. Copy the **Bin ID** from the URL bar.
4. Go to **API Keys** → **+ Create API Key**, name it `hoc-game`, copy the key.

## 2. Inject Credentials into index.html

Open `index.html` and find near the top of the `<script>` block:

```js
const JSONBIN_API_KEY = "$2a$10$YOUR_KEY_HERE";
const JSONBIN_BIN_ID  = "YOUR_BIN_ID_HERE";
```

Replace both values with your JSONBin API key and Bin ID. Save the file.

## 3. Push the Update

```bash
git add index.html
git commit -m "Add JSONBin leaderboard credentials"
git push origin main
```

## 4. Test It

Visit: **https://010GCC.github.io/HOC**

Play a game, submit your score, and check the leaderboard works.

---

Good night! 🌙
