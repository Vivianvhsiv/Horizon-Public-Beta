# Horizon v24 — Bilingual Academic Exploration Platform

Horizon is a student-led exploration prototype for EMASI high-school students. It helps students explore possible connections among interests, current school subjects, academic disciplines, university majors and possible career areas.

## Languages
- English
- Tiếng Việt

The major profile sections, academic evidence labels and EMASI subject names have paired English/Vietnamese content. Official university names, programme titles and source-page titles remain in their original published language so that students can locate and verify the source.

## Current EMASI subject inventory
The selector includes 13 subjects: Mathematics, Literature, English, Physics, Biology, Chemistry, Music, Fine Arts, ICT, Economics and Law, Technology, Geography and History.

Geography and History were added as exploratory inputs (S12 and S13). Their presence does not mean that every university programme requires them. Subject connections are suggestions for exploration, not universal admission prerequisites or judgements of student suitability.

## Run locally
```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
export HORIZON_ACCESS_PASSWORD='choose-a-local-test-password'
streamlit run app.py
```
Open `http://localhost:8501`. The password environment variable is required to access the app.

## Deploy to Railway (private test first)
The repository includes `railway.json`, `Procfile`, `.python-version`, Streamlit server configuration, and `DEPLOYMENT_GUIDE_PRIVATE_TEST.md`. A password gate is enabled by default. Set `HORIZON_ACCESS_PASSWORD` in the Railway service Variables panel before sharing the site. A private source repository does not automatically make the deployed website private; the app-level password is a basic pilot gate, not individual authentication.

## Project structure
- `app.py` — Streamlit application
- `majors.json` and `data/majors.json` — 20 bilingual major profiles
- `academic_sources.json` and `data/academic_sources.json` — source and claim records
- `data/emasi_subjects.json` — the 13-subject inventory
- `data/emasi_mapping_protocol.json` — evidence and mapping rules
- `qa_check.py` — offline structural QA
- `QA_RESULTS.txt` — latest QA results

## Evidence and limitations
University programme pages and curricula support descriptions of university-level subject areas. They do not automatically establish EMASI course equivalence or universal admission requirements. EMASI mapping remains exploratory until the actual EMASI syllabi and grade-level learning outcomes are compared with the relevant university curricula. Requirements vary by institution, programme, pathway and admission year.

## Validation status
The offline QA script checks JSON integrity, bilingual field coverage, subject inventory consistency, source metadata, HTTPS URL format, absence of CJK characters in user-facing app/data files and Python syntax. It does not verify that every external URL remains live, provide Vietnamese academic copy-editing, or replace a full browser/mobile interaction test.
