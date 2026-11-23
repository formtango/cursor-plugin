# FormTango plugin for Cursor

Teaches Cursor's agent to add a working form to any site, and connects it to FormTango so it can create forms and read submissions.

[FormTango](https://formtango.com) is a form backend: your form posts to one address, and every submission is stored in an inbox, checked for spam and emailed to you. No server code, no API key.

## What is inside

- **A skill** (`skills/formtango`): how to create a form endpoint with no signup, wire it into HTML or a framework, and verify it with a test submission. Invoke it with `/formtango` or let the agent pick it up when you ask for a form.
- **An MCP server** (`mcp.json`): the FormTango server at `https://formtango.com/mcp`, with tools to create forms (`create_form`), list them (`list_forms`), fetch framework snippets (`get_form_snippet`) and list submissions (`list_submissions`). The first time it is used, Cursor opens a browser window to sign in to FormTango and approve access (OAuth). It appears in Cursor as `plugin-formtango-formtango`.

No configuration or API key is needed. The skill also works without signing in: it can create a form with no account and gives you a link to claim it.

## Install

From the Cursor Marketplace: search for **FormTango** and click **Add to Cursor**.

To try it locally before it is listed:

```bash
mkdir -p ~/.cursor/plugins/local
git clone https://github.com/formtango/cursor-plugin ~/.cursor/plugins/local/formtango
```

Then restart Cursor (or run **Developer: Reload Window**) and check the skill and MCP server under **Customize**.

Or add only the MCP server to `~/.cursor/mcp.json`:

```json
{
  "mcpServers": {
    "formtango": { "url": "https://formtango.com/mcp" }
  }
}
```

## Use

Ask: "Add a contact form to this site."

The agent creates a form endpoint, adds the form to your page, sends one test submission and tells you where submissions go.

## Links

- Guide for AI tools: https://formtango.com/ai.md
- Docs index for LLMs: https://formtango.com/llms.txt
- Claude Code plugin: https://github.com/formtango/claude-plugin

## License

MIT
