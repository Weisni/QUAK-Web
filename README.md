# QUAK Web

**[Open QUAK](https://weisni.github.io/QUAK-Web/)** — Quak! Unsere Abstimmung klappt.

QUAK is a browser-based scheduling poll with availability calendars, timezone-aware matching, optional encrypted file exchange, invitations and a small duck game. No app download, account or installation is needed. Interface: German.

## Use

1. Open the website in a modern browser, including Safari on iPhone.
2. Create an invitation and choose **Einladungslink erstellen**, or open a received invitation link. File invitations can still be loaded with **Einladung laden**.
3. Enter availability, choose **Antwortlink erstellen**, then copy/share the link back to the organizer. Every response link the organizer opens is collected automatically in that browser.
4. Use **Gesammelte Antworten** to select a collection, remove replies or save/restore a backup. **Links einfügen** accepts multiple links copied from chat text. Matching uses the selected collection.

QUAK processes participant data locally in your browser. There is no shared poll backend or automatic response delivery. GitHub hosts the static website and receives normal page requests. Browser storage is specific to this website; it is separate from offline copies. Optional export encryption does not encrypt browser storage.

Link payloads are compressed in the URL fragment (`#quak=…`) and can optionally be password protected. Share passwords separately. Anyone with a plain link can read/forward it. Successfully opened links are removed from the current address; original messages and browser history may retain them. IndexedDB collections persist across reloads and update other supported tabs. Identical answers are skipped; changed answers with the same participant ID ask before replacing. Invitation revisions remain separate. There is no sender authentication or cross-device synchronization. Deleting a local answer does not invalidate its link; opening it again imports it again.

Limits: 20 collections, 12 replies each, 2 MiB combined compact backup data. Backups contain unencrypted names and answers. Browser policy can clear local data, so keep a backup. Links over 4000 characters show a compatibility warning; over 12000 are refused with file exchange as fallback. These limits do not guarantee compatibility with every messenger.

## Distribution

This public repository contains only the generic built app (`site/index.html`), its version/SHA256 metadata and hosting configuration. Development takes place in a private repository. Browser-delivered executable code is necessarily public. Personal availability, invitation packages, passwords and private-repository credentials must never be committed here.

A private release publisher verifies the release artifact and pushes only allowlisted files into `site/`. It uses a deploy key restricted to this public repository; this repository has no access to the private development repository. The Pages workflow publishes only `site/`, not repository documentation.

## Progress and open tasks

- [x] Publish QUAK as a generic browser app with invitation/reply links and local collections.
- [x] Verify ten replies, reload persistence, duplicate/replacement handling, deletion, backup restore and cross-tab updates using synthetic data.
- [x] Include release version and SHA256 in `site/version.json`.
- [x] Configure automatic Pages deployment on distribution updates.
- [ ] Confirm hosted operation on a physical iPhone.

HTTPS avoids the iOS Files-preview restriction because the app opens as a normal web page. Actual target-device acceptance remains separate from desktop/browser automation checks.
