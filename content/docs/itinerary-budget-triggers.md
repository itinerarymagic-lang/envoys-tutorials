# Itinerary & Budget Triggers

How an Itinerary & Budget request moves through the system, and what each of the three interfaces is for.

---

## What an I&B Trigger is

When a school asks us for a proposal, someone has to build an itinerary and price it. That whole cycle — request comes in, OPS builds it, Finance prices it, it goes back to PT — is what we call an **Itinerary & Budget**, or I&B.

An **I&B Trigger** is the moment that cycle starts. Instead of a request arriving by Slack or email and living in someone's head, it becomes a record in the **I&B Requests** database. From that point on the request has a status, an owner, a due date, and a paper trail.

I&B Requests are deliberately kept **separate from Programs**. A request is a proposal we are working on, not a trip we are running. Only when a proposal is approved does it migrate over and become a Program.

Each request is also tied to its own **Itinerary & Budget Google Sheet**. The Sheet is where the day-by-day building happens; Airtable is where the request is tracked, priced, and handed between teams.

---

## The three interfaces

Three interfaces sit on top of the same data. Which one you open depends on what you are trying to do.

### 1. OPS | I&B DASHBOARD

The dashboard is the **overview and management layer** — the place you go to understand the state of I&B work as a whole rather than to act on any one request. It visualises the statistics that come out of the request database: how many requests are open, where they are sitting in the pipeline, how they are split across OPS leads and builders, how long they are taking to deliver, and which ones are running against their due date. Use it when you need to see the shape of the workload, spot a bottleneck, decide where to put capacity, or report on how OPS is performing. It's for reading and deciding, not for data entry.

### 2. OPS | I&B Request List

This is **OPS's main working interface** and where the day-to-day job actually gets done. Every I&B request lives here, and OPS uses it to track and manage each one from the moment it's received through to delivery: opening a request, assigning the OPS lead and builder, setting the due date, recording the trip parameters, moving the status along as work progresses, uploading the staging files from the Google Sheet, and handing the request over to Finance for pricing. If you work in OPS, this is the screen you keep open.

### 3. FINANCE | I&B Pricing Input

This is **Finance's dedicated entry point into the pricing step**. When OPS has built an itinerary and needs a price, the request appears here with everything Finance needs to make the call — the trip parameters, the participant numbers, PT's target price, the air estimate, and any notes OPS added. Finance then enters the pricing tiers: for each participant range, the land price per student and the margin the business expects to make. It is scoped deliberately — Finance sees the pricing context and edits the pricing fields, without needing to work inside OPS's full request list. Once the tiers are in, the price flows straight back to the request and OPS can deliver the proposal to PT.

---

## The I&B status flow

Status is the single most important field on a request — it tells everyone where the request stands and who is holding it.

| Status | Means |
|---|---|
| **RFP \| Request Received** | The request has arrived and is logged. Nothing has been built yet. |
| **RFP \| Itinerary & Budget Triggered** | The build has officially started. OPS is working on it. |
| **RFP \| Add'l Info Needed from PT** | Blocked. Something is missing or unclear and PT has to answer before OPS can continue. |
| **RFP \| Waiting for Pricing** | OPS has finished building. The request is with Finance for pricing. |
| **RFP \| Delivered to PT** | The priced proposal has been sent back to PT. |
| **RFP \| Minor Adjustments** | PT came back with small changes. The request is being tweaked rather than rebuilt. |
| **Proposal Approved - Migrate to Programs** | The school said yes. The request now becomes a Program. |
| **Proposal Rejected** | The school said no. Record the reason. |
| **Cancelled** | The request is dropped before a decision — the school withdrew, dates fell through, and so on. |
| **Samples** | Not a real request. Example itineraries used for reference or demonstration. |
| **Archived** | Closed out and kept for the record. |

**Keep the status current.** The dashboard, the delivery-time calculations and Finance's queue are all driven from it. A request left on the wrong status is invisible to the people who need to act on it.

---

## The I&B request — field by field

### Identification

| Field | What it means |
|---|---|
| **Itinerary Name** | The **source of truth** for the name. It must match exactly everywhere else the itinerary appears — the Google Sheet, PT's notes, any automation. A mismatch here silently breaks automations. Decide the name once and reuse it verbatim. |
| **Itinerary & Budget Link** | Link to this request's Itinerary & Budget Google Sheet, where the actual building happens. |
| **PT Program Notes** | Link to PT's notes for the request — the brief behind what's being asked for. |
| **Destination** | Pick from the Destination list. If the destination isn't there, add it to the Destination database **first**, then come back and link it. Don't type a new one loose. |
| **School** | The school the request is for. Pulls the school name through automatically. |

### Ownership and build

| Field | What it means |
|---|---|
| **OPS Lead** | The OPS person accountable for this request. |
| **PT Lead** | The PT person who owns the relationship. Their email is pulled in automatically. |
| **I&B Builder** | Whoever is actually building the itinerary. Often the OPS lead, not always. |
| **I&B Build Mode** | How this one is being built. |
| **Program Type** / **Category** | What kind of trip this is. Used for grouping and reporting on the dashboard. |

### Timing

| Field | What it means |
|---|---|
| **OPS Due Date** | When OPS has committed to delivering. This drives what shows as at-risk on the dashboard. |
| **Date Received by Ops** | Filled in automatically when the record is created. You don't touch it. |
| **Date Sent to PT** | Calculated automatically from the status flow. |
| **Delivery Time** | Calculated — how long the request took from received to delivered. This is the number the dashboard uses to measure turnaround. |
| **Status Last Update** | Automatic timestamp of the last status change. |

