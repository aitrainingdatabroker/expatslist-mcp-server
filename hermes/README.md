# ExpatsList for Hermes

Adds the public, read-only [ExpatsList](https://expatslist.org) MCP server and one skill that tells the agent how to
use it. Ask what is new in a city, find a dentist or a coworking space that locals recommend, read a question and its
best answer, or look up a country's nomad visa, cost of living, healthcare, tax, safety or tipping table. Every answer
comes with the ExpatsList page link for the full text.

- **Server:** `https://expatslist.org/api/mcp` (Streamable HTTP, no key, no sign-in)
- **Disclosure:** every tool call goes to expatslist.org. The tools only read what the site publishes and write nothing. No key is needed. No local commands are run and nothing is installed beyond configuration and a skill. No telemetry beyond ordinary server logs. The tool list is served by the remote server at runtime and is not covered by the pinned commit of this repository.
- **Skill:** `skills/expatslist-city-guide`

More links: [home](https://expatslist.org), [cities](https://expatslist.org/cities), [blog](https://expatslist.org/blog), [tools](https://expatslist.org/tools).
