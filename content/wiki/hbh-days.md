# HBH Days

**Primary field:** Id

Day-level scaffolding for the Hour-by-Hour itinerary. One record per day per program. HBH Blocks (individual itinerary line items) attach to a Day record, which in turn attaches to a Program. Days are created automatically when the HBH is imported from the I&B sheet — do not create or delete them manually.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Auto-generated label: "Day N : Date Formula \| Program Name". Primary display identifier. |
| **Day #** | formula | Returns "Day N" from the Day Number. Display label for views. |
| **Program** | link → Programs | The Program this day belongs to. |
| **Program Name** | lookup | Program Name pulled from the linked Program. |
| **Start Date (from Program)** | lookup | Program Start Date pulled from the linked Program. Used to calculate the day's calendar date. |
| **Day Number** | number | Sequential day number within the program (Day 1 = arrival day). Used in the date formula and in the Id. |
| **Date** | date | Manual date entry for this day, if set independently of the formula. Used for HBH creation Automation. No need to modify. |
| **Date Formula** | formula | Calculated calendar date: Program Start Date + (Day Number − 1). This is the authoritative date for each day. |
| **HBH Blocks** | link → HBH Blocks | All itinerary blocks scheduled on this day. |
| **# of Activities** | count | Number of HBH Blocks linked to this day. |

## Related tables

- **Programs** — each day belongs to one program
- **HBH Blocks** — the individual itinerary items that make up the day

## Notes

- Days are created automatically during HBH import. Do not add, edit, or delete Day records manually — changes will be overwritten or will break the itinerary sequence.
- The Date Formula is always correct as long as Program Start Date | SOT is set on the Program. The manual Date field is redundant and can be ignored.
