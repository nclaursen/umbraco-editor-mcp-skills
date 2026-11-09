# Umbraco Editor MCP Skills

Twelve reusable AI skills and eight editable knowledge templates for content
work with Umbraco CMS Editor MCP. This is Niels' independent community pack,
not an official Umbraco distribution. It uses plain skill folders: no plugin
or marketplace setup is required.

The CMS-facing skills combine editorial judgement with task-specific Editor
MCP references. Three companion skills use supplied search/analytics evidence
and business context. You can also work from saved pages and exports; state
which live checks are unavailable. CMS operations depend on permissions,
enabled tools and the individual site build.

## Quick start

1. Download this repository and read the relevant `SKILL.md`.
2. Create a working folder outside the public repository for your data,
   tailored knowledge and outputs. Copy the needed `knowledge/` templates.
3. Fill in the context for one task: audience, voice, approved facts and goal.
4. Tell your assistant to read the skill and point it to your working folder.
   For CMS work, connect your Editor MCP through your client's supported setup.
5. Start with one of the workflows below and inspect the result.

Supplying the files explicitly does not rely on automatic skill discovery.
If installing into your client's skill directory, follow that client's
instructions and check for naming collisions. Install the complete skill
folder, including `references/`. Skills do not install or configure the MCP.
Keep company facts and raw analytics out of this public repository.

## Skills

### CMS-facing skills

| Skill | Use it for |
| --- | --- |
| [umbraco-page-drafting](skills/umbraco-page-drafting/SKILL.md) | Learn actual blocks, map a brief and create a requested unpublished page |
| [umbraco-seo-audit](skills/umbraco-seo-audit/SKILL.md) | Review intent, metadata and supported technical search checks |
| [umbraco-aeo-audit](skills/umbraco-aeo-audit/SKILL.md) | Review answer quality, evidence and retrieval usability |
| [umbraco-content-qa](skills/umbraco-content-qa/SKILL.md) | Check a complete draft, links, metadata, media and rendering |
| [umbraco-localisation-review](skills/umbraco-localisation-review/SKILL.md) | Find missing variants, compare translations or draft a requested variant |
| [umbraco-internal-link-review](skills/umbraco-internal-link-review/SKILL.md) | Suggest useful links with verified destinations and anchors |
| [umbraco-content-maintenance](skills/umbraco-content-maintenance/SKILL.md) | Review stale facts, expired content, overlap and ownership gaps |
| [umbraco-editorial-revision](skills/umbraco-editorial-revision/SKILL.md) | Implement an accepted change brief locally or in a requested CMS draft |
| [umbraco-campaign-page-brief](skills/umbraco-campaign-page-brief/SKILL.md) | Plan audience, offer, proof and action against available blocks |

Each has a conditional `references/umbraco-editor-mcp.md` with tool sequences
and limits. Read it when using Editor MCP, not for a files-only task.

### Companion skills

| Skill | Use it for |
| --- | --- |
| [gsc-content-review](skills/gsc-content-review/SKILL.md) | Compare page-specific GSC queries with actual content |
| [analytics-page-review](skills/analytics-page-review/SKILL.md) | Analyse exported acquisition, engagement and outcomes |
| [seo-strategy](skills/seo-strategy/SKILL.md) | Prioritise coverage and improvements around business goals |

The Editor MCP does not supply GSC or analytics metrics. Supply exports or
another authorized source. Strategy can use CMS content inventories, but
its priorities require business context and whatever supporting evidence is
available. These skills remain part of the pack; use only what the task needs.

## Tailor the knowledge

Start with `knowledge/voice.md`, `audience.md`, `approved-facts.md` and
`business-goals.md`. Add `measurement.md` for data work, `content-map.md` for
page planning and `terminology.md` for localisation. Learn the actual site
components before treating `page-blocks.md` as a catalogue.

Knowledge templates hold your site's context; skill references explain tool
workflows. Keep them separate. Unanswered template prompts are unknowns,
not permission to invent facts. Tell the assistant where your tailored files
live; no automatic loading of that folder is assumed.

## Featured workflow: brief to unpublished page

First learn the model from a small representative set of pages:

