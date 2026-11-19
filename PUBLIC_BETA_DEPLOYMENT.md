# Horizon v24 — Public Beta Deployment

This package is intended for a public beta: anyone who has the generated URL can open the prototype. It is not a private or access-controlled deployment.

## Deploy on Railway

1. Create a new **public GitHub repository** for this beta, or use a private repository if you prefer to control who can see the source code. The deployed website itself will still be public.
2. Upload the contents of this folder to the repository root (not the parent folder).
3. In Railway, create a new project and choose Deploy from GitHub Repo.
4. Select the repository and deploy.
5. Generate a Railway domain for the service.
6. Wait for the health check at `/_stcore/health` to pass, then open the generated URL in a signed-out/private browser window.

No `HORIZON_ACCESS_PASSWORD` variable is required in this public-beta build.

## Before sharing

- Anyone with the URL can access the prototype; the URL is not a secret.
- Do not upload student questionnaire responses, names, emails, contact details, or other personal information.
- Do not enter sensitive personal information into the prototype.
- This prototype's reflection notes are session-based and are not a shared persistent student database.
- The major/subject relationships are exploratory, not admissions requirements or suitability judgments.
- Test English and Vietnamese, all 13 EMASI subjects, major details, compare, reflection, and mobile layout.
- Label feedback as prototype feedback and review it before treating the site as a finished product.

## Runtime

- Python version: see `.python-version`
- Install: `pip install -r requirements.txt`
- Start: `streamlit run app.py --server.address 0.0.0.0 --server.port $PORT --server.headless true`
- Health check: `/_stcore/health`

The Railway deployment is not performed by creating this ZIP. A Railway account connection and repository selection are still required.
