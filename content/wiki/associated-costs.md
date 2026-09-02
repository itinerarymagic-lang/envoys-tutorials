# Associated Costs

**Primary field:** Id

Costs not tracked in the HBH itinerary blocks, such as Preparation Days pay, Essentials kit, Staffing overhead, and other pre-ops charges. Each record belongs to one Program Version (Budget, Quote, or Execution), so the same cost category can carry different numbers across the three stages. The Budget field calculates automatically from the inputs; the Quoted Cost USD is the actual confirmed amount.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Mirrors the Name field. Primary display identifier. |
| **Type** | singleSelect | The cost category this record belongs to. Determines which rollup field on Programs it feeds into.<br>Options: Preparation Days · Essentials · Teacher Transportation · Staffing · Teacher Flights · Other AC |
| **Program** | link → Programs | The Program this cost is associated with. |
| **Number of Students \| SOT** | lookup | Student count pulled from the linked Program. Used when Cost Basis = Per Student. |
| **Number of Faculty \| SOT** | lookup | Faculty count pulled from the linked Program. Used when Cost Basis = Per Adult. |
| **Number of Field Staff \| SOT** | lookup | Field staff count pulled from the linked Program. Used when Cost Basis = Per Adult. |
| **Total No. of Participants \| SOT** | lookup | Total participant count pulled from the linked Program. Used when Cost Basis = Per Person. |
| **Name** | singleLineText | Cost line label. |
| **Comments** | multilineText | Notes on assumptions, breakdown, or context for this cost. |
| **Budget** | formula | Calculated cost: Unit Price × the participant count defined by Cost Basis, multiplied by No. Pax and # Days where applicable. Returns 0 if Included? = false. *SEE NOTES |
| **Unit Price** | currency | Cost per unit — per person, per student, per group, etc. depending on Cost Basis. |
| **Cost Basis** | singleSelect | How the unit price is multiplied to reach the total.<br>Options: Per Group · Per Person · Per Student · Per Adult · N/A · Per Staff |
| **Included?** | singleSelect | Whether this cost line is active and included in the Budget calculation. Set to false to exclude without deleting the row. Origin comes from I&B sheet.<br>Options: true · false |
| **No. Pax** | number | Multiplier for certain fields. Determined from I&B sheet. If Cost Basis is blank, then Budget is determined with this field as [{No.Pax}*{No. Days}*{Unit Price}]. |
| **# Days** | number | Number of days this cost applies to. Multiplied into the Budget formula alongside No. Pax when Cost Basis is blank. |
| **Program Versions** | link → Program Versions | The Program Version (Budget, Quote, or Execution) this cost row belongs to. Determines which AC rollup (formulas between tables) on Programs it feeds. |
| **Version (from Program Versions)** | lookup | Version label pulled from the linked Program Version record (Budget / Quote / Execution). |
| **Total No. of Participants (from Program Versions)** | lookup | Total participant count from the linked Program Version. Used in Budget formula when Cost Basis = Per Person. IMPORTANT: Not the same as SOT. |
| **Staff (from Program Versions)** | lookup | Staff count from the linked Program Version. Used in Budget formula when Cost Basis = Per Adult. IMPORTANT: Not the same as SOT. |
| **Faculty (from Program Versions)** | lookup | Faculty count from the linked Program Version. Used in Budget formula when Cost Basis = Per Adult. IMPORTANT: Not the same as SOT. |
| **Students (from Program Versions)** | lookup | Student count from the linked Program Version. Used in Budget formula when Cost Basis = Per Student. IMPORTANT: Not the same as SOT. |
| **Manual sort** | manualSort | Controls display order within a Program Version's cost list. Automatic Field. |
| **Quoted Cost USD** | currency | Actual confirmed cost for this line item, entered manually once a quote or invoice is received. Distinct from the calculated Budget field. |

## Related tables

- **Programs** — the AC rollup fields (`Budget | AC …`, `Forecast | AC …`, `Closing | AC …`) aggregate rows from this table filtered by Type and Version
- **Program Versions** — each row belongs to exactly one version; changing the link changes which rollup it feeds

## Notes

- The **Budget formula** reads participant counts from Program Versions (not directly from the Programs SOT field), so that each version can use its own headcount snapshot. This is necessary for OPS to calculate real budgets based on maximum number of participants to attend accordingly and book reservations accordingly.
- **Cost Basis = Per Adult** multiplies by Staff + Faculty combined.
- **Included? = false** zeroes out the Budget calculation without removing the row — useful for tracking optional items or items that were scoped out. The origin of this is the I&B sheet range D62:82.
- `Program Field Staff Assignments` is a `singleLineText` in the live schema — it is orphaned and not a working link field.
