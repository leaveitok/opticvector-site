Publish log
===========

This file records why a commit was made when the commit changes no page content. It also
serves as the mechanism: GitHub Pages only builds on a push, so a commit here is how a lost
build gets recreated.

2026-08-07 - republish 7b3574e
------------------------------

The GitHub Actions and Pages outage on 2026-08-06 swallowed the Pages build for commit
7b3574e. GitHub does not create that build retroactively. The active deployment stayed at
pages-build-deployment 27, which is commit 9a38633, so the served civicroute.html was still
missing loadIntakeConfig, the callback tick inside humanwrap, the contact gate, and the
receipt line that renders the callback promise returned by the city.

This commit changes no page content. It exists only to trigger the build that was lost.

The backend half is already live and proven: govassist release 00.61, commit 382dcfd,
matched against app_release and git_sha on /api/health. The public endpoint
/api/cases/opticvector-311/intake-config returns the callback promise in English and in
Spanish, so the UI this publishes has a real source to read from.
