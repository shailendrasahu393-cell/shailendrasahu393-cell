# Shailendra GitHub Profile Setup Guide

यह repository तुम्हारे GitHub username के नाम से ही GitHub पर बनानी है:

`shailendrasahu393-cell`

## Folder structure

```text
shailendrasahu393-cell/
├── README.md
├── SETUP-HINDI.md
├── .gitignore
├── .gitattributes
├── assets/
│   ├── profile.gif
│   ├── skills.json
│   ├── projects.json
│   ├── radar-dark.svg
│   └── radar-light.svg
├── scripts/
│   ├── radar.py
│   └── cards.py
└── .github/
    └── workflows/
        ├── metrics.yml
        ├── radar.yml
        └── snake.yml
```

## Step 1 — GitHub repository बनाओ

GitHub → New repository

Repository name exactly:

`shailendrasahu393-cell`

Visibility: **Public**

## Step 2 — इस पूरे folder का content upload करो

इस ZIP को extract करो और सभी files को repository में upload करो।

Important: `README.md` repository के root में होना चाहिए।

## Step 3 — पहली commit

GitHub web upload करते समय commit message:

`feat: add professional GitHub profile README`

या terminal से:

```bash
git init
git branch -M main
git add -A
git commit -m "feat: add professional GitHub profile README"
git remote add origin https://github.com/shailendrasahu393-cell/shailendrasahu393-cell.git
git push -u origin main
```

## Step 4 — Actions permission ON करो

Repository → Settings → Actions → General → Workflow permissions

Select:

`Read and write permissions`

Save करो।

## Step 5 — METRICS_TOKEN बनाओ

GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)

एक classic token बनाओ और scope select करो:

- `read:user`

अगर private repository data भी future में count करना है तो `repo` भी select कर सकते हो।

Token copy करो।

फिर repository:

Settings → Secrets and variables → Actions → New repository secret

Name:

`METRICS_TOKEN`

Value में token paste करो।

## Step 6 — Workflows run करो

Repository → Actions

इन तीनों workflows को एक-एक बार manually run करो:

1. Metrics
2. Charts and cards
3. Snake

पहली बार generation में कुछ मिनट लग सकते हैं।

## Important

- `profile.gif` तुम्हारी animated photo है और लगातार loop होती है।
- `skills.json` में तुम्हारे self-rated skill values हैं; future में इन्हें बदल सकते हो।
- `projects.json` में featured projects हैं; नया project जोड़ने पर वही list update करनी है।
- Snake workflow `output` branch बनाएगा।
- Repo cards और metrics GitHub Actions run होने के बाद दिखाई देंगे।