> Read skills/umbraco-page-drafting/SKILL.md and its Editor MCP reference.
> Inspect these reference pages and their page types without editing the CMS.
> Build knowledge/page-blocks.md in my working folder with actual aliases,
> fields, constraints, allowed structures and media needs. Separate verified
> schema rules from observed patterns and editorial choices. Cite sources
> and mark unknowns; do not infer rendered headings from block names.

Review the catalogue, then request the desired deliverable explicitly:

> Use umbraco-page-drafting with this brief and my reviewed site knowledge.
> Create an unpublished CMS draft under [parent ID], using [page type] in
> [culture]. Map the content to verified fields and blocks, then save it.
> Read back the fields and blocks and use umbraco-content-qa to check the
> complete draft. Return the page ID, saved changes and unresolved checks.
> Do not publish or schedule it.

For copy only, ask for the mapped draft without a CMS save. Draft creation
includes the necessary draft writes when requested; it does not require a
new confirmation for every tool call. Unknown model constraints still need
resolution before relying on them. Rendered QA needs a real preview.

## Featured workflow: section content health

> Use umbraco-seo-audit and umbraco-aeo-audit on [section/parent ID] in
> [culture]. Inspect a bounded set of pages and state coverage and versions.
> Return one prioritised list of evidenced issues with exact fields/passages,
> proposed fixes and unavailable checks. Include no change where appropriate.
> Do not edit the CMS.

The two audits remain separately usable. `audit-page-seo` and
`audit-page-content` support inspection; they are not a full crawl or an AI
visibility measurement. Tree depth alone is not a navigation defect.

If you want fixes saved, follow with:

> Save these accepted metadata changes as drafts on these page IDs. Preserve
> unrelated fields, cultures and existing draft changes. Read back each edit
> and report old/new values and partial failures. Do not publish.

`bulk-set-property` applies the same value to every selected page (up to 10
per call). Distinct titles/descriptions need individual updates.

## Featured workflow: localisation

> Use umbraco-localisation-review and my terminology.md. Find missing [target
> culture] variants under [parent ID], then compare these existing source and
> target variants. Preserve supported market adaptations. Return missing
> variants and proposed corrections without changing the CMS.

For a selected missing variant:

> Draft the [target culture] version of [page ID] from the approved [source
> culture] version and save it as an unpublished variant. Verify terminology,
> claims, metadata and local links. Preserve source and invariant fields.
> Report saved changes and anything requiring a language reviewer.

`copy-variant` copies rather than translates and overwrites target content.
Inspect the target first; replacing existing target work needs explicit
authorization for that overwrite. Do not create site languages or alter
fallback settings as part of translation work.

## Other editorial work

Use `gsc-content-review` and `analytics-page-review` with supplied exports to
form an evidenced change brief, then `umbraco-editorial-revision` and
`umbraco-content-qa` for the requested revision. Keep query and analytics
metrics in their own scopes.

Use `umbraco-internal-link-review` for useful connections and
`umbraco-content-maintenance` for keep/update/investigate/merge/archive
candidates. A reference report alone does not prove a page is orphaned or
safe to remove. Use `umbraco-campaign-page-brief` before drafting a campaign
page; planning does not create pages, forms or tracking.

Review requests are read-only. Requested CMS edits use draft operations and
read-back verification; they do not authorize publication, scheduling,
deletion, URL changes or edits outside the task. Preserve existing work and
report partial completion instead of claiming multi-call atomicity.

## Compatibility, migration and verification

The nine CMS-facing skills now have `umbraco-` prefixes. `page-block-drafting`
became `umbraco-page-drafting`; the other eight retain their previous names
with the prefix added. Update saved prompts and installations, remove the
old installed copies, and retain your private knowledge files. The three
companion skill names are unchanged.

Tool references were checked against the
[official Editor MCP tools](https://docs.umbraco.com/umbraco-in-ai/mcp/mcp-servers/cms-editor-mcp/available-tools.md)
on November 9, 2026. This is documentation verification, not a live integration
test or a claim of compatibility with every CMS/client version. Use the
current session's registered schemas; consult current documentation when
capabilities differ. This pack has its own changes rather than a version
number tied to an Umbraco major.

See [TESTING.md](TESTING.md) for reproducible behaviour scenarios and the
verification record, and [CHANGELOG.md](CHANGELOG.md) for pack changes.

## License

MIT. See [LICENSE](LICENSE).
