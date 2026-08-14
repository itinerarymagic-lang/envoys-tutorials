content/docs/data-vs-interfaces.md# ENVOYS | V.0 — Field Dictionary

**Base:** ENVOYS | V.0
**Last refreshed from the live base:** 13 August 2026
**Coverage:** 34 tables · 1,093 fields

## How to read this document

- **Field** — the name exactly as it appears in Airtable. Where a name is misspelled in the base, it is reproduced as-is and flagged, because changing it would break automations.
- **Type** — the Airtable field type in plain English. `Link → X` means the field connects records to the X table.

## Reading the type column

| Shown as | Meaning |
|---|---|
| Formula | Calculated automatically. Not editable. |
| Rollup | Adds up or summarises values from linked records. Not editable. |
| Lookup | Displays a value that lives on a linked record. Not editable. |
| Count | Counts linked records. Not editable. |
| Link → X | Connects this record to records in table X. |
| Autonumber / Created time / Last modified / Created by | Set by Airtable automatically. |

## Contents

| # | Table | Fields |
|---|---|---|
| 1 | I&B Requests | 50 |
| 2 | I&B Pricing Tier | 15 |
| 3 | Programs | 213 |
| 4 | Program Pricing Tiers | 15 |
| 5 | Reconciliation Accounts | 12 |
| 6 | Invoices | 14 |
| 7 | Statements | 18 |
| 8 | Expenses | 34 |
| 9 | Allocations | 18 |
| 10 | Associated Costs | 24 |
| 11 | Vendor Payments | 36 |
| 12 | Currencies | 10 |
| 13 | Program Versions | 10 |
| 14 | HBH Days | 10 |
| 15 | HBH Blocks | 46 |
| 16 | HBH Categories | 5 |
| 17 | Destinations | 18 |
| 18 | Countries | 17 |
| 19 | Locations | 12 |
| 20 | Vendors | 40 |
| 21 | Vendor Listings | 13 |
| 22 | Schools | 17 |
| 23 | School Faculty & Staff Directory | 15 |
| 24 | School Participant Profiles | 84 |
| 25 | ENVOYS HQ | 20 |
| 26 | Field Staff Profiles | 78 |
| 27 | Program Field Staff Assignments | 53 |
| 28 | EM QC Checks | 86 |
| 29 | OPS QC Checks | 75 |
| 30 | Program Meetings | 12 |
| 31 | Program Dashboard | 8 |
| 32 | Envoys External Toolkit Base | 6 |
| 33 | Program Documents | 6 |
| 34 | Utilities | 3 |

---

# 1. I&B Requests

Itinerary & Budget requests — the stage before a program is confirmed. Each record tracks one request from intake through pricing to migration into a Program.

| Field | Type | What it's for |
|---|---|---|
| Itinerary Name | Long text | **Source of truth.** The name must match every outside source exactly or automations break. Use this exact spelling everywhere. |
| I&B Status | Single select | Where the request sits in the workflow. |
| Itinerary & Budget Link | URL | Link to the Itinerary & Budget Google Sheet for this request. |
| PT Program Notes | URL | Link to the Partnerships team's program notes document. |
| Destination | Link → Destinations | Where the program is going. If the destination isn't listed, create it in Destinations first. |
| OPS Lead | Link → ENVOYS HQ | The Operations person assigned to this request. |
| PT Lead | Link → ENVOYS HQ | The Partnerships person assigned to this request. |
| PT Lead Email | Lookup | Email of the assigned PT Lead, pulled from the HQ directory. |
| Program Type | Single select | Program type based on the school's location and the kind of program. |
| Category | Single select | Program category for this request. |
| I&B Builder | Link → Field Staff Profiles | The field staff member building the itinerary and budget. |
| I&B Build Mode | Single select | How the itinerary is being built (e.g. from scratch vs. adapted). |
| OPS Due Date | Date | Date Operations must deliver the itinerary and budget by. |
| Date Received by Ops | Created time | When the request record was created. Set automatically. |
| Date Sent to PT | Formula | Date the completed I&B was handed back to Partnerships. |
| Status Last Update | Last modified | When anything on this record last changed. |
| Delivery Time | Formula | How long the request took from intake to delivery. |
| Themes | Long text (rich) | Themes the school wants the program to explore. |
| School | Link → Schools | The school requesting the program. |
| School Name | Lookup | School name pulled from the linked school record. |
| Student Ages | Single select | Age band of the students (Upper School 9–12, Lower School 6–8, Faculty, or Mixed). |
| Dates Flexibility | Single select | How much the requested dates can move. |
| Start Date | Date | Requested arrival date at the destination. |
| End Date | Date | Requested departure date from the destination. |
| Ground Days | Formula | Number of days on the ground, calculated from the start and end dates. |
| Number of Students | Number | Students expected on the program. |
| Number of Faculty | Number | School faculty expected on the program. |
| Number of Field Staff | Number | Envoys field staff expected on the program. |
| Number of Participants | Formula | Total headcount — students plus faculty plus field staff. |
| PT Target Price | Currency | Price per student Partnerships is aiming to sell at. |
| Target Flights Include Price? | Single select | Whether the target price includes flights. |
| Air Estimate Price | Currency | Estimated airfare per student. |
| Expected Land Price per Student | Formula | Target price minus the air estimate — the land budget per student. |
| Ranges for Pricing | Long text | Student-count ranges to price against. Use dashes, separated by commas (e.g. 10-15, 16-20). |
| I&B Notes | Long text (rich) | Free notes on the request. |
| I&B Pricing Tier | Link → I&B Pricing Tier | The pricing tiers built for this request. |
| I&B Land Price Tier Range per Student | Lookup | Land price per student for each tier, shown for reference. |
| I&B Price Tier Range Finance | Lookup | Finance's view of the tier pricing, shown for reference. |
| HBH Blocks CSV | Attachment | Staging CSV exported from the I&B Google Sheet. **Upload one file only.** |
| Essentials CSV | Attachment | Essentials/associated-costs CSV exported from the I&B Google Sheet. |
| Step 1 Complete? | Checkbox | Migration step 1 done. Set by the migration process. |
| Step 2 Complete? | Checkbox | Migration step 2 done. Set by the migration process. |
| Step 3 Complete? | Checkbox | Migration step 3 done. Set by the migration process. |
| Step 4 Complete? | Checkbox | Migration step 4 done. Set by the migration process. |
| Programs | Link → Programs | The confirmed Program this request became, once migrated. |
| Program Versions (from Programs) | Lookup | Budget/Operational/Executed versions on the resulting program. |
| Proposal Decline / Deferral Reason | Multiple select | Why the school declined or deferred, if they did. |
| Status For Pricing | Single select | Where the request sits in Finance's pricing queue. |
| Additional Information For Pricing | Long text (rich) | Anything Finance needs to know to price this request. |
| Last Modified Time | Last modified | When the record last changed. |

---

# 2. I&B Pricing Tier

Price tiers attached to an I&B Request. One record per student-count band, each with its own land price and margin.

| Field | Type | What it's for |
|---|---|---|
| I&B Pricing Tier | Formula | Tier card name showing S (students) / F (faculty) / SF (field staff). |
| I&B Requests | Link → I&B Requests | The request this tier belongs to. |
| I&B Land Price Tier Range per Student | Formula | Students, faculty, field staff and land price per student as a whole-dollar amount. |
| I&B Price Tier Finance | Formula | Finance-facing summary of the tier. |
| I&B Tier Min Students | Number | Lowest student count this tier applies to. |
| I&B Tier Max Students | Number | Highest student count this tier applies to. |
| I&B Tier Faculty | Number | Faculty assumed in this tier. |
| I&B Tier Field Staff | Number | Field staff assumed in this tier. |
| I&B Tier Land Price per Student | Currency | Land price charged per student at this tier. |
| I&B Tier Low Margin | Percent | Margin at the low end of the tier. |
| I&B Tier Estimated Profit | Currency | Estimated profit at the low margin. |
| I&B Tier Top Margin | Percent | Margin at the top end of the tier. |
| I&B Tier Top Estimated Profit | Currency | Estimated profit at the top margin. |
| Pricing Tier Notes | Long text (rich) | Notes on how this tier was built or what it assumes. |
| Timestamp | Last modified | When the tier last changed. |

---

# 3. Programs

The centre of the base. Every confirmed program lives here, and almost every other table connects back to it. 213 fields, grouped below by what they do.

> ⚠️ **Two link fields are named the wrong way round.** "Program Documents" actually links to the **Program Dashboard** table, and "Program Dashboard" links to the **Program Documents** table. This is a leftover from a table rename. Check the table ID, not the field name.

## Identity and basics

| Field | Type | What it's for |
|---|---|---|
| Program ID | Formula | Unique ID combining start date (MM/DD/YY) and program name. |
| autonumber | Autonumber | Internal sequential number used by automations. **Do not delete.** |
| Program Name | Single line text | **Source of truth.** Usually School (or abbreviation) + Destination + Year, e.g. "LREI Martinique 2026". Use this exact name anywhere outside Airtable. |
| School | Link → Schools | The client school. Uses a unique school identifier so similarly-named schools don't get confused. |
| Destination | Link → Destinations | Where the program goes — a country, city or region. Create it in Destinations first if missing. |
| Program Status | Single select | Where the program sits on the timeline (LOI, Confirmed, Operated). |
| Program Category | Single select | Category assigned using the Program Categorization Tool. |
| Program Type | Single select | Type based on the school's geography and program style. |
| Period | Single select | American school year the program falls in (2026-2027 = Summer/Fall 2026 through Winter/Spring 2027). |
| Student Ages | Single select | Upper School (9–12), Lower School (6–8), Faculty only, or Mixed. |
| Country | Lookup | Country of the selected destination. Used to connect people and records across tables. |
| Jotform Registration Link | URL | Participant registration form for this program. |

## Headcount

| Field | Type | What it's for |
|---|---|---|
| Number of Students \| SOT | Number | **Source of truth.** Students expected, and the number the active HBH is built on. Should match Students Registered by the start date. |
| Number of Faculty \| SOT | Number | **Source of truth.** Faculty expected, reflected in the active HBH. Should match Faculty Registered by the start date. |
| Number of Field Staff \| SOT | Number | **Source of truth.** Field staff expected, reflected in the active HBH. Should match Staff Assignments by the start date. |
| Number of Participants | Formula | Total headcount — students plus faculty plus staff. |
| Min Number Students | Rollup | Lowest student count needed for the program to run, from the negotiated pricing ranges. Fixed unless a new agreement is reached. |
| Max Number of Students | Rollup | Highest student count expected, from the negotiated pricing ranges. Used by OPS to size bookings. |
| Students Registered | Count | How many student registrations are linked to this program. |
| Faculty Registered | Count | How many faculty registrations are linked. *(Description in the base is a Spanish to-do note — needs review.)* |
| Staff Assigned | Count | How many staff assignments are linked. *(Description in the base is a Spanish to-do note — needs review.)* |
| Additional Participants Notes | Long text | Details of anyone travelling who isn't a student, faculty member or field staff. |
| Registration Probability | Percent | Estimated likelihood the program hits minimum numbers and runs. |

## Dates and duration

| Field | Type | What it's for |
|---|---|---|
| Program Start Date \| SOT | Date | **Source of truth.** Day the group arrives at the destination. Sets day 1 of the HBH. |
| Program End Date \| SOT | Date | **Source of truth.** Day the group departs the destination. Sets the last day of the HBH. |
| Number of Ground Days \| SOT | Formula | Days in the field — the days covered by the HBH. |
| Number of Nights | Formula | Nights of accommodation OPS needs to book. |
| School Flight Departure | Date & time | When the group leaves the point of origin. Differs from the start date because of flight time and layovers. |
| School Flight Return | Date & time | When the group lands back at the point of origin. Differs from the end date for the same reason. |
| Days until program start date | Formula | Countdown to the start date. |
| Preparation Days | Number | **Source of truth**, set by S&R. Paid prep days allocated to field staff. |

## POD assignments — who owns this program

