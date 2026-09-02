# HBH Categories

**Primary field:** Name

Category tags for HBH Blocks. Each block is assigned one category, which determines which cost rollup field on Programs it feeds into (Accommodations, Meals, Transportation, Activities, Internal Flights, Other, etc.). Also used to tag Vendor Listings by service type.

## Fields

| Field | Type | Description |
|---|---|---|
| **Name** | singleLineText | Category name (e.g. Accommodations, Meals, Transportation, Activities, Internal Flights, Other). Primary field. |
| **HBH Blocks** | link → HBH Blocks | All HBH Blocks tagged with this category. |
| **Record ID** | formula | Returns the Airtable record ID. Used internally for cross-table references. |
| **Vendors** | link → Vendors | Vendors associated with this service category. |

## Related tables

- **HBH Blocks** — blocks are tagged with one category each
- **Vendors** — vendors are associated with the categories they serve

## Notes

- OPS make sure no new categories are created in the I&B sheet. They will pass through the import, and will be created but will cause errors in financial calculations.
- Category names must match exactly what the Programs cost rollup formulas and filters expect. Do not rename categories without checking rollup conditions on Programs first.
- The standard categories are: Accommodations · Meals · Transportation · Activities · Internal Flights · Other · Flights (used for international flights in Budget rollup). Additional categories may exist for edge cases, but must be approved by system manager.
