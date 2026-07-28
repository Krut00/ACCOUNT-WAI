# Screener.in Company Analyzer

This is a Streamlit dashboard that scrapes Screener.in and optionally uses a local MCP server to show accounting metrics and simple investment guidance.

Deployment to Streamlit Community Cloud

1. Push this repository to GitHub (create a new repo on GitHub and push your local code):

```bash
git init
git add .
git commit -m "Initial commit - Screener dashboard"
git branch -M main
# create a repo on GitHub and add remote, or use `gh repo create`
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

2. Go to https://streamlit.io/cloud and sign in with GitHub.
3. Click **New app** → select your repository and branch (`main`) → set the main file to `accounting_dashboard_streamlit.py` → Deploy.
4. In the app settings, add any `secrets` required (for example, your local MCP URL or API keys) under **Settings → Secrets**. Example key: `MCP_SERVER_URL`.

Notes
- The app expects values scraped from Screener.in in ₹ Crore scale. Manual inputs should use the same scale.
- If your app depends on private data or secrets, use Streamlit secrets or environment variables in the Cloud settings.
