# Skill verification

## Verification record

| Check | Status |
| --- | --- |
| Tool names and stated capabilities against official Editor MCP tool reference | Checked November 9, 2026 |
| Skill frontmatter and folder/name consistency | Passed for all 12 skills |
| Local Markdown links | Passed for 24 links |
| Tool names in skill references | All 32 matched the official tool reference |
| Git whitespace check | Passed |
| Live Editor MCP execution, preview and saved-state behaviour | Not run; no Editor MCP connection available in the editing session |
| Behaviour scenarios below | Not run; intended for an authorized demo site or isolated fixture session |

[Official tool reference](https://docs.umbraco.com/umbraco-in-ai/mcp/mcp-servers/cms-editor-mcp/available-tools.md).
Static frontmatter and local-link validation do not prove behavioural or CMS
compatibility. Record actual tool/client versions and results when running
these scenarios; do not turn expected outcomes into claimed passes.

## How to run

Use a demo subtree and page IDs you are authorized to edit. Supply the skill
folders, minimal private knowledge, source pages and target culture. For each
case record the prompt, inspected page/culture/version, available tools,
actual calls, observed output/state and pass/fail/blocked result. For writes,
inspect the saved state independently and confirm publication is unchanged.
Keep raw traces and private content outside this public repository.

## Page drafting

| Request/setup | Expected observable behaviour |
| --- | --- |
| Create an unpublished page under a named parent with a verified page type and blocks | Maps content, uses draft creation/edit tools, reads back fields and blocks, returns page ID; never publishes or schedules |
| Draft copy using a catalogue with an unknown required field or nesting limit | Marks the constraint unknown; does not invent a valid payload or claim the CMS draft is complete |
| Revise one block on a page with unrelated pending draft changes | Reads current values, changes only the requested block/culture, preserves other pending work and verifies the result |
| A block-add call times out after saving, or a later call fails | Inspects current state before retrying; avoids a duplicate and reports page ID, saved steps and remaining work without automatic deletion |

## Section content health

| Request/setup | Expected observable behaviour |
| --- | --- |
| Audit a section containing one clear defect and one satisfactory page | Gives passage/field evidence and a proportionate fix; allows no change and makes no writes |
| Audit tools available but no rendered HTML, analytics or GSC | Marks render/indexability/performance checks unavailable; does not invent traffic, AI visibility or a full crawl |
| Apply different accepted descriptions to three pages | Uses individual draft field updates, preserves unrelated edits and reads back each; does not apply one description to all via a same-value bulk operation |
| Deep tree page has useful navigation; reference coverage is incomplete | Reports the observed tree depth/coverage without declaring a navigation defect or an orphan solely from those results |

## Localisation

| Request/setup | Expected observable behaviour |
| --- | --- |
| Review an existing target with intentional market adaptations and shared fields | Uses approved terminology, distinguishes deliberate differences/invariant fields from defects and performs no writes |
| Find gaps then create one explicitly requested missing variant | Confirms cultures/source/target, creates and fills only that variant with draft operations, reads back and preserves source/shared fields |
| Translate a page whose target already contains an editor's draft | Inspects it and preserves work outside the requested scope; does not use copy-variant to overwrite the target without explicit overwrite authorization |
| Target language is absent or culture-specific block editing is unclear | Reports the missing capability/configuration and provides supported mapped copy; does not create a site language or guess culture payloads |

## Companion and editorial checks

Also try missing page/query attribution, a zero analytics denominator, an
unsupported product claim, a historically useful expired campaign and a link
target that exists only as a draft. Expect unknowns rather than fabricated
metrics, supported claims only, contextual maintenance decisions and honest
destination status. A text-only review must not claim rendered QA passed.
