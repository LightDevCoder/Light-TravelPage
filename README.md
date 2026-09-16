# Light-TravelPage

A fictional Hangzhou travel page used to verify the reusable `light-travelpage` Skill.

Hosted at https://light-travelpage.pages.dev (demo access code: `demo`, prefilled on the sign-in page). Runtime data is stored in Cloudflare D1 and shared by group members: travelers, bills, currency settings, tasks and ticket status. There is one equal-access travel group per deployment. The map is schematic.

This repository contains only fictional itinerary and ticket examples. Access codes, signing secrets and local recovery files are excluded. Retrieve access material from the local project owner's protected file, not from this repository.

## Development and deployment

Use Node 22.13+ (the test suite uses node:sqlite), then `npm ci`, `npm test` and `npm run build`. For local preview configure `.dev.vars` with development-only `ACCESS_CODE_HASH` and `SESSION_SECRET`, apply `migrations/0001_state.sql` to local D1, then run `npm run preview`.

Cloudflare project and D1 binding are declared in `wrangler.jsonc`. Production secrets are configured in Cloudflare. Deploy the validated artifact with `npm run deploy` using authorized Wrangler credentials. GitHub stores source; deployment currently uses Wrangler, not automatic GitHub push deployment.

See ATTRIBUTION.md and LICENSE for upstream provenance. This is a working demo, not a booking service. Actual mobile browser acceptance and Skill admission are tracked separately in the authoring workspace.
