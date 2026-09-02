# I&B Requests

**Primary field:** Itinerary Name

Itinerary & Budgets Request Database.

Separate from Programs and depends on a linked I&B Google Sheet. This is where a request lives *before* it becomes a confirmed Program — once the proposal is approved, the record migrates to the Programs table and the two stay linked.

## Fields

| Field | Type | Description |
|---|---|---|
| **Itinerary Name** | multilineText | Itinerary Name Source of Truth. The name here has to match all other outside sources so automations work properly. Make sure this is the name exactly you are using throughout any process. |
| **I&B Status** | singleSelect | Current stage of the request through the RFP pipeline. Drives the Date Sent to PT and Delivery Time calculations.<br>Options: RFP \| Request Received · RFP \| Itinerary & Budget Triggered · RFP \| Add'l Info Needed from PT · RFP \| Waiting for Pricing · RFP \| Delivered to PT · RFP \| Minor Adjustments · Proposal Approved - Migrate to Programs · Proposal Rejected · Cancelled · Samples · Archived |
| **Itinerary & Budget Link** | url | Link to Itinerary & Budget Google Sheet. |
| **PT Program Notes** | url | PT Program Notes Link from Hubspot |
| **Destination** | link → Destinations | Select a Destination from the list. If unavailable, add the Destination in the Destination Database first. |
| **OPS Lead** | link → ENVOYS HQ | I&B OPS lead assigned. Required for automatic notifications. |
| **PT Lead** | link → ENVOYS HQ | I&B PT lead assigned. Required for automatic notifications. |
| **PT Lead Email** | lookup | Looks for the email of the linked PT Lead from the HQ database. |
| **Program Type** | singleSelect | Classifies the request by the school's geography and whether the program is mandatory or optional.<br>Options: US/CA School - Mandatory Program · International School - Mandatory Program · US/CA School - Optional Program · International School - Optional Program · Other · hubspot |
| **Category** | singleSelect | Internal effort/complexity/turnover classification for the request.<br>Options: Core · Specialized · Explore · Gamble · Other |
| **I&B Builder** | link → Field Staff Profiles | The individual (HQ/CC/FS) building the itinerary and budget for this request. |
| **I&B Build Mode** | singleSelect | Building involvement from different parties. Outsourced dependencies result in longer turnovers.<br>Options: Internally - Full · Internally - Country Coordinator Support · Internally - DMC Support · Country Coordinator - Full · DMC - Full · Other |
| **OPS Due Date** | date | Ops due date to deliver the completed I&B back to PT. |
| **Date Received by Ops** | createdTime | Timestamp the request record was created. |
| **Date Sent to PT** | formula | Stamps the moment I&B Status updated to "RFP \| Delivered to PT". Blank until delivered. |
| **Status Last Update** | lastModifiedTime | Last time the I&B Status field was modified. |
| **Delivery Time** | formula | Turnaround in days: Date Sent to PT minus Date Received by Ops. Blank until the request is delivered. |
| **Themes** | richText | Educational themes the school has requested for this itinerary. |
| **School** | link → Schools | The school making the I&B request. |
| **School Name** | lookup | School Name pulled from the linked School record. If name is wrong, or selected a wrong record, update School link or School Name directly in the record details. |
| **Student Ages** | singleSelect | Grade band of the participating students, US standards.<br>Options: Middle School · Upper School · Faculty · Other |
| **Dates Flexibility** | singleSelect | Whether the school can move the proposed travel dates.<br>Options: Yes · No |
| **Start Date** | date | Proposed arrival date at the destination. Should match the I&B. |
| **End Date** | date | Proposed departure date from the destination. Should match the I&B. |
| **Ground Days** | formula | Days on the ground: End Date minus Start Date, plus one. |
| **Number of Students** | number | Estimated student count for pricing this request. |
| **Number of Faculty** | number | Estimated faculty count for pricing this request. |
| **Number of Field Staff** | number | Estimated Envoys field staff count for pricing this request. |
| **Number of Participants** | formula | Calculates the total number of participants by adding students, faculty, and field staff. |
| **PT Target Price** | currency | Per-student price the school is targeting, as given to PT. |
| **Target Flights Include Price?** | singleSelect | Whether the PT Target Price already includes airfare.<br>Options: Yes · No |
| **Air Estimate Price** | currency | Estimated airfare per student. |
| **Expected Land Price per Student** | formula | Calculates the PT Target Price minus the Air estimate per student. |
| **Ranges for Pricing** | multilineText | Include ranges using dashes and separated by space & comma. (Ex. 10-15, 16-20) |
| **I&B Notes** | richText | Working notes on the itinerary and budget build. |
| **I&B Pricing Tier** | link → I&B Pricing Tier | The pricing tier records built for this request, one per student-count range. |
| **I&B Land Price Tier Range per Student** | lookup | Land price per student for each linked tier, pulled from I&B Pricing Tier. |
| **I&B Price Tier Range Finance** | lookup | Finance-facing tier summary pulled from I&B Pricing Tier. |
| **HBH Blocks CSV** | multipleAttachments | Upload Staging CSV from the I&B Google Sheets Staging Sheet. Only upload 1 file. Make sure it is the correct file for each. Download from I&B linked Sheet in CSV form from "staging_hbh" tab. |
| **Associated Costs CSV** | multipleAttachments | Upload Staging CSV from the I&B Google Sheets Staging Sheet. Only upload 1 file. Make sure it is the correct file for each. Download from I&B linked Sheet in CSV form from "staging_associated_costs" tab. |
| **Step 1 Complete?** | checkbox | Build checklist marker — step 1 done. |
| **Step 2 Complete?** | checkbox | Build checklist marker — step 2 done. |
| **Step 3 Complete?** | checkbox | Build checklist marker — step 3 done. |
| **Step 4 Complete?** | checkbox | Build checklist marker — step 4 done. |
| **Programs** | link → Programs | Link between I&B predecessor to Program. |
| **Program Versions (from Programs)** | lookup | Budget / Operational / Executed version records of the linked Program. Reference only. |
| **Proposal Decline / Deferral Reason** | multipleSelects | Why the school declined or postponed. Select all that apply.<br>Options: Pricing exceeded budget · Chose a different vendor · Did not align with academic goals · Destination no longer a priority · Theme no longer a priority · Response time (ENVOYS) was too long · Travel logistics too complex · Safety or risk concerns · Program postponed to a future year · Trip cancelled internally by the school · Change in school leadership · Enrollment numbers too low · Other |
| **Status For Pricing** | singleSelect | Pipeline category whether Finance is pricing a brand-new itinerary or re-pricing an existing one.<br>Options: Re-Pricing · New Itinerary |
| **Additional Information For Pricing** | richText | Context required for pricing the request that isn't captured in the structured fields. |
| **Last Modified Time** | lastModifiedTime | Last time any field on this record changed. |

## Related tables

- **Destinations** — where the program would travel
- **Schools** — the requesting partner school
- **ENVOYS HQ** — OPS Lead, PT Lead
- **Field Staff Profiles** — I&B Builder
- **I&B Pricing Tier** — student-count price ranges for this request
- **Programs** — the confirmed program this request becomes after approval
