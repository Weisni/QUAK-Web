# QUAK Web

**[Open QUAK](https://weisni.github.io/QUAK-Web/)** — Quak! Unsere Abstimmung klappt.

QUAK is a browser-based scheduling poll with availability calendars, timezone-aware matching, optional encrypted file exchange, invitations and a small duck game. No app download, account or installation is needed. Interface: German.

## Use

1. Open the website in a modern browser, including Safari on iPhone.
2. Enter availability or load an invitation using **Einladung laden**. Invitation JSON and self-contained invitation HTML are supported.
3. Save/share your response file and send it back to the organizer. The organizer loads replies to find common dates.

QUAK processes participant data locally in your browser. There is no shared poll backend or automatic response delivery. GitHub hosts the static website and receives normal page requests. Browser storage is specific to this website; it is separate from offline copies. Optional export encryption does not encrypt browser storage.

## Distribution

This public repository contains only the generic built app (`site/index.html`), its version/SHA256 metadata and hosting configuration. Development takes place in a private repository. Browser-delivered executable code is necessarily public. Personal availability, invitation packages, passwords and private-repository credentials must never be committed here.

A private release publisher verifies the release artifact and pushes only allowlisted files into `site/`. It uses a deploy key restricted to this public repository; this repository has no access to the private development repository. The Pages workflow publishes only `site/`, not repository documentation.

## Progress and open tasks

- [x] Publish QUAK v0.2.1 as a generic browser app.
- [x] Include release version and SHA256 in `site/version.json`.
- [x] Configure automatic Pages deployment on distribution updates.
- [ ] Confirm hosted operation on a physical iPhone.

HTTPS avoids the iOS Files-preview restriction because the app opens as a normal web page. Actual target-device acceptance remains separate from desktop/browser automation checks.
