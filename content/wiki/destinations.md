# Destinations

**Primary field:** Id

Destination-level knowledge base — country, city, or regional entries that Programs and I&B Requests point to. Each destination aggregates the locations, vendors, scouting reports, and field staff expertise tied to that geography. Rich text fields are used to document standing knowledge (travel logistics, weather, safety) that informs every program built in that destination.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Mirrors Destination Name. Primary display identifier. |
| **Destination Name** | singleLineText | Name of the destination (e.g. Japan, Marseille, Cartagena, America South). Can be a country, city, or region. |
| **Country** | link → Countries | The country this destination falls within. Drives the Country lookup on Programs. |
| **Currency** | lookup | Local currency pulled from the linked Country. |
| **Exchange Rate to USD** | lookup | Exchange rate pulled from the linked Country's currency. |
| **Programs** | link → Programs | All Programs running in this destination. |
| **Locations** | link → Locations | Specific places (city, town, neighborhood, site) within this destination. |
| **I&B Requests** | link → I&B Requests | I&B Requests that have been built for this destination. |
| **Vendors** | link → Vendors | Vendors operating in this destination. |
| **Field Staff \| Country Coordinator** | link → Field Staff Profiles | Field staff designated as Country Coordinator for this destination. |
| **Field Staff Profiles** | link → Field Staff Profiles | Field staff with expertise in this destination (not necessarily CC-designated). |
| **Overall Summary** | richText | High-level overview of this destination — what makes it compelling, its character, typical program profile. |
| **Travel & Logistics** | richText | Visa requirements, airport info, arrival/departure procedures, permits, typical transit options. |
| **Weather Seasons** | richText | Year-round climate summary — rainy season, dry season, temperature ranges, what to expect month by month. |
| **Peak / High Seasons to Avoid** | richText | Periods to avoid due to tourism crowds, pricing spikes, or local events and holidays that would conflict with a program. |
| **Safety Considerations** | richText | Standing safety notes for this destination — areas to avoid, common risks, medical facilities, emergency contacts. |
| **Cultural Considerations** | richText | Cultural norms, etiquette, local customs, and sensitivities relevant for school groups. |
| **Other Notes** | multilineText | Miscellaneous notes that don't fit the structured fields above. |
| **Country Code** | lookup | Country dialing code pulled from the linked Country record. |
| **Destination Attachments** | multipleAttachments | Supporting files — maps, guides, reference documents for this destination. |

## Related tables

- **Countries** — each destination belongs to one country
- **Programs**, **I&B Requests** — the program pipeline starts with a destination selection
- **Locations**, **Vendors** — the operational detail underneath the destination
- **Field Staff Profiles** — country coordinators and expertise links

## Notes

- If a destination isn't in this table, it must be created here before it can be selected on an I&B Request or Program. Keep naming consistent to stay organized.
- The knowledge fields are standing documentation — update them after each scouting report or debrief that surfaces new information.
