# teamcapybara/capybara context
> refreshed 2026-09-30 | upstream default: master @ 15b5fdb76e972e9623d5af2123ed3755594f9732

## Identity & policies
- upstream: teamcapybara/capybara, default branch `master`, primary language Ruby, English-first (yes - README/CONTRIBUTING/issues all English)
- CLA/DCO: none (CONTRIBUTING.md has no CLA or sign-off requirement; no CLA bot on merged PRs)
- AI-assisted PR policy: unstated (no policy line in CONTRIBUTING.md or .github)
- signed commits required: no (no branch protection on master detectable for this token; merged external PRs are not GPG-signed)
- PR template: none (no .github/PULL_REQUEST_TEMPLATE.md and no teamcapybara/.github default) - fork PRs use the pipeline 3-section fallback body
- external tracker: github only

## Conventions (verified from merged PRs)
- branch naming: mixed, descriptive and hyphenated is common (`fix-2828-node-assert-text-count`, `update-links-in-readme`, `selector-example-doc-strings`, `capybara-rails-docs-mismatch-for-default-url`)
- commit style: plain imperative subjects, capitalized, no Conventional-Commits prefix
- test command: `bundle exec rake spec_rack` (rack-only, no browser) / `bundle exec rake` (Firefox) / `bundle exec rake spec_chrome`
- lint command: `bundle exec rubocop` (CI `rack_smoke` = rubocop + spec_rack)
- CI: GitHub Actions `.github/workflows/build.yml`, jobs rack_smoke (ruby 3.3/3.4/4.0, tasks rack_smoke + cucumber), headless (chrome/firefox), headless_base_versions, non_headless, rack_3
- how outside PRs get merged: responsive maintainer (twalpole); small docs/test/fix PRs from outside contributors merged in days (e.g. #2842, #2830, #2786, #2835)

## Maintainer picture
- twalpole (Thomas Walpole) is the active maintainer and merges nearly all external PRs
- recent outside contributors merged: cgunther, khhizr007, ragesoss, wwenrr, wynksaiddestroy, osatoh, theodorton
- docs-only PRs are merged, so small doc clean-ups are welcome

## Issue-area health
- ~24 open issues; issues are mostly usage questions redirected to Discussions
- Discussions (Q&A) are the support channel: https://github.com/orgs/teamcapybara/discussions/categories/q-a
- trivial typo/link clean-ups: none open upstream touching the README Selenium link or the spec-description typos

## Gap ledger (dedupe - READ FIRST, never re-pick)
- 2026-08-18 issue #2710 - pr-opened (fork #1) - RackTest Browser#refresh reused the app-mutated env hash; fixed + regression test
- 2026-08-26 fork #1 - pr-updated (audit sweep, body gate)
- 2026-09-25..27 - engine-failure x3 (run.sh exited 1, no trace; not a repo problem)
- 2026-09-30 self-found trivial cleanup - pr-opened (fork #2) - dead seleniumhq.org link + README missing space + spec-description typos (`specififed`, `explicity`, `doesnt`, `instaed`, `fullfilled`, `querys`)

## Mined gaps (discovered, not yet attempted)
- none open right now; the trivial typo/link pass for 2026-09-30 found 8 genuine fixes and shipped them in one PR
