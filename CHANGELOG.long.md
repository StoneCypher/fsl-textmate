# Changelog

All notable changes to this project will be documented in this file.

5 merges



&nbsp;

&nbsp;

Published tags:







&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 1:03:17 PM

Commit [893a4160a6e73a0ef9ddd741256874a1f901d72c](https://github.com/StoneCypher/fsl-textmate/commit/893a4160a6e73a0ef9ddd741256874a1f901d72c)

Author: `John Haugeland <stonecypher@gmail.com>`

Merges [87506bc, b1f0646]

  * Merge pull request #5 from StoneCypher/docs_26-07-17_readme-template-cleanup
  * docs: strip template boilerplate + dead viz table from the README (0.1.1)




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 10:52:29 AM

Commit [b1f0646d1d797199dc6379bb200d324979d01f54](https://github.com/StoneCypher/fsl-textmate/commit/b1f0646d1d797199dc6379bb200d324979d01f54)

Author: `John Haugeland <stonecypher@gmail.com>`

  * docs: strip template boilerplate + dead viz table from the README (0.1.1)
  * Remove the "How to use this template" / "Before invoking it" section and the
bundle_*.png visualization table from base_README.md — leftovers from the
react_ts_with_claude_gh_template scaffold that were shipping in this mirror's
published README (the viz table pointed at PNGs that no longer exist, since
viz_png is disabled for the mirror). The build chain regenerates README.md
(and the site/docs) from base_README, so this cleans up the front page. Also
drops the committed bundle_*.png and bumps to 0.1.1.




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 10:52:29 AM

Commit [3858a42a29061802177ee30cf8c5b22279706993](https://github.com/StoneCypher/fsl-textmate/commit/3858a42a29061802177ee30cf8c5b22279706993)

Author: `John Haugeland <stonecypher@gmail.com>`

  * docs: strip template setup boilerplate from the README (0.1.1)
  * Remove the "How to use this template" / "Before invoking it" section from
base_README.md — leftover from the react_ts_with_claude_gh_template scaffold,
which was shipping in this mirror's published README. The build chain
regenerates README.md (and the site/docs) from base_README, so this cleans up
the front page. Also drops the now-unused bundle_*.png (viz_png is off) and
bumps to 0.1.1.




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 7:58:21 AM

Commit [87506bcf8fa0a1ed85a6b16c79360735ef586c6f](https://github.com/StoneCypher/fsl-textmate/commit/87506bcf8fa0a1ed85a6b16c79360735ef586c6f)

Author: `John Haugeland <stonecypher@gmail.com>`

Merges [695fa3a, 5f28543]

  * Merge pull request #4 from StoneCypher/chore_26-07-17_drop-playwright-browser
  * chore(build): drop the Playwright browser install from the mirror




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 7:57:46 AM

Commit [5f2854319d617528b5b4f7552096bda35617f3ee](https://github.com/StoneCypher/fsl-textmate/commit/5f2854319d617528b5b4f7552096bda35617f3ee)

Author: `John Haugeland <stonecypher@gmail.com>`

  * chore(build): drop the Playwright browser install from the mirror
  * A grammar mirror never drives a browser, so downloading Chromium on every
install was pure overhead — and it was what cached Chromium into the repo
tree, producing the eslint-on-chromium noise. Remove the `postinstall`
browser install and disable the browser-rendered `viz_png` build step, so
`npm install` fetches no browser and the full build never needs one.
  * Verified: build, lint, 43 tests, and attw all stay green (`[build] disabled:
viz_png`, no viz stage, no browser). The Playwright devDeps and the now-unused
e2e / visualization scaffolding can be removed in a follow-up if wanted; this
keeps the change minimal and low-risk.




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 7:50:23 AM

Commit [695fa3a23562ed4f303fab77fdc40e62d817fd56](https://github.com/StoneCypher/fsl-textmate/commit/695fa3a23562ed4f303fab77fdc40e62d817fd56)

Author: `John Haugeland <stonecypher@gmail.com>`

Merges [c8dde91, e675ca5]

  * Merge pull request #3 from StoneCypher/fix_26-07-17_eslint-ignore-playwright
  * fix(lint): ignore .playwright-browsers so eslint doesn't lint Chromium




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 7:37:27 AM

Commit [e675ca5763064c0aa9a42cc3ba50c8ac772a2876](https://github.com/StoneCypher/fsl-textmate/commit/e675ca5763064c0aa9a42cc3ba50c8ac772a2876)

Author: `John Haugeland <stonecypher@gmail.com>`

  * fix(lint): ignore .playwright-browsers so eslint doesn't lint Chromium
  * CI sets PLAYWRIGHT_BROWSERS_PATH to a workspace-relative .playwright-browsers/
and postinstall runs `playwright install`, so Chromium is unpacked inside the
repo tree. The bare `eslint` script lints the whole working dir, and eslint's
built-in ignores cover node_modules but not .playwright-browsers/ — so it
recursed into Chromium's bundled extension scripts (reading_mode_gdocs_helper/*)
and failed on the `chrome` extension global ('chrome' is not defined, no-undef).
  * Add .playwright-browsers/** to the eslint ignores, alongside the other vendor/
generated dirs (build, dist, docs, .stryker-tmp).




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 7:31:31 AM

Commit [c8dde911e1d174a8e52c2eec5d8e4eeecb149c54](https://github.com/StoneCypher/fsl-textmate/commit/c8dde911e1d174a8e52c2eec5d8e4eeecb149c54)

Author: `John Haugeland <stonecypher@gmail.com>`

Merges [555e72c, b954375]

  * Merge pull request #2 from StoneCypher/fix_26-07-17_rollup-global-name
  * fix(build): use a legal JS identifier for the rollup bundle global




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 7:31:04 AM

Commit [b954375bacbc57138960a2be8577f7dcf07e428f](https://github.com/StoneCypher/fsl-textmate/commit/b954375bacbc57138960a2be8577f7dcf07e428f)

Author: `John Haugeland <stonecypher@gmail.com>`

  * fix(build): use a legal JS identifier for the rollup bundle global
  * rollup.config.js hardcoded output.name as the package name 'fsl-textmate',
but the iife format requires a legal JS identifier and a hyphen is illegal
(RollupError: Given name "fsl-textmate" is not a legal JS identifier).
Camel-case it to 'fslTextmate' across the es/cjs/iife outputs (name is
ignored for es/cjs but kept consistent). Full build now passes — rollup
emits all three bundles, attw is clean, and the 43 tests are green.




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 6:25:31 AM

Commit [555e72cc1660fe78137c20b28333067ddf1242d8](https://github.com/StoneCypher/fsl-textmate/commit/555e72cc1660fe78137c20b28333067ddf1242d8)

Author: `John Haugeland <stonecypher@gmail.com>`

Merges [5b5d2da, b5a0a60]

  * Merge pull request #1 from StoneCypher/feat_26-07-16_grammar-sync
  * ci: add jssm grammar mirror + pull-based sync




&nbsp;

&nbsp;

## [Untagged] - Jul 17, 2026 6:21:37 AM

Commit [b5a0a603b3b9f3507ae7e64f083cfc62c885f284](https://github.com/StoneCypher/fsl-textmate/commit/b5a0a603b3b9f3507ae7e64f083cfc62c885f284)

Author: `John Haugeland <stonecypher@gmail.com>`

  * ci: add jssm grammar mirror + pull-based sync
  * Seed fsl.tmLanguage.json (the canonical FSL TextMate grammar, scope
source.fsl) byte-for-byte from StoneCypher/jssm@main. This repo is a
read-only mirror and the GitHub Linguist target; the source of truth
stays StoneCypher/jssm.
  * Add .github/workflows/sync-from-jssm.yml — a scheduled + on-demand
workflow that refetches the grammar from jssm's main and commits any
change via the repo's own GITHUB_TOKEN (no cross-repo secret). Do not
hand-edit fsl.tmLanguage.json; it is overwritten by the sync.
  * Refs: StoneCypher/fsl#1960




&nbsp;

&nbsp;

## [Untagged] - Jul 16, 2026 9:28:17 PM

Commit [5b5d2dadc9d6eb99ea0ce36545a13c77c1fac365](https://github.com/StoneCypher/fsl-textmate/commit/5b5d2dadc9d6eb99ea0ce36545a13c77c1fac365)

Author: `John Haugeland <stonecypher@gmail.com>`

  * cleanup




&nbsp;

&nbsp;

## [Untagged] - Jul 16, 2026 9:19:42 PM

Commit [9eda9913c8df768b735301068d059d9718a2a004](https://github.com/StoneCypher/fsl-textmate/commit/9eda9913c8df768b735301068d059d9718a2a004)

Author: `John Haugeland <stonecypher@gmail.com>`

  * Initial commit