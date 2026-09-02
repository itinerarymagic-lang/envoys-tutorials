# HBH Blocks

**Primary field:** Id

Individual line items of the Hour-by-Hour itinerary — activities, meals, accommodation, transport, flights, and anything else scheduled on a program day. The largest operational table in the base. Each block belongs to one HBH Day and one Program Version (Budget, Quote, or Execution), so costs are always tied to the right stage.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Auto-generated identifier: Day + Name + Autonumber. |
| **Programs** | link → Programs | The Program this block belongs to. System link — do not edit directly. |
| **Program Status** | lookup | Program Status pulled from the linked Program. |
| **Program** | lookup | Program Name pulled from the linked HBH Day. |
| **Itinerary Day** | link → HBH Days | The day this block is scheduled on. Determines the calendar date. |
| **Day #** | lookup | Day number pulled from the linked HBH Day. |
| **Name** | singleLineText | Short label for this itinerary block. |
| **Categories** | link → HBH Categories | Category tag (Accommodations, Meals, Transportation, Activities, Internal Flights, etc.). Determines which cost rollup on Programs this block feeds. |
| **Start Time** | singleLineText | Scheduled start time (specify as — e.g. "9:00 AM"). |
| **End Time** | singleLineText | Scheduled end time (specify as — e.g. "9:30 AM"). |
| **Location** | link → Locations | The specific location for this block. Will create a record for Location linked to the Destination. During I&B creation, try to use same labels for existing Locations to avoid duplicates. |
| **Destination** | lookup | Destination pulled from the linked Program. Reference only. |
| **Vendor** | link → Vendors | The vendor providing this service. |
| **Booking Status** | singleSelect | Where the booking stands for this block.<br>Options: Booking Needed · Dates Blocked · Reach Out Made · Field Booking Needed · Booking Made · No Booking Needed |
| **Payment Status** | singleSelect | Payment state for this block.<br>Options: N/A · Payment Needed · Deposit Made · Full Payment Made · Field-CC · Field-Cash |
| **Visible To School** | checkbox | When checked, this block appears on the school-facing HBH. |
| **Program Debrief Required** | checkbox | When checked, this block becomes available to be evaluated in the program debrief. |
| **Debrief Rating** | singleSelect | Program quality rating for this block, set during debrief.<br>Options: Highlight · Recommended · Acceptable · Caution · Avoid |
| **Program Debrief \| Notes** | multilineText | Debrief notes for this specific block. |
| **Notes** | multilineText | Working notes on this block (logistics, special instructions, context). |
| **autonumber** | autoNumber | System auto-increment. Used in the Id formula. DO NOT DELETE. |
| **Booking Name** | formula | Display label combining Day #, Name, and autonumber. Used in booking communications and unique, quick identification. |
| **Booking Priority** | singleSelect | How urgently this booking needs to be resolved.<br>Options: Low · Normal · High · NA |
| **Date** | lookup | Calendar date pulled from the linked HBH Day from Formula Date. |
| **manual_sorting** | number | Numeric sort key for ordering blocks upon import. Once imported, it becomes irrelevant. |
| **Manual sort (Quote)** | manualSort | Automatic sort order that dictates sorting in the interfaces. DO NOT DELETE. MODIFY BY DRAG AND DROP INTO POSITION. |
| **Version (Link)** | link → Program Versions | The Program Version (Budget, Quote, or Execution) this block belongs to. Determines which cost rollup it feeds on Programs. Do not touch — changing this moves the block's costs to a different stage. |
| **Version** | lookup | Version label (Budget / Quote / Execution) pulled from the linked Program Version. |
| **Cost Basis** | singleSelect | How the Unit Cost is multiplied to reach the total forecast cost.<br>Options: Per Group · Per Person · Per Student · Per Adult |
| **Unit Cost USD** | currency | Cost per unit in USD (per person, per group, etc. depending on Cost Basis). |
| **Total Forecast Cost USD** | formula | Calculated total: Unit Cost × participant count (from Version), based on Cost Basis. |
| **Quoted Total Cost** | currency | Actual quoted or invoiced cost IN USD, entered manually once a vendor confirms pricing. Distinct from the forecast Total Forecast Cost. |
| **Total No. of Participants (Versions)** | lookup | Total participants from the linked Program Version. Used when Cost Basis = Per Person. Do not touch. |
| **Staff (Versions)** | lookup | Staff count from the linked Program Version. Do not touch. |
| **Faculty (Versions)** | lookup | Faculty count from the linked Program Version. Do not touch. |
| **Students (Versions)** | lookup | Student count from the linked Program Version. Do not touch. |
| **Local Amount** | currency | Cost in the destination's local currency, entered manually. Used to calculate Local Amount USD via the exchange rate. |
| **Local Currency** | lookup | Destination currency pulled from the linked Program. |
| **Fx Rate Used** | lookup | Exchange rate pulled from the linked Program. Used to convert Local Amount to USD. |
| **Local Amount USD** | formula | If Local Amount is blank, returns Quoted Total Cost; otherwise converts Local Amount ÷ Fx Rate. Used to figure out Quoted Total Cost in USD. |
| **Confirmed Payment Date** | date | Date the payment for this block was confirmed as received by the vendor. |
| **AdvancePaidFlag** | formula | Returns "Completed" if Payment Status is not "Payment Needed" or "Deposit Made". Used in booking dashboards. |
| **BookingFlag** | formula | Returns "Completed" if Booking Status is "Booking Made", "No Booking Needed", or "Field Booking Needed". |
| **Estimate / Quote Difference** | formula | Difference between Total Forecast Cost and Quoted Total Cost. Positive = over budget. |
| **sequence_order** | number | Internal sequence number for ordering blocks in automations and exports. |
| **Visible For Staff** | checkbox | When checked, this block is visible in the field staff view of the itinerary. |
| **Notes for School** | richText | External notes for school visible in school-facing HBH. |
| **School Comments on Itinerary** | richText | School feedback notes on specific HBH Blocks on School HBH. |

## Related tables

- **Programs** — blocks roll up into the cost sections (Budget, Operations Budget, Closing, Quoted Total)
- **HBH Days** — one Day per calendar day, blocks attach to Days
- **Program Versions** — Version link determines which stage cost rollup this block feeds
- **HBH Categories** — classifies the block for cost rollup routing
- **Locations**, **Vendors** — venue and supplier for this block

## Notes

- **The Version (Link) field is the most critical field in this table.** It determines whether a block's cost feeds the Budget, Operations Budget, or Closing totals on Programs. Never change it without understanding the downstream effect.
- **Cost Basis = Per Adult** multiplies by Faculty + Staff combined.
- **Quoted Total Cost** is what was actually paid. **Total Forecast Cost** is the estimate. The Estimate / Quote Difference shows variance.
- Booking Status and Payment Status drive the completion percentage fields on Programs (% Bookings Completed, Transportation Completion Status, etc.).
