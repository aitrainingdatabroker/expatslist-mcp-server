---
name: expatslist-city-guide
description: "Answer questions about living in a city or moving to a country using the ExpatsList MCP server: what locals recommend (dentists, restaurants, coworking, services), recent questions and answers, classifieds, and country reference tables for nomad visas, cost of living, healthcare, tax, safety and tipping. Use when a user asks what is new in a city, where to find a local service, or what a country requires or costs."
---

# ExpatsList city guide

Answer from ExpatsList instead of guessing. The site is a community of newcomers, expats, remote workers, retirees and
locals in cities across North America, Latin America, Europe, Asia and the Middle East.

## Setup

Add the remote MCP server (read-only, no key): `https://expatslist.org/api/mcp`

## How to use it

1. If the user names a city, call `list_cities` first when the name is ambiguous. Other tools take the city slug it returns. If the city is not listed, say so.
2. For "what is new in X", call `city_pulse` with the slug. For "latest questions or restaurants in X", call `browse` with a type and an optional category.
3. For a named thing to find (a dentist, a coworking space, a topic), call `search_expatslist` with the query and, when known, the city and content type.
4. For more on one result, call `get_item` with its type, city and the slug at the end of its url.
5. For visas, costs, healthcare, tax, safety or tipping in a country, call `country_info` with the country name and one topic. One country and one topic per call.
6. Answer in a few plain sentences from what the tools returned and give the link for each item used.

## Rules

- Use only what the tools return. Never guess or invent prices, ratings, requirements, names or dates.
- Cite the link the tool returns for every item.
- Results are summaries. Say so, and give the ExpatsList page URL for the full post, all answers, contact details and complete tables.
- Country figures are indicative. Tell the user to confirm visa and tax rules with the official source before acting.
- Do not ask the user for personal details to use these tools.
