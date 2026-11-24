# KeePassXC Titanium

KeePassXC Titanium is an independent fork of [KeePassXC](https://keepassxc.org), the open-source password manager. It adds data-integrity, hardening and performance changes on top of KeePassXC and is regularly rebased on the upstream `develop` branch.

Titanium is **not** the official KeePassXC project and is not affiliated with or endorsed by the KeePassXC team. All credit for KeePassXC itself belongs to its authors and contributors. Project badges, certifications, release channels and support channels of the official project (for example its OpenSSF Best Practices badge, CI and community channels) apply to the official project only and are deliberately not claimed here.

See [TITANIUM.md](./TITANIUM.md) for the branch layout and the list of changes.

## Project team

* **scramblr** ([@scramblr](https://github.com/scramblr)): architecture design manager
* **anonymous** ([@anonymous](https://keepassxc-titanium.fuct.app/)): anonymous contributions for ideas and enhancements

## What Titanium adds

* **XML export and import without data loss:** complete export (attachments, history, database settings), streaming export with a low memory peak, an import wizard entry with a settings checklist, exact round trip of control characters, and handling of UUID collisions.
* **CSV export and import without dropped columns:** all entry data is exported, every exported column is imported, unrecognised columns are kept as custom fields, large files parse in linear time, and a warning is shown before an export that cannot hold everything.
* **XML reader hardening:** protected values without a stream, duplicate group and entry UUIDs, a nesting depth limit and out-of-range binary dates.
* **Browser integration:** credentials are found in every connected, unlocked database; stricter checks of requests from web pages and local clients; database-scoped actions are bound to the database the client associated with.
* **Performance and leaks:** throttled tag-list rescans, an icon-picker leak fix and a URL pattern that is compiled once.

Parts of these changes have been offered to the official project as pull requests ([#14146](https://github.com/keepassxreboot/keepassxc/pull/14146), [#14147](https://github.com/keepassxreboot/keepassxc/pull/14147)). Whether they are accepted is up to the official project.

## About KeePassXC

KeePassXC is a password manager that stores usernames, passwords, URLs, attachments and notes in an offline, encrypted file that can be kept in any location. Entries are organised in groups, can be searched with advanced patterns, and a password and passphrase generator is included. It runs on Windows, macOS and Linux. Titanium keeps all of these features.

### Core features (inherited from KeePassXC)

* Create, open and save databases in the KDBX format (KDBX4 and KDBX3)
* Entries organised in groups, search, password generator
* TOTP storage and generation
* YubiKey/OnlyKey challenge-response support
* Auto-Type into applications
* Browser integration with Chrome, Firefox, Edge, Chromium, Vivaldi, Brave and Tor Browser, including passkeys
* Entry icon download
* Import from CSV, 1Password, Bitwarden, Proton Pass and KeePass1 formats

### Advanced features (inherited from KeePassXC)

* Database reports (password health, HIBP, statistics)
* Export to CSV, XML and HTML
* Field references, file attachments, custom attributes
* Entry history and restoration
* Command line interface (`keepassxc-cli`)
* SSH Agent integration and FreeDesktop.org Secret Service
* Additional encryption choices: Twofish and ChaCha20

Documentation of the official project: [Getting Started](https://keepassxc.org/docs/KeePassXC_GettingStarted.html) and [User Guide](https://keepassxc.org/docs/KeePassXC_UserGuide.html). Titanium-specific behaviour is described in [TITANIUM.md](./TITANIUM.md). For keyboard shortcuts see [KeyboardShortcuts.adoc](./docs/topics/KeyboardShortcuts.adoc).

## Building

See [INSTALL.md](./INSTALL.md). Titanium builds the same way as KeePassXC.

## Contributing

Changes are welcome as pull requests to this repository. Changes that also make sense for the official project can be sent to [KeePassXC](https://github.com/keepassxreboot/keepassxc); please read its [CONTRIBUTING](.github/CONTRIBUTING.md) guide and [Code of Conduct](CODE-OF-CONDUCT.md) first.

## Human Architecture Design + Generative AI = A Better Place

While still largely controversial, the fusion of human intuition with Claude's Generative AI (specifically Sonnet 5.5 & Second-Layer Collaboration with Opus 5.5) is being used as a hybrid approach to one of the most serious areas of security: The Password Vault. By leveraging the best of the best, this project hopes to attain an extremely reliable and secure platform in which anyone can store their passwords and secrets without fear of compromise or failure in day-to-day operations. Because this project enjoys the company of Claude, the commits carry a `Co-Authored-By` trailer, and pull requests to the official project will continue to be transparent in this manner.

## License

The original KeePassXC code is licensed under GPL-2 or GPL-3, and so are the Titanium changes. Additional licensing for third-party files is detailed in [COPYING](./COPYING).
