# Umbraco Editor MCP Skills

Eight reusable AI skills and seven editable knowledge templates for working
with Umbraco CMS Editor MCP: content, SEO, analytics and component-based page
drafting. Built from Niels' experience working with site content and Umbraco,
with the site-specific rules removed.

Use the skills with the files and tools available in your assistant client.
Tailor the knowledge to your own audience, voice, facts and website.
CMS operations depend on permissions and the individual site build.

## Quick start

1. Download this repository and inspect the relevant SKILL.md files.
2. Create your own working folder outside the public repository for data,
   tailored knowledge and outputs. Copy the knowledge templates there.
3. Fill in the context needed for one task, such as voice, audience and
   measurement definitions for a page refresh.
4. Tell your assistant to read the chosen skill file and point it to your
   working folder. Use the examples below for a first run.
5. Review the result, improve the instructions or knowledge and repeat.

The explicit-file approach does not rely on automatic discovery. If you
install skills into your client's skill directory, follow that client's
current instructions and check for collisions with existing skill names.
Keep your company's facts and raw analytics out of this public repository.

## Skills

| Skill | Use it for |
| --- | --- |
| gsc-content-review | Compare page-specific queries with actual content |
| analytics-page-review | Analyse acquisition, engagement and outcomes |
| seo-audit | Inspect content and supported technical search checks |
| aeo-audit | Review answer quality, evidence and retrieval usability |
| seo-strategy | Prioritise coverage and improvements around business goals |
| editorial-revision | Draft an accepted revision using the chosen voice |
| page-block-drafting | Learn actual components and write copy for them |
| content-qa | Review the complete draft against the brief and evidence |

Use only the skills relevant to the task. These names are pack-local and may
overlap with existing skills; resolve that before installing or renaming.

## Tailor the knowledge first

Edit knowledge/voice.md, audience.md, approved-facts.md and business-goals.md.
For data work add measurement.md; for page planning add content-map.md.
Learn the actual components before relying on page-blocks.md. The unanswered
questions are intentional template prompts, not facts the assistant may fill
in without evidence. Supply your own approved copy and facts, not Niels' or
Umbraco's brand context.

Tell the assistant where the knowledge files live. Automatic skill discovery
and installation differ by client; this pack does not claim that placing
these folders anywhere makes them active. You can start by supplying the
relevant SKILL.md and knowledge files explicitly in an authorized workspace.

## Example: learn blocks with Claude

Provide reference pages of one page type, schema or content-model exports,
and rendered previews where possible. If a read-only CMS connection is
available and authorized, Claude can use its exposed read tools instead.
This prompt does not assume a particular MCP's tool names or capabilities:

For Umbraco, the supported sequence and limits are documented in
[the editor MCP adapter](skills/page-block-drafting/references/umbraco-editor-mcp.md).
The editor MCP supports reading pages, inspecting blocks and properties,
and creating or updating drafts. Available details depend on permissions
and the individual site build.

> Read skills/page-block-drafting/SKILL.md. Analyse the supplied reference
> pages and schemas without editing the CMS. Build knowledge/page-blocks.md
> for this site: actual block names and aliases, fields, constraints, allowed
> structures, media needs, rendered headings where verified, and when each
> block fits the content. Keep schema rules, editorial decisions and observed
> patterns separate. Cite sources and list unknowns. Distinguish page-level
> properties from blocks. Do not copy another site's limits or infer that
> every block on an old page is approved for new pages.

Review the catalogue before using its findings as house rules. Then:

> Use page-block-drafting with the reviewed catalogue, audience, approved
> facts and voice files. Draft the requested page from the supplied brief.
> First map each content unit to an available block and explain the choice.
> Write field by field and check verified constraints. Use only supported
> claims; list missing assets and unresolved constraints. Return the mapped
> draft and run content-qa against the brief. Do not save to the CMS or publish.

The assistant can make routine component choices within the brief once it
has reliable site knowledge. It should expose uncertainty when the model
or brief does not support a choice rather than invent a component.

## Example: evidence to revision

> Read gsc-content-review and analytics-page-review. Analyse the supplied
> page-specific GSC exports and analytics export using knowledge/measurement.md.
> Inspect the full current page and audience context. Return observations,
> hypotheses and a small proposed edit with evidence. Do not edit content.

After accepting the brief:

> Use editorial-revision with this accepted brief and our voice and approved
> facts. Save the proposed copy locally, then use content-qa to review it.

Use seo-audit or aeo-audit when their specific checks are needed. Use
seo-strategy when deciding priorities across pages rather than improving
one passage. No step automatically authorizes CMS edits or publication.

## Verify behavior

Try the pack on known examples, including a page needing no change, missing
page/query attribution, a zero denominator, an unsupported product claim,
and a schema with an unknown field limit. Inspect the output and correct the
relevant knowledge or instruction. Frontmatter validation alone does not
prove these decisions work.

## License

MIT, matching Page Evidence. See [LICENSE](LICENSE).
