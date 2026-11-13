# Security

Report suspected vulnerabilities privately to info@slaide.de. Please do not open a public issue for a security report.

This repository holds only configuration and text: `plugin.json`, `mcp.json`, `lhm.plugin.json`, `server.json` and an agent skill. It contains no executable code and no credentials. The Slaide MCP server is a hosted service at `https://app.slaide.de/api/mcp`; it uses browser-based OAuth 2.1, and the client stores the tokens, not this repository.

## What the connector can do

- Read, create, update and export the signed-in user's own Slaide documents.
- It cannot delete documents, change a plan, buy anything or reach other people's documents.
- Creating or updating a document uses the user's Slaide plan allowance, the same as working in Slaide directly. Changes are versioned and can be restored in Slaide.
- Export files are delivered through a private link that expires after 15 minutes.
