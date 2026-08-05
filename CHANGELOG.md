# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/).

## [1.0.1] - 2026-08-05

### Changed
- Department filter switched from `?department=NOVA Power & Gas` (3 jobs, one heading) to `?department=Nova`, which matches both board headings (`NOVA Power & Gas` and `NOVA Power&Gas`) and scrapes all 11 open NOVA jobs.
- Careers URL updated from `https://vreaulanova.ro/cariere` (404) to `https://vreaulanova.ro/posturi-disponibile`.
- Listing URL now URL-encodes the department parameter (`build_listing_url`).

## [1.0.0] - 2026-08-03

### Added
- Python scraper for the NOVA POWER & GAS S.A. department on the group's applytojob board (`?department=NOVA Power & Gas`).
- Publisher to peviitor v1 API: company upsert, job upload, stale-job delete.
- ANAF company validation with CUIScan fallback and cache.
- ANOFM job search mirroring the Node.js template.
- `validate_jobs.py` CLI for head/content URL validation.
- Unit, integration, e2e, and consistency tests.
- GitHub Actions workflows: `job-seeker-ro-spider`, `automation-testing`, deep-validate, recovery.
- GitHub Pages (`docs/`) with generated `jobs.md` and `company.json`.
- AI documentation under `ai/`.

### Fixed
- Location normalization: common spellings (`Bucuresti`, `Turda`, etc.) and case/diacritic variants are no longer dropped to `România`.
- Stale-job deletion is scoped to this scraper's applytojob board, so jobs published by other peviitor scrapers under the same CIF are never removed.
- E2E `EXPECTED_MIN_JOBS` and integration tests reflect the NOVA POWER & GAS department and CIF `18680651`.
