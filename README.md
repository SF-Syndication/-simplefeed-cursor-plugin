# SimpleFeed for Cursor

Search **rights-cleared news and video** from hundreds of publisher catalogs directly in [Cursor](https://cursor.com). This plugin bundles SimpleFeed **Paid** and **Free Discovery** MCP servers.

Billing is through **AWS Marketplace** — not through Cursor.

## MCP servers included

| Server | Plan | MCP URL |
|--------|------|---------|
| `simplefeed-paid` | Paid MCP | `https://dsyf7237b1hl8.cloudfront.net/mcp` |
| `simplefeed-free` | Free Discovery | `https://d3b8d1lqb9mb0.cloudfront.net/mcp` |

## Before you connect

1. **Subscribe** on AWS Marketplace:
   - [Paid MCP](https://aws.amazon.com/marketplace/pp/prodview-vi266fgii3oms)
   - [Free Discovery](https://aws.amazon.com/marketplace/pp/prodview-rj5jqhfy33ieo)
2. **Register** using the link AWS sends after purchase. You receive an API key on the success page.
3. **Link your account** on that page (**How to use (OAuth)**): create a login or sign in with the **same email and password** you will use in Cursor.
4. Install this plugin (Marketplace or local), enable the MCP server for your plan, and sign in with that same email and password when prompted.

Full guide: [SimpleFeed MCP for Cursor](https://d2fc02tchkjlk2.cloudfront.net/cursor-connectors-docs.html) · [Claude guide](https://d2fc02tchkjlk2.cloudfront.net/claude-connectors-docs.html)

## Install from Cursor Marketplace

After the plugin is published, install from [Cursor Marketplace](https://cursor.com/marketplace) or submit this repo at [cursor.com/marketplace/publish](https://cursor.com/marketplace/publish).

## Install locally (development / review)

```bash
git clone https://github.com/SF-Syndication/-simplefeed-cursor-plugin.git
cd -- -simplefeed-cursor-plugin
ln -s "$(pwd)" ~/.cursor/plugins/local/simplefeed
```

Reload Cursor (**Developer: Reload Window**), then open **Settings → Features → Model Context Protocol** and enable `simplefeed-paid` or `simplefeed-free`.

## OAuth in Cursor

SimpleFeed uses OAuth 2.0 with dynamic client registration. You do **not** paste your API key into Cursor when using OAuth.

When connecting, you may see a short **setup page** (Marketplace instructions) before sign-in. Use the same email and password you set on the registration **How to use (OAuth)** step.

## Alternative: API key (advanced)

For scripts or clients that send headers instead of OAuth, set an environment variable and use a custom `mcp.json` entry:

```json
{
  "mcpServers": {
    "simplefeed-paid": {
      "url": "https://dsyf7237b1hl8.cloudfront.net/mcp",
      "headers": {
        "X-Api-Key": "${env:SIMPLEFEED_API_KEY}"
      }
    }
  }
}
```

## Example prompts

```
Show me which news publisher catalogs I can search.

Search for recent articles about renewable energy policy in the United States. Return up to 5 results with titles and summaries.

Find sports news from the last 3 days that mentions the NFL playoffs. Limit to 10 articles.
```

## Tools

- **Search articles and video** — semantic search with filters (publisher, date, category, full text on Paid)
- **List publishers** — catalogs available for your subscription

## Support

- Email: support@simplefeed.com or ai@simplefeed.com
- Website: https://www.simplefeed.com/
- Privacy: https://www.simplefeed.com/other/privacy-policy/

## License

MIT — see [LICENSE](LICENSE).
