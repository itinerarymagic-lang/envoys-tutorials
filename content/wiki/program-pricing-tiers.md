# Program Pricing Tiers

**Primary field:** Program Pricing Tier

Dynamic Associated Price Ranges linked to Programs after LOI Stage.

Each record is one price bracket for a confirmed Program. Because the final price per student depends on how many students actually register, a Program carries several tiers and the system picks whichever one contains the current **Number of Students | SOT** — that tier's price flows back to the Program as the Final Land Price. This is the authoritative post-LOI pricing table; the pre-LOI equivalent is **I&B Pricing Tier**, which differs as there are price negotiations between I&B and LOI. Double check that the prices here match the school's proposal.

## Fields

| Field | Type | Description |
|---|---|---|
| **Program Pricing Tier** | formula | Cleans up the Program name and summarizes the tier's student, faculty, and field staff numbers. |
| **Program** | link → Programs | Linked Program record. |
| **Program Name** | lookup | Linked Program Name from linked Program. |
| **I&B Price Tier Finance Linked to Program** | lookup | Display of I&B Pricing Tiers linked to Program. They are a reference for input the Program Pricing Tiers but confirm no changes were enabled by the PT / EL Lead. |
| **Tier Min Number Students** | number | Lowest student count this tier's price applies to. |
| **Tier Max Number Students** | number | Highest student count this tier's price applies to. |
| **Tier Number of Faculty** | number | Number of faculty assumed in this tier's cost model. |
| **Tier Number of Field Staff** | number | Number of Envoys field staff assumed in this tier's cost model. |
| **Tier Land Price USD** | currency | Price charged per student for this tier, land only — excludes airfare. Feeds the Program's Final Land Price Student in USD when this tier is the active range. |
| **Tier Flight Price USD** | currency | Price charged per student for airfare in this tier. |
| **Tier Total Price** | formula | Calculates the total price by adding land and flight prices for the tier. |
| **Price Tier Notes** | richText | Notes on assumptions or caveats behind this tier's pricing. |
| **Number of Students \| SOT** | lookup | Current source-of-truth student count from the linked Program. Determines which tier is active. |
| **Active Price Range** | formula | Indicates if the number of students is within the tier's active range.<br>Returns: Active Range · Inactive Range |
| **School's Local Currency** | lookup | The school's billing currency, pulled through the linked Program. Used to display prices in local currency. |

## Related tables

- **Programs** — the confirmed program these tiers price
- **I&B Pricing Tier** — the pre-LOI tiers, carried over for reference

## Notes

- Exactly one tier per Program should read **Active Range** at a time. If two do, the min/max ranges overlap and need correcting.
- `I&B Price Tier Finance Linked to Program` is reference only — it shows what was quoted at proposal stage. Always confirm against what the PT / EL Lead actually agreed before entering the tier values here.
