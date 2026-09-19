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

ZIP को extract करो और सभी files को repository में upload करो।

Important: `README.md` repository के root में होना चाहिए और `.github/workflows/` folder भी upload होना चाहिए।

## Step 3 — Actions permission ON करो

Repository → Settings → Actions → General → Workflow permissions

Select:

`Read and write permissions`

Save करो।

## Step 4 — METRICS_TOKEN बनाओ

Metrics workflow को GitHub Personal Access Token (PAT) चाहिए। `GITHUB_TOKEN` अकेला Metrics data fetch करने के लिए पर्याप्त नहीं है. 

GitHub → Settings → Developer settings → Personal access tokens

Classic token बनाना इस setup के लिए सबसे straightforward option है। कम से कम:

- `read:user`

Private repositories का data भी metrics में चाहिए तो जरूरत के अनुसार `repo` scope जोड़ सकते हो।

Token copy करो और फिर repository में जाओ:

Settings → Secrets and variables → Actions → New repository secret

**Name:**

`METRICS_TOKEN`

**Secret:**

अपना पूरा GitHub token paste करो।

Token को workflow YAML या README में कभी paste मत करना।

## Step 5 — Workflows run करो

Repository → Actions

इन workflows को एक-एक बार manually run कर सकते हो:

1. Metrics
2. Charts and cards
3. Snake

पहली generation में कुछ मिनट लग सकते हैं।

## Important

- `profile.gif` animated profile image है।
- `skills.json` में self-rated skill values हैं।
- `projects.json` में featured projects हैं।
- Snake workflow `output` branch बनाएगा।
- Metrics generated SVG files `assets/` में commit होंगे।
- Metrics workflow generated metrics SVG को बदलने वाली push event पर दोबारा trigger नहीं होगा, इसलिए unnecessary loop नहीं बनेगा।
