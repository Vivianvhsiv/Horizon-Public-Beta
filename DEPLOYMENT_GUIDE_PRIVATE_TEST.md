# Horizon v24 — Private Web Deployment Guide

This package keeps the existing Streamlit application and prepares it for a controlled Railway web deployment. It does not publish the site by itself.

## 1. What is included

- Existing Horizon v24 Streamlit application and 20 bilingual major profiles.
- 13 EMASI subject choices, including Geography (S12) and History (S13).
- Existing academic source and claim records.
- Railway start configuration (`railway.json` and `Procfile`).
- Python runtime pin (`.python-version`).
- Streamlit server configuration (`.streamlit/config.toml`).
- A password gate controlled by the `HORIZON_ACCESS_PASSWORD` environment variable.

## 2. Publish through Railway

1. Put the contents of this folder in a **private** GitHub repository. Do not upload `.env`, passwords, student responses, or private records.
2. In Railway, create a new project and deploy from the private GitHub repository.
3. In the Railway service's Variables panel, add:
   - `HORIZON_ACCESS_PASSWORD` = a new, strong password chosen by the project owner.
4. Generate a Railway domain for the service.
5. Wait for the deployment health check at `/_stcore/health` to pass.
6. Open the generated domain in a private/incognito browser and test the password gate before sharing it with invited testers.

Railway's project/service visibility and a private GitHub repository do not, by themselves, guarantee that the generated website URL is private. The application-level password gate is enabled by default. For a larger pilot, use individual accounts or an identity-aware access layer rather than sharing one password widely.

## 3. Local test

macOS / Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export HORIZON_ACCESS_PASSWORD='choose-a-local-test-password'
streamlit run app.py
```

Windows PowerShell:

```powershell
py -3.11 -m venv .venv
.venv\Scripts\Activate.ps1
pip install -r requirements.txt
$env:HORIZON_ACCESS_PASSWORD = 'choose-a-local-test-password'
streamlit run app.py
```

Open `http://localhost:8501`.

## 4. Private pilot checklist

- Test both English and Vietnamese on home, network, major details, compare, reflection and about pages.
- Test all 13 EMASI subjects and graph interactions on desktop and mobile.
- Confirm a wrong password is rejected and the correct password opens the app.
- Confirm the Log out button returns to the login screen.
- Confirm the site does not request names, email addresses or other identifying student information.
- Do not ask students to enter sensitive personal information in reflection fields.
- Reflection entries remain in the current Streamlit session and can be downloaded by the student; they are not written to a shared database by this prototype.
- Have a Vietnamese academic editor review technical terminology.
- Obtain EMASI syllabi and grade-level learning outcomes before making exact curriculum-equivalence claims.

## 5. Important limitations

- This is a private-test deployment package, not a public-release certification.
- The shared password is a basic pilot gate, not individual user authentication or a complete security system.
- Do not store sensitive student data in this prototype.
- Programme requirements vary by institution, country, pathway and admission year. EMASI subject links remain exploratory unless explicitly verified against programme-specific evidence.
