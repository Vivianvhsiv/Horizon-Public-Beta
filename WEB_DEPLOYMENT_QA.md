# Web deployment preparation QA

## Passed
- `app.py` and `qa_check.py` compile with Python 3.11-compatible syntax.
- Existing offline structural QA: 574/574 checks passed.
- Railway configuration (`railway.json`) and `Procfile` are present.
- Python runtime pin and Streamlit server configuration are present.
- `HORIZON_ACCESS_PASSWORD` gate is required; app refuses to start its main interface if the secret is absent.
- Password comparison uses `hmac.compare_digest`.
- Login supports English and Vietnamese; a logout control is available in the sidebar.
- No password or `.env` file is included in the deployment package.
- Reflection journal remains session-only and is not saved to a shared database by this prototype.
- ZIP integrity test passed.

## Not yet verified
- Dependencies could not be installed in this build environment because outbound package-network access is unavailable.
- No live Streamlit browser session could be launched here.
- Railway deployment and generated domain have not been created; the owner's Railway account connection and secret configuration are required.
- Desktop/mobile interaction, graph component behavior, and real Vietnamese academic copy-editing remain part of the private pilot test.

## Release status
Prepared for owner-controlled private deployment. Not a live website and not certified for public student use yet.
