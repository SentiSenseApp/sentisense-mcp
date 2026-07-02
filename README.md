# SentiSense MCP Connector

**Market intelligence for the most-watched US stocks, right inside Claude and ChatGPT.**

SentiSense is a hosted [Model Context Protocol](https://modelcontextprotocol.io) (MCP) server. Add one URL and your AI assistant can answer questions about US market mood, a stock's sentiment and the SentiSense Score, market-moving news, analyst ratings, and institutional flows, in plain English.

- **Connector URL:** `https://app.sentisense.ai/mcp`
- **Auth:** zero-config OAuth (no API key to paste)
- **Access:** read-only. Nothing is ever written, moved, or traded.
- **Learn more:** https://sentisense.ai/connect

---

## Add the connector

### Claude

1. Open **Settings → Connectors**.
2. Add a custom connector and paste `https://app.sentisense.ai/mcp`.
3. Sign in with your SentiSense account and approve access.
4. Start a chat and ask about a ticker or the market.

### ChatGPT

1. Turn on **developer mode** under **Settings → Connectors** (this is what lets you add a connector by URL).
2. Add a connector and paste the same URL.
3. Sign in and approve access.
4. Ask your question in a new chat.

The exact menu labels shift between releases; look for "Connectors" and an option to add one by URL.

---

## Tools

Ask in plain English, your assistant picks the right tool.

| Tool | What it answers |
|------|-----------------|
| `get_market_mood` | The proprietary fear-to-greed composite for the US market, its phase, and the signal components. |
| `get_stock_snapshot` | Price plus SentiSense sentiment, the SentiSense Score, and key stats for a ticker. |
| `get_news` | Recent, sentiment-tagged market-moving news for a ticker, each with a link to the source. |
| `get_analyst_ratings` | The buy / hold / sell consensus and price targets for a ticker. |
| `get_smart_money` | Institutional 13F holdings and flows: who is buying and who is selling. |

All five are read-only. The server also exposes a lightweight `sentisense_health` connection check.

### Try these

- "What's the market mood right now?"
- "Give me a snapshot of NVDA with its SentiSense Score and recent news."
- "What do analysts think of TSLA, and what are the price targets?"
- "Which institutions are buying and selling AAPL?"

---

## Free vs PRO

The connector respects the tier of the SentiSense account you sign in with. Free accounts get preview data across every tool; PRO unlocks the full payloads through the same connection, with no reconnecting.

---

## Notes

- **Quotes are real-time; sentiment, market mood, and news are batch** (recomputed on a regular cadence).
- **Coverage spans the most-watched US stocks**, not every ticker.
- Building something? The connector is a read-only slice of the same data graph as the [SentiSense API](https://sentisense.ai/docs/api), which has typed SDKs and an agent skill for full programmatic access.
- For informational and educational purposes only. Not investment advice.

---

Built by the SentiSense team · [sentisense.ai](https://sentisense.ai)
