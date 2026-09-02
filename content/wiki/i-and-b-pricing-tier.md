# I&B Pricing Tier

**Primary field:** I&B Pricing Tier

Associated pricing tiers for each Itinerary & Budget Request.

Each record is one price bracket for a given student-count range. A single I&B Request usually has several tiers — the price per student changes depending on how many students end up registering. These tiers are pre-LOI and are for the proposal stage only; once a request becomes a Program, the equivalent post-LOI table is **Program Pricing Tiers**.

## Fields

| Field | Type | Description |
|---|---|---|
| **I&B Pricing Tier** | formula | Displays the Price Tier Card Name<br>S: Students<br>F: Faculty<br>SF: Field Staff |
| **I&B Requests** | link → I&B Requests | The Itinerary & Budget Request this tier belongs to. |
| **I&B Land Price Tier Range per Student** | formula | Displays students, faculty, field staff, and land price per student as a dollar amount with no decimals. |
| **I&B Price Tier Finance** | formula | Finance-facing version of the tier card. Same student/faculty/field-staff breakdown and land price, plus the low margin percentage and estimated profit. |
| **I&B Tier Min Students** | number | Lowest student count this tier's price applies to. Available in Pricing tab of I&B sheet. |
| **I&B Tier Max Students** | number | Highest student count this tier's price applies to. Available in Pricing tab of I&B sheet. |
| **I&B Tier Faculty** | number | Number of faculty assumed in this tier's price point. Available in Pricing tab of I&B sheet. |
| **I&B Tier Field Staff** | number | Number of Envoys field staff assumed in this tier's price point. Available in Pricing tab of I&B sheet. |
| **I&B Tier Land Price per Student** | currency | Price charged per student for this tier, land only — excludes airfare. |
| **I&B Tier Low Margin** | percent | Margin percentage for this tier, using Tier Min Students. |
| **I&B Tier Estimated Profit** | currency | Expected profit for this tier using Tier Min Students. |
| **I&B Tier Top Margin** | percent | Expected margin percentage for this tier, using Tier Max Students. |
| **I&B Tier Top Estimated Profit** | currency | Expected profit for this tier, using Tier Max Students. |
| **Pricing Tier Notes** | richText | Notes on assumptions or caveats behind this tier's pricing. |
| **Timestamp** | lastModifiedTime | Last time any field on this tier was changed. |

## Related tables

- **I&B Requests** — the request these tiers price
- **Program Pricing Tiers** — the post-LOI equivalent, once the request becomes a Program

## Notes

- The tier card formulas (`I&B Pricing Tier`, `I&B Land Price Tier Range per Student`, `I&B Price Tier Finance`) all read from the same four count fields plus the land price. If a count changes, all three displays update together.
- Margin and profit are entered manually — they are not calculated from cost data in the base.
