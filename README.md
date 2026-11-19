# AutoRepair Cloud MCP server for ChatGPT and Claude

Cotlet.dev connects AutoRepair Cloud to ChatGPT, Claude and other AI agents through your own signed-in Cloud Browser.
The AutoRepair Cloud integration page reports no public API documentation, official MCP server or official ChatGPT or Claude connector, checked 17 November 2026.

## What can I ask my agent to do?

- Turn a customer concern into a repair quote for your approval.
- Find repairs waiting for parts and review workflow delays.
- Review workshop bookings, technician hours and daily sales.
- Find customer vehicles and their repair history.

Quotes, orders, payments and anything a customer sees wait for your approval.

## How do I connect AutoRepair Cloud to ChatGPT or Claude?

1. [Sign up for Cotlet.dev](https://cotlet.dev/signup?app=autorepair-cloud).
2. Enable AutoRepair Cloud and sign in at autorepaircloud.com/login in your Cotlet.dev Cloud Browser.
3. In ChatGPT, open Settings > Apps & Connectors > Create. In Claude, open Settings > Connectors > Add custom connector.
4. Add `https://cotlet.dev/mcp/v1/connect` and sign in to Cotlet.dev with OAuth.

Refresh the connector after enabling AutoRepair Cloud.

## Can I connect an editor or a script?

Use `https://cotlet.dev/mcp/v1` with an API key from your Cotlet.dev console.

```json
{"mcpServers":{"cotlet":{"url":"https://cotlet.dev/mcp/v1","headers":{"Authorization":"Bearer ${env:COTLET_API_KEY}"}}}}
```

## Can I run a local MCP bridge?

The included Python bridge forwards browser operations to the hosted Cotlet.dev MCP server.
It requires Python 3.10 or later and uses the standard library.
Its tools cover guidance, connection status, opening and reading a page, clicking, typing and closing the browser.
The hosted connector above is the recommended setup.

```bash
export COTLET_API_KEY="your-key"
python3 autorepair_cloud_agent.py serve
```

Run `python3 autorepair_cloud_agent.py connect` for configuration help.
Without a key, the bridge lists its tools and explains how to obtain a key when a tool is called.

## Is this official?

Cotlet.dev is independent and is not affiliated with, endorsed by or sponsored by AutoRepair Cloud.
AutoRepair Cloud is a trademark of its owner.

[AutoRepair Cloud integration details and tool reference](https://cotlet.dev/integrations/autorepair-cloud-api-mcp-server?utm_source=github&utm_medium=readme&utm_campaign=autorepair-cloud).
