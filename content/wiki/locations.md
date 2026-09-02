# Locations

**Primary field:** Name

Specific venues and sites within a Destination — hotels, restaurants, activity sites, transit hubs, etc. HBH Blocks link to a Location to record where each itinerary item takes place. Rich text fields document standing knowledge about the location to inform future program builds.

## Fields

| Field | Type | Description |
|---|---|---|
| **Name** | singleLineText | Name of the venue or site (e.g. "Hotel Dann Carlton", "El Peñón de Guatapé", "Medellín Metro"). Primary field. |
| **Destinations** | link → Destinations | The destination this location belongs to. |
| **HBH Blocks** | link → HBH Blocks | All HBH Blocks scheduled at this location. |
| **Description** | richText | Overview of the location — what it is, what it offers, why it's used for programs. |
| **Program Relevance & Associated Themes** | richText | How this location connects to Envoys program themes and learning objectives. |
| **Access & Travel Time** | richText | How to get here — transit options, drive times from common arrival points, access notes. |
| **Seasonal Trends: Weather & Tourism** | multilineText | When this location is best (or worst) to visit — crowds, weather, closures. |
| **Activities Trends** | richText | What activities are typically run at this location and any operational notes (capacity, booking lead time, etc.). |
| **Safety & Cultural Considerations** | richText | Site-specific safety notes and cultural context relevant for school groups. |
| **Additional Notes** | richText | Any other relevant information about this location that doesn't fit the structured fields above. |
| **Vendors** | link → Vendors | Vendors that operate at or are commonly associated with this location. |

## Related tables

- **Destinations** — each location belongs to one destination
- **HBH Blocks** — blocks are placed at a location
- **Vendors** — vendors associated with this site

## Notes

- Create a new Location record whenever a new venue is used in an HBH, so future programs can reference it with standing knowledge attached.
- The Scouting field is a `singleLineText` orphan following the Scouting table restructure.
