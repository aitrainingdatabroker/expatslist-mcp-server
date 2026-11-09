# ExpatsList MCP server

A public, read-only [Model Context Protocol](https://modelcontextprotocol.io) server for
[ExpatsList](https://expatslist.org), a community site for cities across North America, Latin America, Europe, Asia
and the Middle East. It is used by newcomers, expats, remote workers, retirees and locals. The server lets an AI
client read what the site publishes: business listings recommended by locals, questions and answers about city life,
recommendations, classifieds, blog posts and country reference tables for visas, cost of living, healthcare, tax,
safety and tipping.

- **Server URL:** `https://expatslist.org/api/mcp`
- **Transport:** Streamable HTTP, stateless. Replies come as `text/event-stream`, so the JSON result is on the line that starts with `data:`.
- **Authentication:** none
- **Access:** read-only. Nothing is written by the tools.

## Tools

| Tool | What it does |
|---|---|
| `browse` | Newest items of one content type in one city: questions, missed-connection posts (human_connection), recommendations, classifieds, blog posts or businesses. Optional category filter. For businesses with no category it returns the category list with counts instead of items. At most 10 items per call. |
| `city_pulse` | Recent community activity in one city, grouped by type with up to five summaries each and a link to the full section. Covers only the last 1 to 90 days and only cities from `list_cities`. |
| `country_info` | Reference numbers for one country and one topic: nomad_visa, cost_of_living, healthcare, tax, safety or tipping. Figures are indicative and the linked page has the full table and sources. |
| `fetch` | Connector-style fetch of one item by the id returned from `search`. Same summary as `get_item`. |
| `get_item` | One item by type, city and slug: a question with its best answer and the count of further answers, a missed-connection post, a recommendation, a classified, a blog post or a business listing. Text is a summary of up to about 600 characters; contact details are never included and are on the linked page. |
| `list_cities` | The cities ExpatsList covers, with the slug every other tool expects. It does not search content. |
| `search` | Connector-style search across all ExpatsList content. Returns ids for `fetch`. Prefer `search_expatslist` when you can filter by city or type. |
| `search_expatslist` | Keyword search across business listings, classifieds, blog posts, questions, recommendations and missed-connection posts, optionally limited to one city and one content type. Keyword match, not semantic; at most 10 results. |

Every result carries a link to the ExpatsList page. Results are summaries; the full post, all answers, contact
details and complete tables are on that page. The data is what the site publishes.

## Add it to your client

Add the server URL `https://expatslist.org/api/mcp` as a remote MCP server of type Streamable HTTP. No key is needed.

## Example questions

- Which cities does ExpatsList cover?
- Is there a dentist that locals recommend in Austin?
- What does Portugal's digital nomad visa require?
- What are healthcare costs in Thailand?

## Links

- Home: https://expatslist.org
- Cities: https://expatslist.org/cities
- Blog: https://expatslist.org/blog
- Tools: https://expatslist.org/tools
- About the MCP server: https://expatslist.org/developers/chatgpt
- Contact: https://expatslist.org/contact
- Privacy: https://expatslist.org/privacy
- Terms: https://expatslist.org/terms

## Hermes plugin

The `hermes/` folder holds a Hermes plugin entry (`plugin.json`, `mcp.json`) and one skill, `expatslist-city-guide`,
that teaches an agent how to use these tools.
