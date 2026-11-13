# Ridge Pack

Free tools a UK roofer's AI assistant uses on the job: roof take-offs and materials, pitch and headlap checks, weather windows by postcode, building regulations and Part L, working at height plans and storm damage triage.

**Endpoint:** `https://ridge-pack.nerolabs.workers.dev/mcp` (MCP, Streamable HTTP)
**Sign-in:** None. No account, no key and no sign-in: add the address and use it.
**How to connect:** https://ridge-pack.nerolabs.workers.dev/docs
**Privacy:** https://ridge-pack.nerolabs.workers.dev/privacy
**Support:** founder@neroengine.com

## Tools

| Tool | What it does |
|---|---|
| `list_capabilities` | What Ridge Pack can do. Lists Ridge Pack's tools, what it covers (nations, roof shapes, coverings, job types) and what it deliberately does not do. |
| `roof_takeoff` | Roof area and materials take-off. Works out a pitched roof's slope area, rafter length, ridge, hips, eaves and verges from the plan size and pitch, then a materials list: tiles or slates, battens, underlay rolls, ridge and hip tiles, hip irons, valleys, nails, eaves trays,... |
| `check_pitch_headlap` | Pitch, headlap and gauge sanity check. Checks a roof covering type against the pitch, the headlap and the batten gauge: is the pitch below the typical minimum for that kind of tile or slate, is the headlap enough for the exposure, does the gauge leave the headlap you want. |
| `weather_window` | Weather window for roof work. Gets the hourly forecast for a UK postcode (today and up to 8 days ahead, from MET Norway) and checks each working hour against wind, gusts, rain, frost and the material's limits for the job type (tiling, membranes and sheets, torch-on,... |
| `check_building_regs` | Building regulations, Part L and planning flags. England and Wales. Says whether a roofing job is notifiable to building control (re-covering 25% or more of a roof, a change of covering, structural work, rooflights, dormers, solar, new roofs), whether Part L wants the whole roof... |
| `work_at_height_plan` | Working at height checklist and job risk note. Builds the working at height and scaffold checklist for a roofing job (hierarchy of controls, scaffold to TG20 with guardrails, 7-day inspections, ladders only for short work, roof ladders, flat roof edges, fragile surfaces, power lines,... |
| `storm_triage` | Storm damage and leak triage. Triage for storm damage and roof leaks. |
| `trade_profile` | Check the roofer's business details. Checks the roofer's own business details (Nero Trade Profile v1: trading name, Companies House number, competent person scheme and number, postcode, contact) and returns them cleaned, with a stable `nero_trade_ref` computed from the scheme... |

Every tool carries a plain title and the read-only, destructive and open-world hints, so your AI app can ask before anything that changes data.

## Connect

- **Claude (web or desktop):** Settings, Connectors, Add custom connector, paste the endpoint.
- **ChatGPT:** Settings, Apps and connectors, Advanced settings, switch on Developer mode, then Create, paste the endpoint, No authentication.
- **Claude Code:** `claude mcp add --transport http ridge-pack https://ridge-pack.nerolabs.workers.dev/mcp`
- **Cursor, VS Code, Windsurf and others:**

```json
{ "mcpServers": { "ridge-pack": { "type": "http", "url": "https://ridge-pack.nerolabs.workers.dev/mcp" } } }
```

## Try asking

- "Take off materials for a 9 by 7 metre gable roof at 35 degrees in concrete interlocking tiles."
- "Is it safe to lay membrane in BS1 4DJ on Monday and Tuesday? Show me the gusts."
- "A customer has 12 tiles missing after the storm and more rain is due tonight. How urgent is it?"

## Good to know

- Built for UK roofers. Every answer shows its working and sources and lists what the trade must check. The trade doing the work stays responsible for it.
- Free forever: no sign-up, no key, no daily cap, no paid plan.

## Privacy

What is kept, what is never kept, and how to get data deleted: https://ridge-pack.nerolabs.workers.dev/privacy. Usage counts log the tool name, time, AI app name, country and a one-way scrambled caller code; never your questions, the answers or IP addresses.

This repository holds the listing only (README and server.json). The server runs at the endpoint above.

Built by Nero Labs (Nero Engine Group Ltd, UK).
