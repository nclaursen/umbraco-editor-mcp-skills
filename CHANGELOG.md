# Changelog

## Unreleased — November 9, 2026

- Prefix the nine CMS-facing skills with `umbraco-` to reduce naming collisions;
  rename `page-block-drafting` to `umbraco-page-drafting`. Keep all 12 skills.
- Add explicit activation descriptions and task-specific Editor MCP references.
- Extend page drafting and localisation to cover requested unpublished CMS
  drafts while preserving copy-only and review-only modes.
- Feature page drafting, section health and localisation workflows in the
  README without merging the underlying editorial skills.
- Document variant overwrite risks, same-value bulk edits, read-back checks,
  partial failures and the limits of CMS audit/relationship evidence.
- Keep site knowledge separate from operational references. Add behaviour
  scenarios and distinguish documentation checks from live integration tests.

Existing installations need their old CMS-facing skill folders replaced;
see the README migration notes. No marketplace or plugin packaging is added.
