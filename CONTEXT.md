# teamcapybara/capybara context
> refreshed 2026-10-10 | upstream default: master @ 265d2d17a6b8f0c2a9c5cfd0da3aa2ad4e0b9c39

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
- 2026-10-10 self-found trivial cleanup - pr-opened (fork #3, `fix-typos-and-stale-ruby-version`) - README stale min Ruby (3.0.0 -> 3.2.0, gemspec says >= 3.2.0) + `evaluate_script_asnyc` error string in lib/capybara/driver/base.rb + 4 History.md misspellings + spec filename rename `regexp_dissassembler_spec.rb` -> `regexp_disassembler_spec.rb` + 3 spec-comment typos (`jus`, `processe`). LESSON: twalpole explicitly reverted test-name/description spelling changes in upstream PR #2584 ("Other drivers use the suite ... changing large numbers of them outside of a major release isn't great"), so spec file RENAMES and COMMENT fixes are fine but do NOT touch `it`/`describe` description text.

- 2026-10-11 self-found trivial cleanup - pr-opened (fork #4, `fix-doc-and-comment-typos`) - 7 one-word typo fixes in 5 files (+7/-7): UPGRADING.md `non-blanking`->`non-breaking`; History.md `Changned`->`Changed`, `certicficate`->`certificate`, `[John Firebough]`->`[John Firebaugh]`; comment fixes in `lib/capybara/selector/definition.rb` (`user`/`dupport`->`use`/`support`), `lib/capybara/selenium/driver_specializations/edge_driver.rb` (`seleniun-webdriver`->`selenium-webdriver`), `lib/capybara/spec/session/window/window_spec.rb` (`dependant`->`dependent`). Deliberately DISJOINT from the open PR #3 (README stale Ruby version, dead seleniumhq.org link, 4 History.md misspellings, base.rb `evaluate_script_asnyc`, spec-description typos + `regexp_dissassembler_spec.rb` rename) - no shared line/word. Still off-limits: it/describe description text (#2584), History.md historical release-title quotes, and the ambiguous `selector_query.rb` `visbile` cache-typo note.
## Mined gaps (discovered, not yet attempted)
- 2026-10-10 `code.google.com/p/selenium/issues/detail?id=7405` in History.md redirects to issues.chromium.org (works, 302) - left alone, not dead
- 2026-10-10 remaining genuine typo surface is thin; most wrong-word cases outside the fixed set are inside test descriptions (off-limits per #2584) or historical History.md entries where the quote matches a release title
- test-name spelling changes: BLOCKED upstream (see gap ledger 2026-10-10 lesson)