| Field | Type | What it's for |
|---|---|---|
| POD \| PT Lead | Link → ENVOYS HQ | Partnerships lead. |
| POD \| OPS Lead | Link → ENVOYS HQ | Operations lead. |
| POD \| EM Lead | Link → ENVOYS HQ | Experience Management lead. |
| POD \| S&R Lead | Link → ENVOYS HQ | Staffing & Risk lead. |
| POD \| HQ Lead | Link → ENVOYS HQ | HQ emergency contact for the program. |
| POD \| HQ Blackouts Lead | Link → ENVOYS HQ | HQ contact covering blackout periods. |
| EM Lead Assigned Status | Lookup | Whether an EM lead has been assigned, from the EM QC record. |

## Documents and links

| Field | Type | What it's for |
|---|---|---|
| Itineraries & Budgets Document Link | URL | The program's I&B Google Sheet. |
| Program Notes Link | URL | The program notes document. |
| Whatsapp HQ Field Link | URL | WhatsApp group connecting HQ and the field team. |
| Field Program Folder Link | URL | The Field Program Folder (FPF) for this program. |

## Connections to other tables

| Field | Type | What it's for |
|---|---|---|
| Staff Assignments | Link → Program Field Staff Assignments | Field staff assigned to this program. |
| Staff Assignment Status | Lookup | Assignment status pulled from those records. |
| Program Pricing Tiers | Link → Program Pricing Tiers | Confirmed price tiers for this program. |
| Itinerary Days | Link → HBH Days | The day-by-day skeleton of the itinerary. |
| Program Versions | Link → Program Versions | Budget / Operational / Executed snapshots and their headcounts. |
| HBH Blocks | Link → HBH Blocks | Every itinerary line item. **Don't touch** — managed by automation. |
| School Participant Profiles | Link → School Participant Profiles | Registrations coming in from Jotform. **Don't touch.** |
| Associated Costs | Link → Associated Costs | Non-itinerary costs (prep days, essentials, staffing). |
| I&B Requests | Link → I&B Requests | The original request this program came from. |
| EM QC Checks Link | Link → EM QC Checks | The EM quality-control checklist record. |
| OPS QC Checks | Link → OPS QC Checks | The OPS quality-control checklist record. |
| OPS QC Checks Status | Lookup | Overall OPS QC status. |
| Program Meetings | Link → Program Meetings | Meetings scheduled for this program. |
| Program Documents | Link → **Program Dashboard** | ⚠️ Despite the name, links to the Program Dashboard table (school-facing resources). |
| Program Dashboard | Link → **Program Documents** | ⚠️ Despite the name, links to the Program Documents table (internal documents). |
| School's Directory Contacts | Link → School Faculty & Staff Directory | School-side contacts for this program. |
| Vendor Payments | Link → Vendor Payments | Payment requests raised against this program. |
| School Invoices | Link → Invoices | Invoices issued to the school. |
| Allocations | Link → Allocations | Expense allocations charged to this program. |
| Expenses | Link → Expenses | Expenses linked directly to this program. |
| Income | Single line text | Leftover from the deleted Income table. No longer connected to anything — safe to ignore. |
| Staff Salaries | Single line text | Leftover stub, no longer connected to anything. |

## Pricing and revenue

| Field | Type | What it's for |
|---|---|---|
| Final Land Price Student in USD | Lookup | Price per student from the pricing tier, set by Finance and agreed with the school. Changes with the SOT student count. |
| Final Land Price Student in Local Currency | Formula | The same price converted into the school's local currency. |
| School's Local Currency | Lookup | Currency to quote the school in. Reference only. |
| School's Currency Exchange Rate to USD | Lookup | Exchange rate used for that conversion. |
| Estimaded Total Revenue | Formula | Land price per student × SOT student count. *(Field name is misspelled in the base.)* |
| I&B Price Tier Range Finance | Lookup | Pricing tiers from the original I&B request, for reference only — not binding. |
| Flight Estimate Per Person | Lookup | Manually entered estimate of the flight price charged per student, in USD. |

## Cost rollups — Budget version

Everything below sums HBH Blocks or Associated Costs filtered to the **Budget** Program Version. All are read-only.

| Field | Type | What it's for |
|---|---|---|
| Budget \| USD Total | Rollup | Total budgeted cost across all categories. |
| Budget \| Accommodations | Rollup | Budgeted accommodation costs. |
| Budget \| Meals | Rollup | Budgeted meal costs. |
| Budget \| Transportation | Rollup | Budgeted ground transport costs. |
| Budget \| Activities | Rollup | Budgeted activity costs. |
| Budget \| Internal Flights | Rollup | Budgeted in-country flight costs. |
| Budget \| Other | Rollup | Budgeted costs not in another category. |
| Budget \| Flights | Rollup | Budgeted flight costs; should match the I&B Sheet. |
| Budget \| AC Preparation Days | Rollup | Budgeted preparation-day costs from Associated Costs. |
| Budget \| AC Essentials | Rollup | Budgeted essentials costs from Associated Costs. |
| Budget \| AC Staffing | Rollup | Budgeted staffing costs from Associated Costs. |
| Budget \| AC Other | Rollup | Budgeted other Associated Costs. *(Base description mistakenly says Preparation Days.)* |
| Budget \| AC Total USD | Rollup | Total budgeted Associated Costs. |

## Cost rollups — Operational version

Same categories, filtered to the **Operational** Program Version. Read-only.

| Field | Type | What it's for |
|---|---|---|
| Operations Budget \| USD Total | Rollup | Total operational cost across all categories. |
| Operations Budget \| Accommodations | Rollup | Operational accommodation costs. |
| Operations Budget \| Meals | Rollup | Operational meal costs. |
| Operations Budget \| Transportation | Rollup | Operational ground transport costs. |
| Operations Budget \| Activities | Rollup | Operational activity costs. |
| Operations Budget \| Internal Flights | Rollup | Operational in-country flight costs. |
| Operations Budget \| Other | Rollup | Operational costs not in another category. |

## Cost rollups — Executed version (Closing)

Actuals, filtered to the **Executed** Program Version. Read-only.

| Field | Type | What it's for |
|---|---|---|
| Closing \| USD Total | Rollup | Total actual cost across all categories. |
| Closing \| Accommodations | Rollup | Actual accommodation costs. |
| Closing \| Meals | Rollup | Actual meal costs. |
| Closing \| Transportation | Rollup | Actual ground transport costs. |
| Closing \| Activities | Rollup | Actual activity costs. |
| Closing \| Internal Flights | Rollup | Actual in-country flight costs. |
| Closing \| Other | Rollup | Actual costs not in another category. |
| Closing \| Flights | Rollup | Actual flight costs. |
| Closing \| AC Total USD | Rollup | Total actual Associated Costs. *(Base description still says "Quote version" — check before relying on it.)* |
| Closing \| AC Preparation Days | Rollup | Actual preparation-day costs. |
| Closing \| AC Essentials | Rollup | Actual essentials costs. |
| Closing \| AC Staffing | Rollup | Actual staffing costs. |
| Closing \| AC Other | Rollup | Actual other Associated Costs. *(Base description mistakenly says Staffing/Quote.)* |

## Cost rollups — Forecast

Associated Costs used for forecasting. Read-only.

| Field | Type | What it's for |
|---|---|---|
| Forecast \| AC Total USD | Rollup | Total forecast Associated Costs. |
| Forecast \| AC Preparation Days | Rollup | Forecast preparation-day costs. |
| Forecast \| AC Essentials | Rollup | Forecast essentials costs. |
| Forecast \| AC Staffing | Rollup | Forecast staffing costs. |
| Forecast \| AC Other | Rollup | Forecast other Associated Costs. |

## Quoted totals

What was actually quoted or paid per category, from HBH Blocks. Read-only.

| Field | Type | What it's for |
|---|---|---|
| Quoted Total Cost \| USD Total | Rollup | Total quoted cost across all categories. |
| Quoted Total Cost \| Accommodations | Rollup | Quoted accommodation costs. |
| Quoted Total Cost \| Meals | Rollup | Quoted meal costs. |
| Quoted Total Cost \| Transportation | Rollup | Quoted ground transport costs. |
| Quoted Total Cost \| Activities | Rollup | Quoted activity costs. |
| Quoted Total Cost \| Internal Flights | Rollup | Quoted in-country flight costs. |
| Quoted Total Cost \| Other | Rollup | Quoted costs not in another category. |
| Quoted Total Cost \| Flights | Rollup | Quoted flight costs. |
| Quoted Total Cost \| Tour Operator | Rollup | Quoted tour-operator / DMC costs. |

## Finance — income and invoicing

| Field | Type | What it's for |
|---|---|---|
| FIN \| Income Ground Program | Formula | Expected ground income: land price per student × SOT students. |
| FIN \| Income Flights Estimate | Formula | Expected flights income: flight estimate per person × SOT students. |
| FIN \| Additional Ground Invoiced | Rollup | Sum of linked invoices that are **not** categorised as Flights. |
| FIN \| Additional Flights Invoiced | Rollup | Sum of linked invoices categorised as Flights. |
| FIN \| Program Income | Formula | Total expected income: ground + flights + both additional invoiced figures. |
| FIN \| Ground Income | Formula | Ground share of expected income. Used for ground margin. |
| FIN \| Flights Income | Formula | Flights share of expected income. Used for flights margin. |
| FIN \| Total Invoiced | Rollup | Sum of invoiced amounts across all linked invoices. |
| FIN \| Total Paid | Rollup | Sum of invoices marked Complete. |
| FIN \| Unpaid Invoices Total | Rollup | Sum of invoices marked Sent & Pending. |
| FIN \| Invoice Pending | Formula | Expected income not yet invoiced: Program Income − Total Invoiced. |
| FIN \| School Unpaid Balance | Formula | Expected income not yet paid: Program Income − Total Paid. |
| Finance Closing Comments | Long text (rich) | Finance's notes when closing out the program. |

## Finance — performance by category

For each category: **Forecast Performance $/%** compares budget against forecast or quote; **Performance $/%** compares budget against actual (Closing). All are read-only formulas.

