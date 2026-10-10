# Umbraco CMS Editor MCP adapter

Read only when using page-block-drafting with an Umbraco CMS Editor MCP.

## Verification scope

Checked October 10, 2026 against the official tool reference and overview:

- https://docs.umbraco.com/umbraco-in-ai/mcp/mcp-servers/cms-editor-mcp/available-tools.md
- https://docs.umbraco.com/umbraco-in-ai/mcp/mcp-servers/cms-editor-mcp.md
- https://docs.umbraco.com/umbraco-in-ai/mcp/cms-editor-mcp/scenarios

Documentation verification only; no live integration test. Use the actual
registered tool names and schemas in the session. Availability depends on
permissions and server settings.

## Read and draft

- Locate reference pages using search-content or list-children. get-page
  returns page fields but summarizes block properties. Use inspect-blocks
  for block types, keys and values. Library elements use
  inspect-element-blocks instead.
- get-document-type exposes editable page properties. Do not assume it also
  supplies every data-type limit, block restriction or unused component.
- Write the learned catalogue locally using the assistant client's file
  capabilities. The editor MCP is not documented as a local knowledge-file
  manager or SKILL.md installer.
- Prepare copy and its content-to-block map before a CMS write. create-page
  creates a draft; edit-page saves without publishing. add-blocklist-block,
  add-blockgrid-block and add-rte-block add blocks as drafts. Inspect blocks
  before edit-block and use verified identifiers. get-property-value-template
  supplies supported non-block structured-value shapes, including pickers.
- Read back page values and blocks. compare-draft-to-published supports a
  property-level diff but summarizes blocks; inspect-blocks is still needed
  for a detailed comparison. Publishing uses separate tools.

## Boundaries

Missing constraints need site configuration exports or developer-supplied
knowledge. Rendered headings, layout and responsive behavior require actual
rendering evidence; content JSON alone is insufficient.

GSC and analytics exports come from uploads, files or another authorized
source. Editor SEO audit tools supply bounded page data, not a full crawl
or an AEO visibility measurement. AEO assessment is assistant reasoning.

Draft operations do not establish a multi-step atomic transaction. Preserve
existing edits, verify each result and report partial completion. Permission
to edit does not establish permission to create under every parent or publish.
