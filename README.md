# Slaide MCP Server – AI Presentation Maker for PowerPoint, Word and Excel

[Slaide](https://www.slaide.de) is an AI presentation maker and slide deck generator. This MCP server connects your AI assistant to Slaide so it can **build, edit and export PowerPoint presentations, Word documents and Excel workbooks** straight from chat. Everything lands in your own Slaide library, where you can keep editing by hand.

- **Server URL:** `https://app.slaide.de/api/mcp`
- **Transport:** Streamable HTTP (remote, hosted by Slaide, nothing to install)
- **Authentication:** OAuth 2.1 with PKCE and Dynamic Client Registration. No API key or token to copy.
- **Account:** a free Slaide account is enough → [Sign up](https://app.slaide.de/registrieren)

## What you can ask your assistant

- "Make a 10-slide presentation about remote work best practices for my team meeting."
- "Turn the attached PDF report into a 10-slide presentation and export it as PowerPoint." ([PDF to PowerPoint](https://www.slaide.de/pdf-to-powerpoint))
- "Build a pitch deck from these bullet points." ([AI pitch deck generator](https://www.slaide.de/ai-pitch-deck-generator))
- "Turn this Word document into slides." ([Word to PowerPoint](https://www.slaide.de/word-to-powerpoint))
- "Write a report on Q3 results and export it as Word." ([AI report generator](https://www.slaide.de/ai-report-generator))
- "In my Q3 Business Review deck, change the revenue on page 2 to 4.8 million euros. Change nothing else."
- "Apply my brand kit to this presentation." ([On-brand presentations](https://www.slaide.de/on-brand-presentations))

## Features

- **Create** a finished, editable PowerPoint presentation from a topic, notes, or an attached PDF, Word, Excel or PowerPoint file, with your saved brand kit (logo, colors, fonts) applied if you have one.
- **Edit** single slides of an existing deck and leave the rest untouched. Every change an assistant makes is versioned and can be undone in Slaide.
- **Read** the slides, speaker notes and spreadsheet cells of your own documents, and find a deck by title or recency.
- **Export** to PowerPoint, PDF, Word, PNG or Excel behind a private link that expires after 15 minutes.
- **Background jobs:** long builds run as jobs; the assistant checks progress and can cancel a running job.
- **Safe by design:** the connector only works on your own library. It cannot delete documents, buy anything, change a plan or reach other people's documents.

## Tools

| Tool | What it does |
|---|---|
| `search_documents` | Lists your decks by title or recency |
| `get_document` | Reads the pages, speaker notes or cells of one of your documents |
| `create_document` | Starts a background job that builds a new presentation, document or workbook |
| `update_document` | Changes pages of an existing document (versioned, restorable in Slaide) |
| `get_job` | Reports progress and the result of a job |
| `export_document` | Produces a PowerPoint, PDF, Word, PNG or Excel file behind a private link that expires after 15 minutes |
| `cancel_job` | Stops a running job |

## Setup

Any MCP client that supports remote Streamable HTTP servers and OAuth 2.1 can connect. The first time a Slaide tool is used, the client opens Slaide's sign-in page; sign in and press **Allow**.

Generic client configuration:

```json
{
  "mcpServers": {
    "slaide": {
      "url": "https://app.slaide.de/api/mcp"
    }
  }
}
```

**Cursor:** the same snippet in `.cursor/mcp.json`, or install the [Slaide Cursor plugin](https://github.com/Lugier/slaide-cursor-plugin).

**Hermes Agent:** add to `~/.hermes/config.yaml`:

```yaml
mcp_servers:
  slaide:
    url: https://app.slaide.de/api/mcp
    auth: oauth
```

To disconnect, open Slaide → Settings → Account → AI assistants. Access stops immediately.

More setup guides: [Slaide for AI assistants](https://www.slaide.de/ai-assistants).

## Listings

- Official MCP Registry: `de.slaide/slaide`

## Links

- Website: [slaide.de](https://www.slaide.de)
- AI presentation maker: [slaide.de/ai-presentation-maker](https://www.slaide.de/ai-presentation-maker)
- Examples: [slaide.de/examples](https://www.slaide.de/examples)
- Pricing: [slaide.de/pricing](https://www.slaide.de/pricing)
- FAQ: [slaide.de/faq](https://www.slaide.de/faq)
- Help center: [help.slaide.de](https://help.slaide.de)
- Privacy: [slaide.de/privacy](https://www.slaide.de/privacy) · Terms: [slaide.de/terms](https://www.slaide.de/terms)
- Support: info@slaide.de

## License

The files in this repository are MIT-licensed (see `LICENSE`). Using the Slaide service is governed by the [Slaide terms](https://www.slaide.de/terms).