| Field | Type | What it's for |
|---|---|---|
| FIN \| Accommodations Forecast Performance $ | Formula | Forecast variance in dollars, accommodations. |
| FIN \| Accommodations Forecast Performance % | Formula | Forecast variance as a percentage, accommodations. |
| FIN \| Accommodations Performance $ | Formula | Actual variance in dollars, accommodations. |
| FIN \| Accommodations Performance % | Formula | Actual variance as a percentage, accommodations. |
| FIN \| Activities Forecast Performance $ | Formula | Forecast variance in dollars, activities. |
| FIN \| Activities Forecast Performance % | Formula | Forecast variance as a percentage, activities. |
| FIN \| Activities Performance $ | Formula | Actual variance in dollars, activities. |
| FIN \| Activities Performance % | Formula | Actual variance as a percentage, activities. |
| FIN \| Transportation Forecast Performance $ | Formula | Forecast variance in dollars, transportation. |
| FIN \| Transportation Forecast Performance % | Formula | Forecast variance as a percentage, transportation. |
| FIN \| Transportation Performance $ | Formula | Actual variance in dollars, transportation. |
| FIN \| Transportation Performance % | Formula | Actual variance as a percentage, transportation. |
| FIN \| Meals Forecast Performance $ | Formula | Forecast variance in dollars, meals. |
| FIN \| Meals Forecast Performance % | Formula | Forecast variance as a percentage, meals. |
| FIN \| Meals Performance $ | Formula | Actual variance in dollars, meals. |
| FIN \| Meals Performance % | Formula | Actual variance as a percentage, meals. |
| FIN \| Other Forecast Performance $ | Formula | Forecast variance in dollars, other. |
| FIN \| Other Forecast Performance % | Formula | Forecast variance as a percentage, other. |
| FIN \| Other Performance $ | Formula | Actual variance in dollars, other. |
| FIN \| Other Performance % | Formula | Actual variance as a percentage, other. |
| FIN \| Internal Flights Forecast Performance $ | Formula | Forecast variance in dollars, internal flights. |
| FIN \| Internal Flights Forecast Performance % | Formula | Forecast variance as a percentage, internal flights. |
| FIN \| Internal Flights Performance $ | Formula | Actual variance in dollars, internal flights. |
| FIN \| Internal Flights Performance % | Formula | Actual variance as a percentage, internal flights. |
| FIN \| Flights Performance $ | Formula | Actual variance in dollars, flights. |
| FIN \| Flights Performance % | Formula | Actual variance as a percentage, flights. |
| FIN \| Preparation Days Forecast Performance $ | Formula | Forecast variance in dollars, preparation days. |
| FIN \| Preparation Days Forecast Performance % | Formula | Forecast variance as a percentage, preparation days. |
| FIN \| Preparation Days Performance $ | Formula | Actual variance in dollars, preparation days. |
| FIN \| Preparation Days Performance % | Formula | Actual variance as a percentage, preparation days. |
| FIN \| Essentials Forecast Performance $ | Formula | Forecast variance in dollars, essentials. |
| FIN \| Essentials Forecast Performance % | Formula | Forecast variance as a percentage, essentials. |
| FIN \| Essentials Performance $ | Formula | Actual variance in dollars, essentials. |
| FIN \| Essentials Performance % | Formula | Actual variance as a percentage, essentials. |
| FIN \| Staffing Forecast Performance $ | Formula | Forecast variance in dollars, staffing. |
| FIN \| Staffing Forecast Performance % | Formula | Forecast variance as a percentage, staffing. |
| FIN \| Staffing Performance $ | Formula | Actual variance in dollars, staffing. |
| FIN \| Staffing Performance % | Formula | Actual variance as a percentage, staffing. |
| FIN \| Other AC Forecast Performance $ | Formula | Forecast variance in dollars, other associated costs. |
| FIN \| Other AC Forecast Performance % | Formula | Forecast variance as a percentage, other associated costs. |
| FIN \| Other AC Performance $ | Formula | Actual variance in dollars, other associated costs. |
| FIN \| Other AC Performance % | Formula | Actual variance as a percentage, other associated costs. |

> Most of these fields share a copy-pasted description in the base ("Forecasted Performance $ Accommodations"). The descriptions above reflect what each field actually calculates.

## Booking progress

Counts and status formulas showing how far OPS has got with bookings. Read-only unless noted.

| Field | Type | What it's for |
|---|---|---|
| # of Bookings Completed | Count | HBH records marked Booking Completed on the Quote version. |
| # of Bookings Needed | Count | HBH records that still need OPS to book something. |
| % Bookings Completed | Formula | Share of HBH records with a completed booking. |
| Flights \| Booked | Count | Program flights (arrival/departure plus internal) already booked. |
| Flights \| # of Program Flights | Count | Total program flights needing a booking. |
| Program Flights Completion Status | Formula | Overall booking status for flights. |
| Transportation \| Booked | Count | Ground transport items booked. |
| Transportation \| # of Bookings | Count | Ground transport items needing a booking. |
| Transportation Completion Status | Formula | Overall booking status for transportation. |
| Meals \| Booked | Count | Meals booked. |
| Meals \| # of Bookings | Count | Meals needing a booking. |
| Meals Completion Status | Formula | Overall booking status for meals. |
| Accommodations \| Booked | Count | Accommodation items booked. |
| Accommodations \| # of Bookings | Count | Accommodation bookings needed on the Quote version. |
| Accommodations Completion Status | Formula | Overall booking status for accommodation. *(Base note flags the conditions need revising.)* |
| Other \| Booked | Count | Other items booked. |
| Other \| # of Bookings | Count | Other items needing a booking. |
| Other Completion Status | Formula | Overall booking status for other items. |
| Arrival/Departure Flights Status | Single select | Manual status for the school's international flights. |
| In-Country Flights Status | Single select | Manual status for in-country flights. |

## Payment and refund deadlines

Enter the number of days in the "Days Prior" field; the matching date is calculated back from the program start date.

| Field | Type | What it's for |
|---|---|---|
| Days Prior for 100% Refund Rate | Number | Days before start when a 100% refund still applies. |
| 100% Refund Rate Date | Formula | The resulting 100% refund cut-off date. |
| Days Prior for 50% Refund Rate | Number | Days before start when a 50% refund still applies. |
| 50% Refund Rate Date | Formula | The resulting 50% refund cut-off date. |
| Days Prior for Deposits | Number | Days before start the deposit is due. |
| Date For Deposit | Formula | The resulting deposit due date. |
| Days Prior for Balance Payment | Number | Days before start the balance is due. |
| Balance Payment Date | Formula | The resulting balance due date. |
| Days Prior for Confirmed Flights | Number | Days before start flights must be confirmed. |
| Confirmed Flights Date | Formula | The resulting flight confirmation deadline. |
| Days Prior for Registration Deadline | Number | Days before start registration closes. |
| Registration Deadline Date | Formula | The resulting registration deadline. |

## Program content, staffing and automation flags

| Field | Type | What it's for |
|---|---|---|
| Program Themes | Long text (rich) | Themes the program explores. Free text. |
| Program Lenses of Inquiry | Long text (rich) | Lenses of inquiry framing the program. Free text. |
| Staffing Requirements | Long text (rich) | Staffing requirements requested by OPS or EM. |
| Staffing Rooming | Single select | Staff rooming setup decided by S&R. |
| Staffing Rooming Notes | Single line text | Extra notes on the rooming setup. |
| Debrief General Program Notes | Long text (rich) | Notes captured at the post-program debrief. |
| Executed version created? | Checkbox | Triggers the automation that creates the Executed version. **Do not delete.** |
| Pre-ops costs executed version created? | Checkbox | Marks that Executed-version pre-ops costs have been generated. |

---

# 4. Program Pricing Tiers

Confirmed price tiers for a live program — the equivalent of I&B Pricing Tier, once the program exists.

| Field | Type | What it's for |
|---|---|---|
| Program Pricing Tier | Formula | Tier name: cleaned-up program name plus the student, faculty and field staff numbers. |
| Program | Link → Programs | The program this tier belongs to. |
| Program Name | Lookup | Program name from the linked record. |
| I&B Price Tier Finance Linked to Program | Lookup | The original I&B tiers, shown as a reference when setting these. Confirm the PT/EL Lead hasn't changed them. |
| Tier Min Number Students | Number | Lowest student count this tier applies to. |
| Tier Max Number Students | Number | Highest student count this tier applies to. |
| Tier Number of Faculty | Number | Faculty assumed in this tier. |
| Tier Number of Field Staff | Number | Field staff assumed in this tier. |
| Tier Land Price USD | Currency | Land price per student at this tier. |
| Tier Flight Price USD | Currency | Flight price per student at this tier. |
| Tier Total Price | Formula | Land price plus flight price. |
| Price Tier Notes | Long text (rich) | Notes on this tier. |
| Number of Students \| SOT | Lookup | Current SOT student count on the program. |
| Active Price Range | Formula | Flags whether the current student count falls inside this tier. |
| School's Local Currency | Lookup | The school's currency, for quoting. |

---

# 5. Reconciliation Accounts

The chart of accounts. Used to categorise allocations and vendor payments for finance reporting.

| Field | Type | What it's for |
|---|---|---|
| Chart of Accounts Reference | Long text | The account name as it appears in the chart of accounts. |
| COA Code | Long text | Account code. |
| COA Group | Single select | Top-level grouping for the account. |
| COA Sub-Group | Single select | Sub-grouping within the COA group. |
| Airtable Finance Reference | Long text | How this account is referred to inside Airtable finance views. |
| Airtaible Reconciliation Visibility | Single select | Controls where this account shows up during reconciliation. *(Field name is misspelled in the base.)* |
| COA Description | Long text | What this account covers. |
| Allocations | Link → Allocations | Expense allocations tagged to this account. |
| Vendor Payments | Link → Vendor Payments | Vendor payments classified against this account. |
| Income | Single line text | Leftover from the deleted Income table. Safe to ignore. |
| Visible For HQ Office Expenses | Checkbox | Show this account when categorising HQ office expenses. |
| Visible For Program Related Expense | Checkbox | Show this account when categorising program expenses. |

---

# 6. Invoices

Invoices issued to schools. Previously called "School Invoices". Now also covers payments handled directly by parents.

| Field | Type | What it's for |
|---|---|---|
| Income Record ID | Formula | Program name and invoice number, separated by a bar. |
| Program | Link → Programs | The program being invoiced. |
| School | Lookup | School name, from the linked program. |
| Date | Date | Invoice date. |
| Invoice Number | Single line text | Your invoice reference. |
| Invoiced Amount | Currency | Amount invoiced. |
| Invoice Uploaded | Attachment | The invoice document itself. |
| Categories | Single select | Flights or ground. Determines which income rollup on the program this feeds. |
| Proof Of Payment | Attachment | Receipt or transfer confirmation. |
| Invoice Destination Email | Single line text | Where the invoice was sent. |
| Invoice Sent | Checkbox | Tick once the invoice has gone out. |
| Invoice Payment Status | Single select | Sent & Pending, Complete, etc. Drives the paid/unpaid rollups on Programs. |
| Invoice Payment Status Last Updated | Last modified | When the record last changed. |
| Payment Category | Single select | Whether the school handles payment or individual parents do. |

---

# 7. Statements

Bank and card statement uploads. Start of the finance chain: Statements → Expenses → Allocations → Programs.

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Generated identifier for the statement. |
| Type | Single select | Which account or card the statement is for. |
| Period | Single select | The month the statement covers. |
| CSV | Attachment | The statement file. Uploading it creates the Expense records automatically. |
| Created | Created time | When the statement was uploaded. |
| Autonumber | Autonumber | Internal sequential number. |
| Expenses | Link → Expenses | The expense lines parsed out of this statement. |
| Field Staff Profiles | Link → Field Staff Profiles | The staff member responsible for reconciling this statement. |
| Email (from Field Staff Profiles) | Lookup | That person's email address. |
| Reconciler Name | Lookup | That person's name. |
| Reconciler Type | Lookup | What kind of staff member they are. |
| Reconciliation Visibility | Formula | Controls who sees this statement during reconciliation. |
| # of Pending+Partial | Rollup | How many expense lines are still unreconciled or only partly done. |
| Status | Formula | Overall reconciliation status for the statement. |
| Record Id | Formula | Airtable record ID, used to build links into the Softr portal. |
| Allocations | Link → Allocations | Allocations made against this statement. |
| CC Last 4 Digits | Single line text | Last four digits of the card, where relevant. |
| Income | Single line text | Leftover from the deleted Income table. Safe to ignore. |

---

# 8. Expenses

Individual transactions parsed from statements. Each one gets reconciled by splitting it into Allocations.

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Generated identifier for the expense line. |
| Description | Long text | Transaction description from the statement. |
| Date | Date | Transaction date. |
| Post Date | Date | Date the transaction posted to the account. |
| Amount (USD) | Currency | Amount in US dollars. |
| Amount (Local Currency) | Number | Amount in the currency it was charged in. |
| Exchange Rate | Formula | Cost of 1 USD in local currency — local amount ÷ USD amount. |
| Local Currency | Link → Currencies | The currency the transaction was made in. |
| Balance | Currency | Account balance after the transaction. |
| Category | Single line text | Category as it came from the statement file. |
| Type | Single line text | Transaction type from the statement file. |
| Cardholder | Single line text | Name on the card. |
| Card Last4 | Single line text | Last four digits of the card used. |
| Reference Number | Single line text | Bank reference for the transaction. |
| Memo | Long text | Memo line from the statement. |
| Source CSV | Single select | Which uploaded file this line came from. |
| Statement Link | Link → Statements | The statement this line belongs to. |
| Statement Period | Lookup | Period of the linked statement. |
| Field Staff Profiles from Statement | Lookup | Reconciler inherited from the statement. |
| Record Id (from Statement Link) | Lookup | Record ID of the linked statement. |
| Back to Statements | Formula | Clickable link back to the statement in the Softr portal. |
| Reconciler Name | Lookup | Who is responsible for reconciling this line. |
| Field Staff Profiles | Link → Field Staff Profiles | Staff member the expense is attributed to. |
| Email (from Field Staff Profiles) | Lookup | That person's email. |
| Staff Type | Lookup | That person's staff type. |
| Status | Single select | Reconciliation status of this expense. |
| Allocations | Link → Allocations | How this expense has been split across programs and accounts. |
| Allocated Amount Rollup | Rollup | Total already allocated. |
| Amount Pending Reconciliation | Formula | Local amount minus what's been allocated — what's still outstanding. |
| transferred_check | Formula | Internal check flag for transfers. |
| Expense Reconciliation Type | Single select | How this expense should be reconciled. |
| Revised by Finance | Checkbox | Finance has reviewed this line. |
| Program Placehodler | Link → Programs | Program the expense relates to. *(Field name is misspelled in the base.)* |
| Direction | Single select | Whether money went out or came in. |

