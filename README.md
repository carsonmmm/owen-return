# Owen's Return

A responsive birthday/event landing page for Owen's return celebration.

## Files
- `index.html` — the original event page.
- `.nojekyll` — tells GitHub Pages not to run Jekyll processing.

## Publishing with GitHub Pages
1. Open **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Select the `main` branch and `/(root)`, then Save.
4. GitHub will provide the published URL after deployment.

## Important: RSVP backend
The original page uses the Claude-hosted `window.claude.use('db')` and `window.claude.use('user')` APIs for shared RSVPs, guest-list updates, and host editing. Those APIs are not available on GitHub Pages. The visual page can be hosted, but those shared features need to be migrated to a supported backend (for example, Firebase) before the site is ready for guests to use.

Do not collect real guest information until that backend migration and its access rules are configured.