### The trip itself

| Field | What it means |
|---|---|
| **Start Date** / **End Date** | The proposed travel dates. |
| **Dates Flexibility** | How firm those dates are. Matters a lot for what OPS can source. |
| **Ground Days** | Calculated from the dates — the number of days on the ground. |
| **Themes** | What the trip is meant to be about, in PT's words. |
| **Student Ages** | The age band of the students travelling. |
| **Number of Students** | Head count of students. |
| **Number of Faculty** | Head count of accompanying school faculty. |
| **Number of Field Staff** | Head count of our own field staff. |
| **Number of Participants** | Calculated — students plus faculty plus field staff. |

### Pricing context (what Finance reads)

| Field | What it means |
|---|---|
| **PT Target Price** | The total price per student PT is aiming for. This is the number the pricing has to work against. |
| **Target Flights Include Price?** | Whether that target price already includes flights. Get this right — it changes the whole calculation. |
| **Air Estimate Price** | The estimated cost of flights per student. |
| **Expected Land Price per Student** | Calculated — the target price minus the air estimate. In other words, what's left to spend on the ground. This is the figure Finance is pricing towards. |
| **Ranges for Pricing** | The participant ranges Finance should build tiers for. Enter them with dashes, separated by a comma and a space — for example `10-15, 16-20`. |
| **Status For Pricing** | Whether this is a **New Itinerary** or a **Re-Pricing** of something we've already quoted. |
| **Additional Information For Pricing** | Anything Finance needs to know that doesn't fit another field. |
| **I&B Notes** | General working notes on the request. |

### Handoff files and progress

| Field | What it means |
|---|---|
| **HBH Blocks CSV** | The staging CSV exported from the Staging sheet of the I&B Google Sheet. **Upload one file only** — more than one will break the import. |
| **Essentials CSV** | The second staging export from the same Sheet. |
| **Step 1–4 Complete?** | Checkboxes marking your progress through the build. Tick them as you go; they're how anyone else can see how far along a request is without asking you. |

### After approval

| Field | What it means |
|---|---|
| **Programs** | Once approved, the Program record this request became. This is the link between the proposal and the real trip. |
| **Proposal Decline / Deferral Reason** | Why a proposal was rejected or deferred. Fill this in — it's the only way we learn anything from a lost proposal. |

---

## Pricing tiers — field by field

A request doesn't get one price, it gets a set of **tiers**. Group travel costs change with group size, so we quote a price for each participant range: one price if 10–15 students come, a different one if 16–20 do. Each tier is its own record linked back to the request.

Which ranges to build is set by OPS in **Ranges for Pricing** on the request.

### Defining the tier

| Field | What it means |
|---|---|
| **I&B Tier Min Students** | The smallest student count this tier covers. |
| **I&B Tier Max Students** | The largest student count this tier covers. |
| **I&B Tier Faculty** | Number of faculty assumed in this tier. |
| **I&B Tier Field Staff** | Number of our field staff assumed in this tier. |
| **I&B Pricing Tier** | Calculated — the tier's card name, shown as **S** for students, **F** for faculty, **SF** for field staff. You don't type this. |

### The price and the margin

| Field | What it means |
|---|---|
| **I&B Tier Land Price per Student** | The land-only price per student for this tier. The core number Finance is entering. Compare it against **Expected Land Price per Student** on the request to see whether it lands within PT's target. |
| **I&B Tier Low Margin** | The lower end of the margin percentage on this tier — the conservative case. |
| **I&B Tier Estimated Profit** | The profit that low margin translates to in money. |
| **I&B Tier Top Margin** | The upper end of the margin percentage — the better case. |
| **I&B Tier Top Estimated Profit** | The profit that top margin translates to in money. |
| **Pricing Tier Notes** | Assumptions, caveats, anything that explains why the number is what it is. Worth filling in — this is what makes a price defensible three weeks later when someone questions it. |

### Calculated displays

| Field | What it means |
|---|---|
| **I&B Land Price Tier Range per Student** | Calculated — shows students, faculty, field staff and land price per student as a whole-dollar amount. This is the version OPS and PT read. |
| **I&B Price Tier Finance** | Calculated — the Finance-facing version of the same tier. |
| **Timestamp** | Automatic. When the tier was last changed. |

Both calculated ranges are pulled back onto the I&B request itself, so OPS can see the finished pricing on the request without opening the tier records.

---

## The cycle, end to end

1. **Request arrives.** A record is created in I&B Requests. Status: *Request Received*.
2. **OPS triggers the build.** OPS lead, builder, destination and due date are set. Status: *Itinerary & Budget Triggered*.
3. **OPS builds** in the Itinerary & Budget Google Sheet, working through Steps 1 to 4 and ticking them off.
4. **Staging files come back to Airtable.** The HBH Blocks and Essentials CSVs are uploaded to the request.
5. **Hand to Finance.** Ranges for Pricing and the target figures are filled in. Status: *Waiting for Pricing*.
6. **Finance prices it** in the I&B Pricing Input interface, creating a tier for each range.
7. **OPS delivers to PT.** Status: *Delivered to PT*. Delivery Time is calculated automatically.
8. **PT and the school decide.** Either minor adjustments, approval and migration to Programs, or rejection with a reason recorded.

If anything blocks you at any point, set the status to *Add'l Info Needed from PT* rather than letting the request sit quietly. A blocked request that's marked as blocked gets unblocked. A blocked request that still looks active doesn't.