---

# 9. Allocations

Where reconciliation actually happens: each record charges part of an expense to a program and an account.

| Field | Type | What it's for |
|---|---|---|
| Allocation ID | Formula | Generated identifier for the allocation. |
| Allocated Amount | Currency | How much of the expense this allocation covers. |
| Expenses | Link → Expenses | The expense being allocated. |
| Program Linked | Link → Programs | The program being charged. |
| Category | Link → Reconciliation Accounts | The chart-of-accounts line being charged. |
| Airtable Finance Reference (from Category) | Lookup | Finance reference for the selected account. |
| Statements | Link → Statements | The statement the expense came from. |
| Status | Formula | Whether this allocation is complete. |
| Description (from Expenses) | Lookup | Description of the underlying expense. |
| Amount Pending Reconciliation (from Expenses) | Lookup | What's still unallocated on the underlying expense. |
| Field Staff Profiles (from Expenses) | Lookup | Staff member the expense belongs to. |
| Email (from Field Staff Profiles) (from Expenses) | Lookup | That person's email. |
| Reconciliation Visibility (from Statements) | Lookup | Visibility setting from the statement. |
| text Reconciliation Visibility (from Statements) | Formula | The same value as plain text, for filtering. |
| Receipt | Attachment | Receipt backing this allocation. |
| I don't have a receipt. | Checkbox | Tick if no receipt exists — explain in Observations. |
| Observations | Long text (rich) | Notes about the allocation, including missing receipts. |
| ID | Autonumber | Internal sequential number. |

---

# 10. Associated Costs

Costs that sit outside the day-by-day itinerary — preparation days, essentials, staffing and other. Snapshotted per Program Version.

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Generated identifier for the cost line. |
| Type | Single select | Which cost bucket this belongs to (Preparation Days, Essentials, Staffing, Other). |
| Program | Link → Programs | The program this cost belongs to. |
| Program Versions | Link → Program Versions | Which version (Budget / Operational / Executed) this cost counts towards. Shown as "Pre-Ops Costs" on the other side. |
| Version (from Program Versions) | Lookup | The version name. |
| Name | Single line text | What the cost is. |
| Comments | Long text | Notes on the cost. |
| Unit Price | Currency | Price per unit. |
| Cost Basis | Single select | How the cost scales — per person, per day, flat, etc. |
| No. Pax | Number | Number of people the cost applies to. |
| # Days | Number | Number of days the cost applies for. |
| Budget Cost USD | Formula | Calculated budget cost from unit price, basis, pax and days. |
| Closing Cost USD | Currency | Actual cost at closing. |
| Included? | Single select | Whether this cost is included in the price to the school. |
| Number of Students (from Program) | Lookup | Student count on the program. |
| Number of Faculty (from Program) | Lookup | Faculty count on the program. |
| Number of Field Staff (from Program) | Lookup | Field staff count on the program. |
| Total No. of Participants (from Program) | Lookup | Total headcount on the program. |
| Total No. of Participants (from Program Versions) | Lookup | Total headcount on the selected version. |
| Students (from Program Versions) | Lookup | Student count on the selected version. |
| Teachers (from Program Versions) | Lookup | Faculty count on the selected version. |
| Staff (from Program Versions) | Lookup | Staff count on the selected version. |
| Manual sort | Manual sort | Drag-and-drop ordering. |
| manual_sorting_executed | Single line text | Internal helper for sort order on the Executed version. |

---

# 11. Vendor Payments

Payment requests raised against vendors. Most banking details are pulled from the Vendors record — update them there, not here.

| Field | Type | What it's for |
|---|---|---|
| Payment Request ID | Formula | Requester and program, separated by a bar. |
| Payment Request Label | Single line text | Short label so people can spot the request, e.g. "Quito Hotel". |
| Program | Link → Programs | The program being charged. |
| Program Name | Lookup | Program name from the linked record. |
| Destination | Lookup | Destination of the linked program. |
| Requested By | Link → ENVOYS HQ | Who raised the request. |
| Vendor | Link → Vendors | Who is being paid. |
| Form of Payment | Single select | Wire Transfer, Gusto, Paypal, Check or Zelle. |
| Payment Classification | Link → Reconciliation Accounts | Which chart-of-accounts line this payment sits under. |
| Transfer Currency | Link → Currencies | Currency the money is sent in. |
| Transfer Amount | Currency | Amount to send. |
| Confirm Transfer Amount | Number | Re-enter the amount as a check against typos. |
| Transfer Amount Match Check | Formula | Shows OK if the two amounts match, a warning if they don't. |
| Amount in USD | Currency | Equivalent amount in US dollars. |
| Payment Request Attachments | Attachment | Invoice, quote or other supporting files. |
| Payment Request Information | Long text (rich) | Anything else Finance should know about this payment. |
| Payment Date | Date | Date the payment was made or is scheduled for. |
| Work Days Until Payment Due | Formula | Working days between today and the payment date. |
| Status | Single select | Where the request sits in Finance's queue. |
| Proof Of Payment | Attachment | Transfer confirmation once paid. |
| ID | Autonumber | Internal sequential number. |
| Created By | Created by | Who created the record. |
| Beneficiary Name | Lookup | Who actually receives the money, from the vendor record. |
| Country (Financial Details) | Lookup | Beneficiary's country, from the vendor record. |
| Currency (Financial Details) | Lookup | Vendor's preferred currency. |
| Address (Financial Details) | Lookup | Beneficiary's address. |
| Account Type | Lookup | Vendor's account type. |
| Account Number | Lookup | Vendor's account number. |
| SWIFT/BIC Code | Lookup | Vendor's SWIFT/BIC. |
| IBAN Number | Lookup | Vendor's IBAN. |
| Routing Number (from Vendor) | Lookup | Vendor's routing number (US accounts). |
| Payment Information Additional Notes | Lookup | Extra payment notes held on the vendor record. |
| Vendor Payment Information Timestamp | Lookup | When the vendor's payment details were last updated. |
| Finance Information Update | Lookup | When Finance last touched the vendor's details. |
| Vendor Registered In Bank | Lookup | Whether the vendor is already set up with the bank. |
| Vendor Registration Timestamp | Lookup | When the vendor was registered with the bank. |

---

# 12. Currencies

Currency reference, linked from most financial tables.

| Field | Type | What it's for |
|---|---|---|
| Currency | Single line text | Currency code, e.g. USD, EUR, COP. |
| Currency Name | Single line text | Full name of the currency. |
| Exchange Rate to USD | Number | Conversion rate to US dollars. Keep this current. |
| Associated Country | Link → Countries | Country or countries using this currency. |
| Field Staff Profiles | Link → Field Staff Profiles | Staff paid in this currency. |
| Schools | Link → Schools | Schools quoted in this currency. |
| Vendors | Link → Vendors | Vendors paid in this currency. |
| Program Field Staff Assignments | Link → Program Field Staff Assignments | Staff contracts denominated in this currency. |
| Vendor Payments | Link → Vendor Payments | Payments sent in this currency. |
| Expenses | Link → Expenses | Expenses charged in this currency. |

---

# 13. Program Versions

Budget, Operational and Executed snapshots of a program. Every cost record points at one of these so the rollups land in the right column.

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Generated identifier for the version. |
| Programs | Link → Programs | The program this version belongs to. |
| Version | Single select | Budget, Operational or Executed. |
| Students | Number | Student count used for calculations in this version. |
| Faculty | Number | Faculty count used for calculations in this version. |
| Staff | Number | Staff count used for calculations in this version. |
| Total No. of Participants | Formula | Total headcount for this version. |
| HBH Blocks | Link → HBH Blocks | Itinerary line items priced against this version. |
| Pre-Ops Costs | Link → Associated Costs | Associated costs counted in this version. |
| Allocations | Single line text | Leftover stub, not a working link. Safe to ignore. |

---

# 14. HBH Days

One record per day of the itinerary. Parent of HBH Blocks. Shown on Programs as "Itinerary Days".

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Day number, date (e.g. Tue Jan 3) and program name combined. |
| Day # | Formula | Display version of the day number. |
| Day Number | Number | The day's position in the itinerary. |
| Date | Date | Calendar date of this day. |
| Date Formula | Formula | Date derived from the program start date and day number. |
| Program | Link → Programs | The program this day belongs to. |
| Program Name (from Program) | Lookup | Program name. |
| Start Date (from Program) | Lookup | The program's start date. |
| HBH Blocks | Link → HBH Blocks | The itinerary items scheduled on this day. |
| # of Activities | Count | How many items are scheduled on this day. |

---

# 15. HBH Blocks

