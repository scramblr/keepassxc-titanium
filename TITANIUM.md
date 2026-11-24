# KeePassXC Titanium

A fork of [KeePassXC](https://github.com/keepassxreboot/keepassxc) with additional data-integrity, hardening and
performance changes. It is rebased on upstream `develop` regularly.

## Branches

| Branch | Purpose |
|---|---|
| `master` | The Titanium product: upstream `develop` plus all Titanium changes. Start here. |
| `develop` | Unmodified mirror of upstream `develop`, used as the base for `master`. |
| `fix/xml-export-import`, `fix/csv-export-import` | Cleaned, brand-neutral subsets offered to upstream as pull requests ([#14146](https://github.com/keepassxreboot/keepassxc/pull/14146), [#14147](https://github.com/keepassxreboot/keepassxc/pull/14147)). Do not rename: the pull requests depend on these names. |

## What Titanium adds

- **XML export/import without data loss:** complete export (attachments, history, settings), streaming export with a low
  memory peak, import wizard type with a settings checklist, exact round trip of control characters, UUID-collision
  handling.
- **CSV export/import without dropped columns:** all entry data is exported, every exported column is imported, unknown
  columns are kept as custom fields, large files parse in linear time, a warning is shown before a lossy export.
- **XML reader hardening:** protected values without a stream, duplicate group and entry UUIDs, nesting depth limit,
  out-of-range binary dates.
- **Browser integration:** credentials are found in every connected unlocked database, stricter input checks for
  requests from web pages and local clients, database-scoped actions are bound to the database the client associated with.
- **Performance and leaks:** tag-list rescans are throttled, an icon-picker leak is fixed, a URL pattern is compiled once.