The Hour-By-Hour: one record per itinerary line item, carrying its timing, vendor, booking status and cost. This is where day-to-day operations and program costing meet.

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Generated identifier for the itinerary item. |
| Name | Single line text | What the item is. |
| Booking Name | Formula | Display name used on booking views. |
| Itinerary Day | Link → HBH Days | The day this item sits on. |
| Day # | Lookup | Day number, from the linked day. |
| Date | Lookup | Calendar date, from the linked day. |
| Start Time | Single line text | When the item starts. |
| End Time | Single line text | When the item ends. |
| Categories | Link → HBH Categories | Accommodation, Meals, Transportation, Activities, Internal Flights or Other. |
| Location | Link → Locations | Where the item takes place. |
| Destination | Lookup | Destination of that location. |
| Vendor | Link → Vendors | Supplier delivering this item. |
| Programs | Link → Programs | The program this item belongs to. |
| Program | Lookup | Program name, via the itinerary day. |
| Version (Link) | Link → Program Versions | Sets whether this item counts as Budget, Quote or Executed. **Do not touch.** |
| Version | Lookup | The version name. |
| Booking Status | Single select | Where the booking has got to. |
| Booking Priority | Single select | How urgent this booking is. |
| Payment Status | Single select | Where payment for this item has got to. |
| Cost Basis | Single select | How the cost scales — per person, per day, flat, etc. |
| Unit Cost USD | Currency | Cost per unit in US dollars. |
| Total Forecast Cost USD | Formula | Estimated total, calculated from unit cost, basis and headcount. |
| Quoted Total Cost | Currency | The actual total quoted or paid. |
| Estimate / Quote Difference | Formula | Gap between the forecast and the quoted cost. |
| Local Amount | Currency | Cost in the local currency. |
| Fx Rate Used | Currency | Exchange rate applied to that local amount. |
| Local Amount USD | Currency | The local amount converted to US dollars. |
| Confirmed Payment Date | Date | When payment was confirmed. |
| AdvancePaidFlag | Formula | Internal flag showing whether an advance has been paid. |
| BookingFlag | Formula | Internal flag used by booking-progress counts on Programs. |
| Supporting Link | URL | Booking confirmation, quote or reference link. |
| Total No. of Participants (Versions) | Lookup | Headcount from the linked version, used in cost formulas. **Do not touch.** |
| Students (Versions) | Lookup | Student count from the linked version. |
| Faculty (Versions) | Lookup | Faculty count from the linked version. **Do not touch.** |
| Staff (Versions) | Lookup | Staff count from the linked version. **Do not touch.** |
| Visible To School | Checkbox | Tick to show this item to the school. |
| Visible For Staff | Checkbox | Tick to show this item to field staff. |
| Notes | Long text | Internal notes on the item. |
| Notes for School | Long text (rich) | Notes written for the school to read. |
| Program Debrief Required | Checkbox | Tick if this item needs reviewing at the debrief meeting. |
| Debrief Rating | Single select | Highlight (include every time) / Recommended / Acceptable / Caution (don't repeat). |
| Program Debrief \| Notes | Long text | Debrief notes for this item. |
| autonumber | Autonumber | Internal sequential number. |
| manual_sorting | Number | Internal sort order. |
| Manual sort (Quote) | Manual sort | Drag-and-drop ordering on the Quote version. |
| sequence_order | Number | Internal ordering helper. |

---

# 16. HBH Categories

The category list behind HBH Blocks, also used to categorise vendors.

| Field | Type | What it's for |
|---|---|---|
| Name | Single line text | Category name — Accommodations, Meals, Transportation, Activities, Internal Flights, Other. |
| HBH Blocks | Link → HBH Blocks | Itinerary items in this category. |
| Vendors | Link → Vendors | Vendors that supply this category. |
| Record ID | Formula | Airtable record ID. |
| Vendor Listings | Single line text | Leftover stub, not a working link. Safe to ignore. |

---

# 17. Destinations

The destination knowledge base — everything the team should know before running a program somewhere.

| Field | Type | What it's for |
|---|---|---|
| Id | Formula | Generated identifier for the destination. |
| Destination Name | Single line text | Name of the destination — a country, city or region. |
| Country | Link → Countries | Country the destination sits in. |
| Country Code | Lookup | Phone country code, from the linked country. |
| Locations | Link → Locations | Specific sites and venues within this destination. |
| Vendors | Link → Vendors | Vendors operating here. |
| Programs | Link → Programs | Programs that have run or will run here. |
| I&B Requests | Link → I&B Requests | Requests asking for this destination. |
| Field Staff \| Country Coordinator | Link → Field Staff Profiles | The country coordinator for this destination. |
| Field Staff with Experience | Link → Field Staff Profiles | Staff who have worked here before. |
| Overall Summary | Long text (rich) | General overview of the destination. |
| Travel & Logistics | Long text (rich) | Visas, arrival, departure and permits. |
| Weather Seasons | Long text (rich) | Year-round weather conditions and patterns. |
| Peak / High Seasons to Avoid | Long text (rich) | Times of year to steer clear of. |
| Safety Considerations | Long text (rich) | Safety notes for this destination. |
| Cultural Considerations | Long text (rich) | Cultural notes and sensitivities. |
| Other Notes | Long text | Anything else worth recording. |
| Destination Attachments | Attachment | Supporting documents, maps and photos. |

---

# 18. Countries

Country reference. Also doubles as the phone country-code list, which is why several near-identical "Field Staff Profiles" links exist — each one is the reverse of a different link on the staff record.

| Field | Type | What it's for |
|---|---|---|
| Counties | Formula | Display name for the country. *(Field name is misspelled in the base.)* |
| Name | Single line text | Country name. |
| Region | Single line text | Region the country belongs to. |
| Country Code | Single line text | International dialling code. |
| Destinations | Link → Destinations | Destinations in this country. |
| Schools | Link → Schools | Schools based in this country. |
| Currencies | Link → Currencies | Currencies used here. |
| Vendors | Link → Vendors | Vendors whose banking country this is. |
| Field Staff Profiles 3 | Link → Field Staff Profiles | Staff who live in this country. |
| Field Staff Profiles 4 | Link → Field Staff Profiles | Staff whose phone number uses this dialling code. |
| Field Staff Profiles 5 | Link → Field Staff Profiles | Staff whose emergency contact uses this dialling code. |
| ENVOYS HQ | Link → ENVOYS HQ | HQ staff whose phone number uses this dialling code. |
| School Faculty & Staff Directory | Link → School Faculty & Staff Directory | School contacts using this dialling code. |
| Field Staff Profiles | Single line text | Leftover stub, not a working link. Safe to ignore. |
| Field Staff Profiles 2 | Single line text | Leftover stub, not a working link. Safe to ignore. |
| School Participant Profiles | Single line text | Leftover stub, not a working link. Safe to ignore. |
| Scouting | Single line text | Leftover from the deleted Scouting table. Safe to ignore. |

---

# 19. Locations

Specific places within a destination — towns, sites, venues — used when building the itinerary.

| Field | Type | What it's for |
|---|---|---|
| Name | Single line text | Name of the location. |
| Destinations | Link → Destinations | The destination this location sits inside. |
| HBH Blocks | Link → HBH Blocks | Itinerary items happening here. |
| Vendors | Link → Vendors | Vendors operating at this location. |
| Description | Long text (rich) | What the location is and why it matters. |
| Program Relevance & Associated Themes | Long text (rich) | Which program themes this location supports. |
| Access & Travel Time | Long text (rich) | How to get there and how long it takes. |
| Seasonal Trends: Weather & Tourism | Long text | Weather and tourist volume through the year. |
| Activities Trends | Long text (rich) | What activities work well here. |
| Safety & Cultural Considerations | Long text (rich) | Safety and cultural notes specific to this location. |
| Additional Notes | Long text (rich) | Anything else worth recording. |
| Scouting | Single line text | Leftover from the deleted Scouting table. Safe to ignore. |

---

# 20. Vendors

The vendor directory. **This is the source of truth for banking details** — Vendor Payments reads them from here, so update the vendor record rather than the payment request.

| Field | Type | What it's for |
|---|---|---|
| Vendor Name | Single line text | Trading name of the vendor. |
| Id | Formula | Unique code from vendor name, destination, category and record ID. |
| Category | Link → HBH Categories | What the vendor supplies. |
| Destinations | Link → Destinations | Destinations the vendor covers. |
| Location | Link → Locations | Specific location the vendor operates from. |
| Country | Lookup | Country, from the linked destination. |
| Full Address | Long text (rich) | Street address: line 1, line 2, city/state, ZIP, country. |
| Google Maps Location Link | URL | Google Maps link. Search the place, tap Share, then Copy link. |
| Contact Name | Single line text | Main contact at the vendor. |
| Email | Email | Contact email. |
| Country Code | Lookup | Dialling code for the vendor's country. |
| Phone Number | Phone | Contact phone. **Don't include the country code** — it comes from the field above. |
| Website | URL | Vendor's website. |
| Vendor Status | Single select | Whether the vendor is active and approved. |
| Vendor Rating | Single select | How well the vendor performs. |
| Price Range | Single select | Rough price bracket. |
| Vendor Notes | Long text (rich) | General notes on working with this vendor. |
| Vendor Debrief Notes | Long text | Feedback captured after programs. |
| Vendor Files | Attachment | Contracts, insurance certificates, menus and similar. |
| Vendor Review Timestamp | Last modified | When the vendor record last changed. |
| HBH Link | Link → HBH Blocks | Itinerary items supplied by this vendor. |
| Programs (Link) | Lookup | Programs that have used this vendor. |
| Vendor Listings | Link → Vendor Listings | Priced items this vendor offers. |
| Vendor Payments | Link → Vendor Payments | Payments made to this vendor. |
| Beneficiary Name | Single line text | The person or entity that actually receives payment. |
| Country (Financial Details) | Link → Countries | Country the beneficiary is located in. |
| Currency (Financial Details) | Link → Currencies | Currency money should be transferred in. |
| Address (Financial Details) | Long text (rich) | Beneficiary address — at minimum street, city and ZIP. |
| Account Number | Single line text | Bank account number. |
| Account Type | Single select | Checking, savings, etc. |
| Routing Number | Single line text | Routing number, for US accounts. |
| SWIFT/BIC Code | Single line text | SWIFT or BIC code for international transfers. |
| IBAN Number | Single line text | IBAN, where applicable. |
| Payment Information Additional Notes | Long text (rich) | Extra payment details — mailing address for checks, Paypal or Gusto details if different from the above. |
| Finance Information Update | Last modified | When Finance last updated the payment details. |
| Timestamp \| Vendor Payment Information Update | Last modified | When the payment information last changed. |
| Vendor Registered In Bank | Checkbox | Vendor is set up with the bank. If they haven't been used in a while, compare the two timestamps above before relying on this. |
| Vendor Registration Timestamp | Last modified | When the vendor was registered with the bank. |
| Pre-Ops Costs | Single line text | Leftover stub, not a working link. Safe to ignore. |
| Scouting | Single line text | Leftover from the deleted Scouting table. Safe to ignore. |

---

# 21. Vendor Listings

The priced catalogue behind cost estimates — individual items each vendor offers.

| Field | Type | What it's for |
|---|---|---|
| Vendor Listing ID | Formula | Code built from category, vendor name, destination, location, country code and identifier. |
| Item Name | Single line text | What the item is. |
| Unit Final Cost (USD) | Currency | Final cost per unit in US dollars. |
| Quote Date | Last modified | When this price was last updated. |
| Category | Single select | What kind of item this is. |
| Item Description | Long text | What's included. |
| Item Notes | Long text | Caveats, minimums or conditions on the price. |
| Vendor | Link → Vendors | Who supplies this item. |
| Vendor Name (from Vendor) | Lookup | Vendor name. |
| Destinations | Lookup | Destinations the vendor covers. |
| Location | Lookup | Vendor's location. |
| Country Code (from Vendor) | Lookup | Vendor's country code. |
| Identifier | Autonumber | Internal sequential number used in the listing ID. |

---

# 22. Schools

Client schools.

| Field | Type | What it's for |
|---|---|---|
| School | Formula | Unique identifier combining the autonumber and school name. |
| autonumber | Autonumber | Sequential number that makes each school unique, even if names are similar. |
| School Name | Single line text | Name of the school. |
| School Type | Single select | What kind of school it is. |
| City | Single line text | City the school is in. |
| Country | Link → Countries | Country the school is in. |
| Address | Long text (rich) | Mailing address: line 1, line 2, city/state, ZIP — one per line. |
| Main Contact Name | Single line text | Primary contact at the school. |
| Main Contact Email | Email | Primary contact's email. |
| Main Contact Phone | Phone | Primary contact's phone. |
| Current Account Lead | Link → ENVOYS HQ | The Envoys person who owns this relationship. |
| Programs | Link → Programs | Programs run for this school. |
| I&B Requests | Link → I&B Requests | Itinerary and budget requests from this school. |
| School's Local Currency | Link → Currencies | Currency this school is quoted in. |
| Exchange Rate to USD | Lookup | Conversion rate for that currency. |
| School People Directory | Link → School Faculty & Staff Directory | Contacts at this school. |
| School Image Banner | Attachment | Logo or banner image for school-facing materials. |

---

# 23. School Faculty & Staff Directory

Contacts on the school side — faculty, administrators and trip leaders.

| Field | Type | What it's for |
|---|---|---|
| Full Name | Formula | First, middle and last name, with the position title after a dash if there is one. |
| First Name | Single line text | Given name. |
| Middle Name | Single line text | Middle name. |
| Last Name | Single line text | Family name. |
| Preferred Name | Single line text | What they'd like to be called. |
| Preferred Pronoun | Single line text | Their pronouns. |
| Position Title | Single line text | Their role at the school. |
| Email | Email | Email address. |
| Phone | Phone | Phone number. |
| School Directory Country Code Phone | Link → Countries | Dialling code for their phone number. |
| Address | Long text | Postal address. |
| Contact's School | Link → Schools | The school they work at. |
| Primary contact for Programs | Link → Programs | Programs where they are the main school-side contact. |
| Notes | Long text | Notes about this contact. |
| Notes Section | Long text (rich) | Longer formatted notes. |

---

# 24. School Participant Profiles

Participant registrations arriving from Jotform.

> 🔒 **Sensitive data.** This table holds passport numbers, dates of birth, home addresses, parent contact details and full medical histories. Only share what a task actually needs, and think carefully before adding these fields to any interface or export.

## Identity and registration

| Field | Type | What it's for |
|---|---|---|
| Participant ID | Formula | Participant name, passport number and date of birth combined. |
| Participant Full Name | Formula | Full name, including middle name if given. |
| Participant First Name | Single line text | Given name. |
| Participant Middle Name | Single line text | Middle name. |
| Participant Last Name | Single line text | Family name. |
| Preferred Name | Single line text | What they'd like to be called. |
| Preferred Pronoun | Single line text | Their pronouns. |
| Date of Birth | Date | Date of birth. |
| Participant Age During Program Start Date | Formula | Their age in years on the day the program starts. |
| Gender | Single line text | Gender as submitted on the form. |
| Travelers Email | Email | Participant's own email. |
| T-Shirt Size | Single select | Size for program merchandise. |
| Participant Type | Formula | Whether they are a student or faculty, derived from the form answer. |
| Participant Type (From Form) | Single select | The raw participant type submitted on the form. |
| Programs (Link to Database) | Link → Programs | The program they're registered for. |
| Program Name | Single line text | Program name as typed on the form. |
| Start Date of Program | Date | Program start date as submitted. |
| Start Date of Program (From Database) | Lookup | The real start date from the linked program. |
| School (From Database) | Lookup | School name from the linked program. |
| Submission Timestamp | Date & time | When the form was submitted. |
| Registration Date | Formula | Registration date derived from the submission. |
| Created | Created time | When the record was created in Airtable. |
| Jotform Registration Link | URL | Link to the registration form used. |
| Jotform Submission Form ID | Single line text | Jotform's own submission reference. |

## Parent or guardian

| Field | Type | What it's for |
|---|---|---|
| Parent First Name | Single line text | Parent's given name. |
| Parent Last Name | Single line text | Parent's family name. |
| Parent Full Name | Formula | Parent's full name. |
| Parent Email | Email | Parent's email — the main channel for registration comms. |
| Parent/Student Address | Long text | Home address. |

## Passport and travel documents

| Field | Type | What it's for |
|---|---|---|
| Passport Number | Long text | Passport number. |
| Passport Country | Single line text | Country that issued the passport. |
| Passport Expiration Date | Date | When the passport expires. |
| Expiration Date Flags | Formula | Flags passports expiring within 180 days of the program start. |
| Days Until Passport Expiration | Number | Days remaining on the passport. |
| Passport Upload | Attachment | Scan or photo of the passport. |

## Health and dietary — sensitive

| Field | Type | What it's for |
|---|---|---|
| Physical Activity Ability | Single line text | Fitness and mobility level. |
| Swimming Ability | Single line text | Swimming competence. |
| Food Allergies | Single line text | Whether they have food allergies. |
| Food Allergy Severity | Single line text | How severe those allergies are. |
| Food Allergies Details | Long text | Which foods are involved. |
| Food Allergies Symptoms | Long text | What a reaction looks like. |
| Food Allergies Treatment | Long text | How to treat a reaction. |
| Non-food Allergies | Single line text | Whether they have non-food allergies. |
| Non-Food Allergies Severity | Single line text | How severe those allergies are. |
| Non-Food Allergies Symptoms | Long text | What a reaction looks like. |
| Non-Food Allergies Reaction | Long text | Description of past reactions. |
| Non-Food Allergies Treatment | Long text | How to treat a reaction. |
| Carries EpiPen | Single line text | Whether they carry an EpiPen. |
| Dietary Restrictions | Single line text | Whether they have dietary restrictions. |
| Dietary Restrictions Details | Long text | What those restrictions are — share with meal vendors. |
| Current Medications | Single line text | Whether they take regular medication. |
| Medication Information | Long text (rich) | Which medications, doses and timing. |
| Medications Not Taken During Program | Single line text | Whether any medication will be paused. |
| Medications Not Taken During Program Explanation | Long text | Why, and what that means for the field team. |
| Respiratory Issues | Single line text | Whether they have respiratory conditions. |
| Details of Respiratory Issues | Long text | Detail of those conditions. |
| Diabetes | Single line text | Whether they are diabetic. |
| Details of diabetes | Long text | Type, management and what to watch for. |
| Neurological Conditions | Single line text | Whether they have neurological conditions. |
| Details of neurological conditions | Long text (rich) | Detail of those conditions. |
| Chronic / Recurring Medical Conditions | Single line text | Whether they have ongoing conditions. |
| Chronic / Recurring Medical Conditions Details | Long text | Detail of those conditions. |
| Medical Devices | Single line text | Whether they use medical devices. |
| Medical Devices Details | Long text | Which devices and any handling notes. |
| Head Injury | Single line text | History of head injury. |
| Head Injury Details | Long text | Detail and any ongoing effects. |
| Mental Health Treatment | Single line text | Whether they are receiving mental health treatment. |
| Mental Health Treatment Details | Long text | Detail relevant to supporting them in the field. |
| Hospitalized / Crisis Center Admittance | Single line text | History of hospitalisation or crisis-centre admission. |
| Hospitalized / Crisis Center Details | Long text | Detail of those admissions. |
| Eating Disorders | Single line text | History of eating disorders. |
| Eating Disorders Details | Long text | Detail relevant to meals and supervision. |
| Additional Medical Information | Long text | Anything else the field team should know. |
| Medical information Acknowledgment / Consent | Checkbox | Confirms the medical declaration was acknowledged. |

## Emergency, consent and payment

| Field | Type | What it's for |
|---|---|---|
| Emergency Contact Name | Single line text | Who to call in an emergency. |
| Emergency Contact Phone | Long text | Their phone number(s). |
| Photo Release Permission | Single line text | Whether photos of this participant may be used. |
| Signature Assertion | Single line text | Confirms the forms were signed. |
| Payment Status | Single select | Where this participant's payments stand. |
| Total Paid | Currency | Total received from this participant. |
| Financial Aid Details | Long text | Financial aid arrangements. |
| Financial Aid Payments | Long text | Payments made under those arrangements. |
| Flights \| Deviations | Single select | Whether they're travelling separately from the group. |
| Flights \| Notes on Deviations | Long text | Detail of the deviation — arrival, departure or both. |

---

# 25. ENVOYS HQ

The internal staff directory. Every POD assignment on a Program points here; the fields below are the reverse view — "which programs does this person own".

| Field | Type | What it's for |
|---|---|---|
| Name | Formula | Team, first, middle and last name combined. |
| First Name | Single line text | Given name. |
| Middle Name | Single line text | Middle name. |
| Last Name | Single line text | Family name. |
| Team | Single select | Which team they sit on (PT, OPS, EM, S&R, Finance…). |
| Email | Email | Work email. |
| Phone Country Code | Link → Countries | Dialling code for their phone. |
| Phone | Phone | Phone number, without the country code. |
| Slack ID | Single line text | Slack member ID, used by notification automations. |
| Programs PT Pod | Link → Programs | Programs where they are PT Lead. |
| Programs OPS Pod | Link → Programs | Programs where they are OPS Lead. |
| Programs EM Pod | Link → Programs | Programs where they are EM Lead. |
| Programs S&R Pod | Link → Programs | Programs where they are S&R Lead. |
| POD \| HQ Lead | Link → Programs | Programs where they are the HQ emergency contact. |
| POD\| HQ Blackout Lead | Link → Programs | Programs where they cover blackout periods. |
| I&B Requests Owner | Link → I&B Requests | Requests where they are OPS Lead. |
| I&B Requests PT Lead | Link → I&B Requests | Requests where they are PT Lead. |
| Vendor Payments | Link → Vendor Payments | Payment requests they raised. |
| Schools | Link → Schools | Schools where they are the account lead. |
| Statements | Single line text | Leftover stub, not a working link. Safe to ignore. |

---

# 26. Field Staff Profiles

Field staff records — certifications and their expiry tracking, rates, equipment, and the Softr portal login fields.

## Identity and contact

| Field | Type | What it's for |
|---|---|---|
| Staff ID | Formula | Generated unique identifier for the staff member. |
| Full Name | Formula | First, middle and last name combined. |
| First Name | Single line text | Given name. |
| Middle Name | Single line text | Middle name. |
| Last Name | Single line text | Family name. |
| Preferred Name | Single line text | What they'd like to be called. |
| Sex (match travel document) | Single select | Must match the travel document, for flight bookings. |
| Date of Birth | Date | Date of birth. |
| Email | Single line text | Email address. |
| Phone Country Code | Link → Countries | Dialling code for their phone. |
| Phone Number | Phone | Phone number, without the country code. |
| Location | Single line text | Where they're based, as free text. |
| Residence Address | Long text (rich) | Full address: line 1, line 2, neighbourhood/city, ZIP, country. |
| Country of Residence | Link → Countries | Country they live in. |
| Profile Description | Long text | Short bio used when introducing them to schools. |
| Field Staff Photo | Attachment | Profile photo. |
| CV | Attachment | Their CV. |

## Role and expertise

| Field | Type | What it's for |
|---|---|---|
| Staff Type | Single select | What kind of field staff they are. |
| Staff Tier | Single select | Seniority tier, which drives their rate. |
| Country Coordinator Status | Single select | Whether they act as a country coordinator. |
| CC Destinations | Link → Destinations | Destinations they coordinate. |
| Experience in Destinations | Link → Destinations | Destinations they've worked in before. |
| Languages | Multiple select | Languages they speak. |
| Theme Preference | Long text | Program themes they prefer to work on. |
| Able to drive? | Single select | Whether they can drive on programs. |
| Swimming Ability | Single select | Swimming competence. |
| Allergies & Dietary Restrictions | Long text (rich) | Their own allergies and dietary needs. |
| T-Shirt Size | Single select | Size for kit and merchandise. |
| Staff Availability Observation | Long text | Notes on when they're available. |

## Documents and certifications

Each document has an upload, an expiry date and a status formula that flags missing, expired, valid, or expiring within 183 days.

| Field | Type | What it's for |
|---|---|---|
| Passport | Attachment | Passport scan. |
| Passport Number | Single line text | Passport number. Used by the program roster automation. |
| Passport Expiration Date | Date | Passport expiry. |
| Passport Expiration Status | Formula | Missing / expired / valid / expiring within 183 days. |
| Background Check | Attachment | Background check document. |
| Background Expiration Date | Date | When the background check expires. |
| Background Check Expiry Status | Formula | Missing / expired / valid / expiring within 183 days. |
| Driver License | Attachment | Driving licence. |
| Driver License Expiration Date | Date | Licence expiry. |
| Driver License Status | Formula | Missing / expired / valid / expiring within 183 days. |
| Highest Medical Training | Single select | Their highest medical qualification. |
| Medical Certification Expiration Date | Date | When that certification expires. |
| Medical Certification Expiry Status | Formula | Whether the first aid certificate is valid, expired or missing. |
| Life Guard Certification? | Single select | Whether they hold a lifeguard certificate. |
| Lifeguard Certificate | Attachment | The certificate itself. |
| Lifeguard Certificate Expiration Date | Date | Certificate expiry. |
| Lifeguard Certificate Status | Formula | Missing / expired / valid / expiring within 183 days. |

## Pay and finance

| Field | Type | What it's for |
|---|---|---|
| Payment Currency | Link → Currencies | Currency they're paid in. |
| Current Daily Rate | Currency | Their standard daily rate in that currency. |
| Rate USD | Currency | The same rate in US dollars. |
| Payment Detail Notes | Long text (rich) | Bank or payment platform details and notes. |
| Statements | Link → Statements | Statements they're responsible for reconciling. |
| Associated Expenses | Link → Expenses | Expenses attributed to them. |
| Pending Associated Expenses | Count | How many of their expenses are still unreconciled. |
| Total Associated Expenses | Count | Total expenses attributed to them. |
| Has Credit Card? | Single select | Whether they hold a company card. |
| CC Last 4 Digits | Number | Last four digits of that card. |
| Revolut Card | Single select | Whether they have a Revolut card. |
| Gusto Set Up | Checkbox | Whether they're set up for payroll in Gusto. |

## Emergency contact

| Field | Type | What it's for |
|---|---|---|
| PEC Name | Single line text | Personal emergency contact's name. |
| PEC Country Code | Link → Countries | Dialling code for their emergency contact. |
| PEC Phone | Phone | Emergency contact's phone number. |

## Equipment and training

| Field | Type | What it's for |
|---|---|---|
| Has Medical Kit? | Single select | Whether they hold a medical kit. |
| Has Radios? | Single select | Whether they hold radios. |
| Has SPOT? | Single select | Whether they hold a SPOT satellite tracker. |
| SPOT ESN Number | Single line text | Serial number of that tracker. |
| Other Equipment | Single line text | Any other kit they hold. |
| Has SWAG? | Single select | Whether they hold branded merchandise. |
| Training Completed? | Checkbox | Whether they've completed staff training. |
| Training Completion Date | Date | When they completed it. |
| Career Ladder Folder | URL | Their career development folder. |

## Assignments and portal access

| Field | Type | What it's for |
|---|---|---|
| Assigned Programs | Link → Program Field Staff Assignments | Programs they're assigned to. |
| I&B Built | Link → I&B Requests | Itineraries and budgets they've built. |
| SOFTR Permanent Login Link | URL | Their permanent login link for the Softr portal. |
| Magiclink | URL | One-time login link for the portal. |
| Is Admin | Checkbox | Whether they have admin rights in the portal. |
| Avatar | Attachment | Profile picture used in the portal. |
| Softr User Created Time | Date | When their portal account was created. |
| Softr User Last Seen Time | Date & time | When they last used the portal. |

---

# 27. Program Field Staff Assignments

Connects a staff member to a program, and carries their contract, salary, flights and payment tracking.

## Program and staff

| Field | Type | What it's for |
|---|---|---|
| Program Staffing ID | Formula | Program name, role type and staff member combined. |
| Program | Link → Programs | The program they're assigned to. |
| Program Name | Lookup | Program name. |
| Destination (from Program) | Lookup | Where the program takes place. |
| Country of Program | Lookup | Country the program takes place in. |
| Program Start Date | Lookup | Program start date. |
| Program End Date | Lookup | Program end date. |
| Number of Ground Days | Lookup | Days in the field, used to calculate salary. |
| Preparation Days | Lookup | Prep days allocated, used to calculate salary. |
| Selected Field Staff | Link → Field Staff Profiles | Who is assigned. |
| Program Role Type | Single select | The role they're filling on this program. |
| Staff Assignment Status | Single select | Where the assignment stands. |

## Salary

| Field | Type | What it's for |
|---|---|---|
| Staff's Current Daily Rate | Lookup | Their standard daily rate. |
| Staff's Current Daily Rate USD | Lookup | That rate in US dollars. |
| Staff's Accepted Currencies | Lookup | Currencies they can be paid in. |
| Currency for Program Negotiated Staff Salary | Link → Currencies | Currency agreed in this program's contract — what they'll actually be paid in. |
| Program Negotiated Daily Staff Salary | Currency | Daily rate agreed and signed for this program. |
| Solo Program | Checkbox | Tick if they're the only staff member — adds a 10% bonus. |
| Program Director | Checkbox | Tick if they're program director — adds a 10% bonus. |
| Program Negotiated Daily Salary with Applied Bonuses | Formula | Daily rate plus any solo or director bonus. Equals the base rate if neither applies. |
| Negotiated Total Salary | Formula | (Daily rate with bonuses × ground days) + one extra day + (half the daily rate × prep days). Training completion is added to the second payment, not here. |
| Negotiated Total Salary USD | Formula | The same total converted to US dollars. |
| Exchange Rate | Lookup | Rate used for that conversion. |
| Training Completion | Checkbox | Tick once training is done — adds a day's rate to the second payment. |
| Salary Deduction | Currency | Any deduction applied to their pay. |
| Staff Salary Notes | Long text (rich) | Notes on this person's pay for this program. |

## Payments

| Field | Type | What it's for |
|---|---|---|
| Current Payment Date Due | Formula | Next payment date: 10 working days before start if the first payment hasn't gone, or 10 days after the program ends if it has. |
| First Payment Amount | Formula | 50% of the negotiated total salary. |
| First Payment Requested | Checkbox | S&R has asked Finance to pay. |
| First Payment Sent | Checkbox | **Finance only.** Tick once paid so S&R can notify the staff member. |
| Second Payment Ready | Checkbox | The second payment is cleared to go. |
| Second Payment Amount | Formula | The remaining balance, plus a day's rate if training is complete. |
| Second Payment Sent | Checkbox | Tick once the second payment has been made. |
| Second Payment Sent TimeStamp | Last modified | Timestamp used to archive salary requests in the Finance dashboard. |

## Flights and preparation

| Field | Type | What it's for |
|---|---|---|
| Departure Flight Location | Single line text | Airport code they fly out from. |
| Return Flight Location | Single line text | Airport code they return to. |
| Staff Flight Arrival at Destination | Date & time | When they land at the destination, before the program starts. |
| Staff Flight Departure from Destination | Date & time | When they leave the destination after the program ends. |
| Staff Flight Cost | Currency | Actual cost of the ticket in US dollars. |
| Flight Document | Attachment | Flight confirmation document. |
| Flight Ticket Purchased | Checkbox | Ticket has been bought. |
| Flight Email Sent | Checkbox | Confirmation document has been sent to the staff member. |
| Staff First Full Preparation Day | Date | Their first full prep day. |
| Preparation Days Email Sent | Checkbox | Prep days email has gone to the staff member. |

## Contract, cash and meetings

| Field | Type | What it's for |
|---|---|---|
| Contract Status | Single select | Where the contract stands. |
| Contract URL | URL | Link to the signed contract. |
| Program Terms | URL | Link to the program terms they agreed to. |
| Selected for Cash Instructions | Checkbox | They're carrying program cash. |
| Cash Instructionss | Long text (rich) | Instructions for handling that cash. *(Field name is misspelled in the base.)* |
| Confirmed Leftover Cash | Currency | Cash returned at the end of the program. |
| Confirmed Personal Funds | Currency | Their own money spent that needs reimbursing. |
| Program Meetings | Link → Program Meetings | Meetings they're expected at. |
| Program Participants | Single line text | Leftover connector stub. Safe to ignore. |

---

# 28. EM QC Checks

The Experience Management quality-control checklist — one record per program. Most fields are simple gates; the formulas at the top summarise them into a readiness status.

## Status summaries (all calculated)

| Field | Type | What it's for |
|---|---|---|
| EM Checks Status | Formula | Overall readiness across setup, logistics and registration. |
| LOI Registration Period Status | Formula | Complete or Pending for the LOI registration period. |
| Program Confirmed: Minimums Met Status | Formula | Whether the essential pre-departure steps confirm minimums are met. |
| Program Confirmed: Numbers Finalized Status | Formula | Whether registration steps confirm final numbers. |
| Program Confirmed: Registration Complete Status | Formula | Whether registration is fully complete. |
| Program Launch Status | Formula | Whether all QC sign-offs and launch emails are done. |
| Post Program Status | Formula | Whether post-program surveys and debriefs are complete. |

## Program context

| Field | Type | What it's for |
|---|---|---|
| Programs | Link → Programs | The program being checked. |
| Record | Link → OPS QC Checks | The matching OPS checklist record. |
| Program Start Date | Lookup | Program start date. |
| School Flight Departure | Lookup | When the school group leaves the point of origin. |
| School Flight Return (from Programs) | Lookup | When the group arrives back home. |
| Days until program start date | Lookup | Countdown to departure. |
| Program Notes | Lookup | Link to the program notes document. |
| Jotform Registration Link | Lookup | Registration form for this program. |
| POD \| PT Lead | Lookup | Partnerships lead. |
| POD \| OPS Lead | Lookup | Operations lead. |
| POD \| S&R Lead | Lookup | Staffing & Risk lead. |
| POD \| EM Lead | Lookup | Experience Management lead. |
| EM Lead | Lookup | The assigned EM lead. |
| EM Lead Assigned Status | Single select | Whether an EM lead has been assigned yet. |
| Handover Status | Single select | Where the handover from PT to EM stands. |
| Link to Program Dashboard | URL | The school-facing dashboard for this program. |
| Program Website | URL | The program's public website. |
| LOI Email | URL | The letter-of-intent email thread. |
| Link to RAMP Folder | URL | Folder holding the risk assessment documents. |

## School-facing deliverables

| Field | Type | What it's for |
|---|---|---|
| Registration Management | Single select | Who is running registration. |
| Transportation to Program Management | Single select | Who arranges transport to the destination. |
| Program Dashboard Sent to School | Checkbox | Dashboard has been shared. |
| Program Website Sent to School | Checkbox | Website has been shared. |
| Travel Policies Created and Added to Dashboard | Checkbox | Travel policies published to the dashboard. |
| Travel Policies Complete and Signed | Single select | Policies signed off by the school. |
| Hotel Information Document Sent to School | Checkbox | Hotel information shared. |
| Rooming List | Single select | Rooming list status. |
| Packing List | Single select | Packing list status. |
| Contract | Single select | School contract status. |
| Pre Departure Learning Resources | Single select | Pre-departure learning material status. |
| Flight Information | Single select | Flight information status. |
| Flight Information Document Sent to School & Linked in Dashboard | Checkbox | Flight document shared and linked. |
| Final Flight Information in Envault/Dashboard Share with School | Checkbox | Final flight details shared. |
| Program website updated with latest itinerary (Canva) | Single select | Website reflects the current itinerary. |
| Envoys Photo Album on Website/Dashboard | Single select | Photo album published. |
| Final HBH Shared with School | Single select | Final hour-by-hour shared. |

## Risk, safety and staffing

| Field | Type | What it's for |
|---|---|---|
| RAMPS | Single select | Risk assessment and management plans status. |
| Medical RAMP | Single select | Medical risk plan status. |
| Field RAMP Ready | Checkbox | Field risk plan is ready. |
| Destination Report | Checkbox | Destination report completed. |
| Health Safety and Security Manual | Checkbox | Manual prepared for this program. |
| Global Rescue | Single select | Global Rescue coverage arranged. |
| SWAG | Single select | Branded merchandise organised. |
| Envoys Staff Confirmed | Single select | Field staff confirmed for the program. |
| Envoys Staff Profiles | Single select | Staff profiles shared with the school. |

## Registration completeness

| Field | Type | What it's for |
|---|---|---|
| Basic Information | Single select | Participant basic details collected. |
| Dietary Restrictions | Single select | Dietary information collected. |
| Medical Information | Single select | Medical information collected. |
| Emergency Contacts | Single select | Emergency contacts collected. |
| Participant Agreements | Single select | Agreements signed. |
| Passport Copies | Single select | Passport copies collected. |

## Invoicing and payment

| Field | Type | What it's for |
|---|---|---|
| Status on Payment | Single select | Overall payment status for the program. |
| Payment Method | Single select | How the school is paying. |
| Financial Aid | Single select | Whether financial aid is involved. |
| Deposit Invoice | Single select | Deposit invoice status. |
| Balance Invoice | Single select | Balance invoice status. |
| Additional Invoice | Single select | Any additional invoice status. |

## Flights operations

| Field | Type | What it's for |
|---|---|---|
| TLT Ready and Shared with Flight Team | Checkbox | Traveller list ready and handed to the flight team. |
| Ticket Issued Document Ready | Single select | Ticket-issued document prepared. |

## QC sign-off and meetings

| Field | Type | What it's for |
|---|---|---|
| Regional Management QC | Checkbox | Regional management has signed off. |
| Risk and Staff QC | Checkbox | Risk and staffing signed off. |
| Flights QC | Checkbox | Flights signed off. |
| OPS QC | Single select | Operations sign-off. |
| S&R QC | Single select | Staffing & Risk sign-off. |
| FINANCE QC | Single select | Finance sign-off. |
| Flights/Trains QC | Single select | Flights and rail sign-off. |
| EM QC Email Sent to AllHands | Single select | Launch email sent to the whole team. |
| HQ Lead Email Sent to School | Single select | HQ lead introduced to the school. |
| Check In Meeting (School) | Checkbox | Check-in meeting held with the school. |
| Optional Check-In Meeting w/ School | Checkbox | Optional extra check-in held. |
| Orientation Meeting | Checkbox | Orientation meeting held. |
| Team Traveler Meeting | Single select | Traveller team meeting status. |
| Program Handover Meeting | Single select | Handover meeting status. |
| Program's WhatsApp Group | Single select | WhatsApp group set up. |
| Email to Global Ed with Survey | Single select | Post-program survey sent. |
| HQ Debrief Meeting | Single select | Internal debrief held. |
| School Debrief Meeting | Single select | Debrief held with the school. |

## Notes

| Field | Type | What it's for |
|---|---|---|
| EM General Notes | Long text (rich) | General EM notes on this program. |
| EM Deadlines | Long text (rich) | Important EM deadlines. |

---

# 29. OPS QC Checks

The Operations quality-control checklist — one record per program, grouped by booking category. Nearly every check is a single select. "FPF" means Field Program Folder; "HBH" means the Hour-By-Hour itinerary.

## Header

| Field | Type | What it's for |
|---|---|---|
| Name | Formula | Program name with pending or complete QC status appended, based on any unchecked fields. |
| OPS QC Checks Status (Single Select) | Single select | Manual overall status for the checklist. |
| Programs | Link → Programs | The program being checked. |
| Program Name (Linked) | Lookup | Program name. |
| Program Start Date (Linked) | Lookup | Program start date. |
| Due Date | Formula | 15 days before the program start date. |
| EM QC Checks | Link → EM QC Checks | The matching EM checklist record. |

## OPS support and general

| Field | Type | What it's for |
|---|---|---|
| Dates & No. of Travelers Match with OPS Support Program | Single select | Dates and headcount agree with the OPS support provider. |
| OPS Support final payment made | Single select | Final payment to the OPS support provider is done. |
| OPS Support Contract or Final Voucher Saved in FPF | Single select | Contract or voucher filed. |
| All Booking Fields 'Booking Made', 'No Booking Needed' or 'Field Booking Needed' | Single select | Every HBH item has a resolved booking status. |
| Petty Cash Requested to Finance | Single select | Petty cash requested. |
| Expense Sheet Saved in FPF | Single select | Expense sheet filed. |
| Vendor Contact List Saved in FPF | Single select | Vendor contact list filed. |
| Printable HBH Saved in FPF | Single select | Printable itinerary filed. |

## Accommodation

| Field | Type | What it's for |
|---|---|---|
| Hotel Booking or Contract Saved in FPF | Single select | Booking or contract filed. |
| Hotel Contract Dates Match HBH | Single select | Contract dates agree with the itinerary. |
| Breakfast Included in Hotels or Breakfast Added to Staff Budget | Single select | Breakfast is either included or budgeted for. |
| Dietary Restrictions Shared with Hotel for Breakfast | Single select | Hotel knows about dietary needs. |
| Room Distribution Matches Group Size and Gender Distribution | Single select | Rooming works for the group make-up. |
| Rooming List with Traveler Names Sent to Hotel | Single select | Named rooming list sent. |
| Rooming List Saved in FPF | Single select | Rooming list filed. |
| Hotel Price Added to HBH | Single select | Cost entered against the itinerary. |
| Final Payment Made to Hotel | Single select | Hotel paid in full. |
| Hotel Quality Check Completed (Location, Reviews, Rating) | Single select | Hotel vetted on location, reviews and rating. |
| Booking.com Reservations Updated with Group Names | Single select | Reservations show the correct traveller names. |
| Hotel Vendor Contact Saved in Database | Single select | Hotel added to the Vendors table. |
| Hotel Vendor Linked to HBH | Single select | Hotel linked to the relevant itinerary items. |
| Meeting Spaces Confirmed for Activities | Single select | Meeting rooms booked for program activities. |
| Meeting Spaces Confirmed in Hotel | Single select | Hotel meeting spaces confirmed. |
| Night Watchers Booked and Payment Completed | Single select | Overnight security arranged and paid. |
| Nurse Booked and Payment Completed | Single select | On-site nurse arranged and paid. |

## Transportation

| Field | Type | What it's for |
|---|---|---|
| Transport Vendor Contract Dates Match HBH | Single select | Transport contract dates agree with the itinerary. |
| General Envoys Schedule Matches HBH Itinerary (Including Times) | Single select | Vendor's schedule matches ours, times included. |
| Vendor Booked Itinerary Matches HBH | Single select | What the vendor booked matches the itinerary. |
| Bus Size Works for Group Size | Single select | Vehicle is big enough for the group. |
| Transportation Price Added to HBH | Single select | Cost entered against the itinerary. |
| Final Payment Made to Transportation Provider | Single select | Transport provider paid in full. |
| Transportation Vendor Contact Saved in Database | Single select | Provider added to the Vendors table. |
| Transportation Vendor Linked to HBH | Single select | Provider linked to the relevant itinerary items. |
| Hotel Rooms Booked for Bus Drivers | Single select | Driver accommodation arranged. |
| COI or MOU Saved in Folder | Single select | Insurance certificate or MOU filed. |
| Metro Cards Purchased | Single select | Public transport cards bought. |
| Metro Card Delivery or Pick Up Arranged | Single select | Delivery or collection arranged. |

## Trains

| Field | Type | What it's for |
|---|---|---|
| Ticket Dates Match HBH | Single select | Ticket dates agree with the itinerary. |
| One Ticket per Traveler Available (Students, Faculty, Staff) | Single select | Everyone travelling has a ticket. |
| Train Numbers Added to HBH | Single select | Train numbers recorded in the itinerary. |
| Final Train Price Added to HBH | Single select | Cost entered against the itinerary. |
| Name Check Completed | Single select | Names on tickets checked against travel documents. |
| Train Vendor Contact Saved in App | Single select | Rail operator added to the Vendors table. |

## Activities

| Field | Type | What it's for |
|---|---|---|
| Activity Booking Confirmation Document Saved in FPF | Single select | Confirmation filed. |
| Dates in Activity Booking Confirmations Match HBH | Single select | Confirmed dates agree with the itinerary. |
| Times in Activity Booking Confirmations Match HBH | Single select | Confirmed times agree with the itinerary. |
| Final Activity Price Added to HBH | Single select | Cost entered against the itinerary. |
| Final Payment Made to Vendor | Single select | Activity vendor paid in full. |
| Vendor Contact Saved in Database | Single select | Vendor added to the Vendors table. |
| One Ticket per Traveler Available | Single select | Everyone has an activity ticket. |
| Core Activity Description Saved in FPF | Single select | Activity description filed for the field team. |
| Activity MOU Signed and Saved | Single select | MOU signed and filed. |

## Meals

| Field | Type | What it's for |
|---|---|---|
| Restaurant Booking Confirmation Saved in FPF | Single select | Confirmation filed. |
| Dates in Restaurant Booking Confirmations Match HBH | Single select | Confirmed dates agree with the itinerary. |
| Times in Restaurant Booking Confirmations Match HBH | Single select | Confirmed times agree with the itinerary. |
| Numbers in Confirmation Match Total Travelers | Single select | Covers booked match the group size. |
| Final Meal Price Added to HBH | Single select | Cost entered against the itinerary. |
| Final Payment Made to Restaurant | Single select | Restaurant paid in full. |
| Dietary Restrictions and Allergies Shared with Vendor | Single select | Vendor briefed on dietary needs and allergies. |
| If Booked by Staff: Budget Document Shared with Staff | Single select | Field staff have the meal budget document. |
| If Booked by DMC: Restaurant Names and Menu Selection Received and Saved in FPF | Single select | DMC's restaurant and menu choices filed. |
| If Booked by RM: Meal Plan Document Completed and Saved in FPF | Single select | Regional manager's meal plan filed. |

## Notes

| Field | Type | What it's for |
|---|---|---|
| OPS QC Checks Notes | Long text (rich) | General notes on the checklist. |
| OPS Support Notes | Long text | Notes on the OPS support provider. |
| General HBH & FPF Notes | Long text | Notes on the itinerary and program folder. |
| Meals - General Notes | Long text (rich) | General notes on meals. |
| Meals - Specific Notes | Long text | Notes on specific meals or venues. |
| Notes on QC Checks | Long text (rich) | Anything else about the QC process. |

---

# 30. Program Meetings

Meetings scheduled around a program. All meetings are planned in Eastern Time.

| Field | Type | What it's for |
|---|---|---|
| Meeting Name | Formula | Program plus meeting type, or the optional name if the type is "Other". |
| Programs | Link → Programs | The program this meeting is about. |
| Program Name | Lookup | Program name. |
| Program Start Date (from Programs) | Lookup | Program start date, used to propose a meeting date. |
| Program End Date (from Programs) | Lookup | Program end date. |
| Meeting Type | Single select | Which meeting this is — Kickoff, Introduction, Handover, Debrief and so on. Each has its own timing and attendee list. |
| Optional Meeting Name | Single line text | Name to use when the meeting type is "Other". |
| PROPOSED \| Meeting Date | Formula | Suggested date based on the standard timing rules. **A suggestion only** — you must still set a real date. |
| SET \| Meeting Date | Date & time | **Source of truth.** The confirmed date and time, in Eastern Time. |
| Meeting Participants | Single line text | Attendee email addresses, separated by commas. |
| Link to Program Meeting Notes | URL | Notes document for this meeting. |
| Program Field Staff Assignments | Link → Program Field Staff Assignments | Field staff expected at this meeting. |

---

# 31. Program Dashboard

Resources published to the school-facing program dashboard. **Previously called "Program Documents"** — the table ID hasn't changed, so existing scripts still work.

> ⚠️ On the Programs table, the link back to here is the field named **"Program Documents"**, not the one named "Program Dashboard".

| Field | Type | What it's for |
|---|---|---|
| Dashboard Link | Formula | Program name and resource combined. |
| Programs | Link → Programs | The program this resource belongs to. |
| Resource Name | Single select | Which standard resource this is. |
| Resource Description | Formula | Standard description for the selected resource. |
| Other \| Resource Name | Single line text | Name to use when the resource isn't on the standard list. |
| Other \| Resource Description | Single line text | Description for that custom resource. |
| Resource Link | URL | Where the resource lives. |
| Active in Dashboard | Checkbox | Tick to show this resource on the school's dashboard. |

---

# 32. Envoys External Toolkit Base

A catalogue of external tools and resources the team uses. Stands alone — no links to other tables.

| Field | Type | What it's for |
|---|---|---|
| Tool Name | Single line text | Name of the tool or resource. |
| Tool Link | URL | Where to find it. |
| Description of Tool | Long text (rich) | What it does and when to use it. |
| Resource Category | Single select | What kind of resource it is. |
| Tags | Multiple select | Tags for searching and filtering. |
| Open URL | Button | Opens the tool link in a new tab. |

---

# 33. Program Documents

Internal documents attached to a program. **This is a new table** that reuses a name previously used by what is now the Program Dashboard table — always check the table ID.

| Field | Type | What it's for |
|---|---|---|
| Documents ID | Formula | Program name and document combined. |
| Programs | Link → Programs | The program this document belongs to. |
| Docuemnt Name | Single select | Which document this is. *(Field name is misspelled in the base.)* |
| Document Link | URL | Where the document lives. |
| Last Update Timestamp | Last modified | When the record last changed. |
| Document Ready | Checkbox | Tick when the document is finished and usable. |

---

# 34. Utilities

A helper table used by automations and scripts. **Do not delete.** No links to other tables.

| Field | Type | What it's for |
|---|---|---|
| Id | Single line text | Identifier for the utility row. |
| Type | Single select | What kind of helper row this is. |
| Day N° | Number | Day number used by itinerary-generation automations. |

---

*Generated from the live ENVOYS | V.0 base on 13 August 2026. If the base changes, re-generate rather than editing this file by hand.*
