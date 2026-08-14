content/docs/data-vs-interfaces.md# ENVOYS | V.0 — Field Dictionary

**Base:** ENVOYS | V.0 · `appi7EFBj8bLjhbHj` · [Open the base](https://airtable.com/appi7EFBj8bLjhbHj)
**Last refreshed from the live base:** 13 August 2026
**Coverage:** 34 tables · 1,093 fields

## How to read this document

- **Field** — the name exactly as it appears in Airtable. Where a name is misspelled in the base, it is reproduced as-is and flagged, because changing it would break automations.
- **Type** — the Airtable field type in plain English. `Link → X` means the field connects records to the X table.
- **Field ID** — the stable `fld…` identifier. Names can change, IDs cannot. **Always use the ID in scripts, extensions and API calls.**

Each table heading links straight to that table in Airtable. Airtable has no per-field URL, so the field ID is given instead — paste it into a script, or use `Cmd/Ctrl+F` on the field name once the table is open.

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

`tblaB2uiFAvsLUXUG` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblaB2uiFAvsLUXUG)

Itinerary & Budget requests — the stage before a program is confirmed. Each record tracks one request from intake through pricing to migration into a Program.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Itinerary Name | Long text | **Source of truth.** The name must match every outside source exactly or automations break. Use this exact spelling everywhere. | `fldnQhaJnHebg3NOO` |
| I&B Status | Single select | Where the request sits in the workflow. | `fldHwJigtT6o7PTpC` |
| Itinerary & Budget Link | URL | Link to the Itinerary & Budget Google Sheet for this request. | `fldax4e6rHeNjMmcC` |
| PT Program Notes | URL | Link to the Partnerships team's program notes document. | `fldNA61gGcJk9szIo` |
| Destination | Link → Destinations | Where the program is going. If the destination isn't listed, create it in Destinations first. | `fldCy4eH3Y11lg4Kp` |
| OPS Lead | Link → ENVOYS HQ | The Operations person assigned to this request. | `fldQ4YYgxsSzQIAPr` |
| PT Lead | Link → ENVOYS HQ | The Partnerships person assigned to this request. | `fldXOSK4uSKYnvFJC` |
| PT Lead Email | Lookup | Email of the assigned PT Lead, pulled from the HQ directory. | `fldzHpH52E2YuyqNZ` |
| Program Type | Single select | Program type based on the school's location and the kind of program. | `fldwc17vlgHqZabse` |
| Category | Single select | Program category for this request. | `fldKg7028nDnCcvjz` |
| I&B Builder | Link → Field Staff Profiles | The field staff member building the itinerary and budget. | `fld095e9nSnYnSgJY` |
| I&B Build Mode | Single select | How the itinerary is being built (e.g. from scratch vs. adapted). | `fldM93Hgk11hFDDTw` |
| OPS Due Date | Date | Date Operations must deliver the itinerary and budget by. | `flddZUlX6C3Cldt2P` |
| Date Received by Ops | Created time | When the request record was created. Set automatically. | `fldyTYxqGg3AYpP6I` |
| Date Sent to PT | Formula | Date the completed I&B was handed back to Partnerships. | `fldqH5NpRNrprODBY` |
| Status Last Update | Last modified | When anything on this record last changed. | `fldyp4Vhus5pXAlxT` |
| Delivery Time | Formula | How long the request took from intake to delivery. | `fldgc5IlVd7tb3tzE` |
| Themes | Long text (rich) | Themes the school wants the program to explore. | `fldujPKU9QUt4a1XM` |
| School | Link → Schools | The school requesting the program. | `fldMs2MijoLRg2qoq` |
| School Name | Lookup | School name pulled from the linked school record. | `fld2dFumB25HiIqLH` |
| Student Ages | Single select | Age band of the students (Upper School 9–12, Lower School 6–8, Faculty, or Mixed). | `flduyTyV4sY8KHSgZ` |
| Dates Flexibility | Single select | How much the requested dates can move. | `fldC4Ag1lr3oRGw5C` |
| Start Date | Date | Requested arrival date at the destination. | `fldmwcq3g9qZL4EAP` |
| End Date | Date | Requested departure date from the destination. | `fldGPT0Eu43honWF8` |
| Ground Days | Formula | Number of days on the ground, calculated from the start and end dates. | `fldLhK17bojIzXW8C` |
| Number of Students | Number | Students expected on the program. | `fldKZ4lOmIDDx3UxJ` |
| Number of Faculty | Number | School faculty expected on the program. | `fldBD1REvcXy0l097` |
| Number of Field Staff | Number | Envoys field staff expected on the program. | `fldI3tkZ3Dxe2wECw` |
| Number of Participants | Formula | Total headcount — students plus faculty plus field staff. | `fldeRtopitIN4cfWb` |
| PT Target Price | Currency | Price per student Partnerships is aiming to sell at. | `fldROrv6S7rsAlBaM` |
| Target Flights Include Price? | Single select | Whether the target price includes flights. | `fldIPf8dRHM0ylLmv` |
| Air Estimate Price | Currency | Estimated airfare per student. | `fld4ugmpIjMDMm5Gh` |
| Expected Land Price per Student | Formula | Target price minus the air estimate — the land budget per student. | `fldsiz5K3TVjnYxiS` |
| Ranges for Pricing | Long text | Student-count ranges to price against. Use dashes, separated by commas (e.g. 10-15, 16-20). | `fld4BBd7junayoLb0` |
| I&B Notes | Long text (rich) | Free notes on the request. | `fld6jiPRFapxdoc5K` |
| I&B Pricing Tier | Link → I&B Pricing Tier | The pricing tiers built for this request. | `fldFuxIJ5Bt855weW` |
| I&B Land Price Tier Range per Student | Lookup | Land price per student for each tier, shown for reference. | `fldsFVcM7A8DALFye` |
| I&B Price Tier Range Finance | Lookup | Finance's view of the tier pricing, shown for reference. | `fldKO7a67MJsDhfUU` |
| HBH Blocks CSV | Attachment | Staging CSV exported from the I&B Google Sheet. **Upload one file only.** | `fldWPFKiMLfGHTDu9` |
| Essentials CSV | Attachment | Essentials/associated-costs CSV exported from the I&B Google Sheet. | `fldCaeczPYnvHdI48` |
| Step 1 Complete? | Checkbox | Migration step 1 done. Set by the migration process. | `fldvIMbJJX4AF6S59` |
| Step 2 Complete? | Checkbox | Migration step 2 done. Set by the migration process. | `fldoponx9tN0aHc1R` |
| Step 3 Complete? | Checkbox | Migration step 3 done. Set by the migration process. | `fldOfvvqywIu82a4k` |
| Step 4 Complete? | Checkbox | Migration step 4 done. Set by the migration process. | `fld51jHEH8e6XlAgA` |
| Programs | Link → Programs | The confirmed Program this request became, once migrated. | `fld2QA6ZiqnteWUe6` |
| Program Versions (from Programs) | Lookup | Budget/Operational/Executed versions on the resulting program. | `fldPF9aIcrOeac8AF` |
| Proposal Decline / Deferral Reason | Multiple select | Why the school declined or deferred, if they did. | `fld5AWH5nlIdaKABg` |
| Status For Pricing | Single select | Where the request sits in Finance's pricing queue. | `fldUiGd8XtXzjLVa5` |
| Additional Information For Pricing | Long text (rich) | Anything Finance needs to know to price this request. | `fldSMK2i6XI5d8Wfr` |
| Last Modified Time | Last modified | When the record last changed. | `fld8CfY0TuSXFwCO6` |

---

# 2. I&B Pricing Tier

`tblKqUlIZHZBxbMTY` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblKqUlIZHZBxbMTY)

Price tiers attached to an I&B Request. One record per student-count band, each with its own land price and margin.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| I&B Pricing Tier | Formula | Tier card name showing S (students) / F (faculty) / SF (field staff). | `fldXdvfBV1ZMC9pCV` |
| I&B Requests | Link → I&B Requests | The request this tier belongs to. | `fldHwo7BuYN8OgWpR` |
| I&B Land Price Tier Range per Student | Formula | Students, faculty, field staff and land price per student as a whole-dollar amount. | `fld3rJ2Melik79Ny8` |
| I&B Price Tier Finance | Formula | Finance-facing summary of the tier. | `fldBzxJwEs1jb1YXw` |
| I&B Tier Min Students | Number | Lowest student count this tier applies to. | `fldWJxQXjqhN0KJgP` |
| I&B Tier Max Students | Number | Highest student count this tier applies to. | `fld2HxVh7vSOCIFey` |
| I&B Tier Faculty | Number | Faculty assumed in this tier. | `fld3fvKVjUjPVIQ5G` |
| I&B Tier Field Staff | Number | Field staff assumed in this tier. | `fldZ2u4MuCYsi2Mu2` |
| I&B Tier Land Price per Student | Currency | Land price charged per student at this tier. | `fldnB3XUFbPbCEtPF` |
| I&B Tier Low Margin | Percent | Margin at the low end of the tier. | `fldXrN2W7gkSqGUOT` |
| I&B Tier Estimated Profit | Currency | Estimated profit at the low margin. | `fldwSf5h2k7DXdKhd` |
| I&B Tier Top Margin | Percent | Margin at the top end of the tier. | `fldeq2TPy16CkjDHN` |
| I&B Tier Top Estimated Profit | Currency | Estimated profit at the top margin. | `fldXjb8DksDaAoTEE` |
| Pricing Tier Notes | Long text (rich) | Notes on how this tier was built or what it assumes. | `fldWXpfTI7cTkxdW1` |
| Timestamp | Last modified | When the tier last changed. | `fld6DUvP95SAQG2xn` |

---

# 3. Programs

`tblcVh5F1cjtxrQJJ` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblcVh5F1cjtxrQJJ)

The centre of the base. Every confirmed program lives here, and almost every other table connects back to it. 213 fields, grouped below by what they do.

> ⚠️ **Two link fields are named the wrong way round.** "Program Documents" (`fld0ZflZ0h8fqhepG`) actually links to the **Program Dashboard** table, and "Program Dashboard" (`fldQcwuOnjk8DadFq`) links to the **Program Documents** table. This is a leftover from a table rename. Check the table ID, not the field name.

## Identity and basics

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Program ID | Formula | Unique ID combining start date (MM/DD/YY) and program name. | `fldENaBD6a8Pqz9s1` |
| autonumber | Autonumber | Internal sequential number used by automations. **Do not delete.** | `fldEu83QlkAUvBXB9` |
| Program Name | Single line text | **Source of truth.** Usually School (or abbreviation) + Destination + Year, e.g. "LREI Martinique 2026". Use this exact name anywhere outside Airtable. | `fldMARPJK6JYqieUJ` |
| School | Link → Schools | The client school. Uses a unique school identifier so similarly-named schools don't get confused. | `fldv8Hefl4lExeFvN` |
| Destination | Link → Destinations | Where the program goes — a country, city or region. Create it in Destinations first if missing. | `fldYBDulqfyTpSy46` |
| Program Status | Single select | Where the program sits on the timeline (LOI, Confirmed, Operated). | `fldzoy6mFYpDO5mFi` |
| Program Category | Single select | Category assigned using the Program Categorization Tool. | `fldDbzHNceYDythtT` |
| Program Type | Single select | Type based on the school's geography and program style. | `fldjyl9q22H2hvcOr` |
| Period | Single select | American school year the program falls in (2026-2027 = Summer/Fall 2026 through Winter/Spring 2027). | `fldmo7QA34TOXUdRP` |
| Student Ages | Single select | Upper School (9–12), Lower School (6–8), Faculty only, or Mixed. | `fldIphnsk9P08T3da` |
| Country | Lookup | Country of the selected destination. Used to connect people and records across tables. | `fld1HY1TcmZUnzpp5` |
| Jotform Registration Link | URL | Participant registration form for this program. | `fldaZjEcS2Hu6SUzu` |

## Headcount

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Number of Students \| SOT | Number | **Source of truth.** Students expected, and the number the active HBH is built on. Should match Students Registered by the start date. | `fldjrtIRSi5Fx0DVD` |
| Number of Faculty \| SOT | Number | **Source of truth.** Faculty expected, reflected in the active HBH. Should match Faculty Registered by the start date. | `fld6sqpdiwVpLCG41` |
| Number of Field Staff \| SOT | Number | **Source of truth.** Field staff expected, reflected in the active HBH. Should match Staff Assignments by the start date. | `fld7s67V59YqfrEb8` |
| Number of Participants | Formula | Total headcount — students plus faculty plus staff. | `fldvkbRlauPbFN8mI` |
| Min Number Students | Rollup | Lowest student count needed for the program to run, from the negotiated pricing ranges. Fixed unless a new agreement is reached. | `fldbNPCNoIT9sfXwq` |
| Max Number of Students | Rollup | Highest student count expected, from the negotiated pricing ranges. Used by OPS to size bookings. | `fldkCBHSPXmg6Y8uM` |
| Students Registered | Count | How many student registrations are linked to this program. | `fldzXw3uB5RFGzhn1` |
| Faculty Registered | Count | How many faculty registrations are linked. *(Description in the base is a Spanish to-do note — needs review.)* | `fldSHitlI3KGUHFfP` |
| Staff Assigned | Count | How many staff assignments are linked. *(Description in the base is a Spanish to-do note — needs review.)* | `fldzZL8CtK0LZBqe3` |
| Additional Participants Notes | Long text | Details of anyone travelling who isn't a student, faculty member or field staff. | `fldcuWhUB8nFw9PGc` |
| Registration Probability | Percent | Estimated likelihood the program hits minimum numbers and runs. | `fld5mFibIA8X7u0yC` |

## Dates and duration

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Program Start Date \| SOT | Date | **Source of truth.** Day the group arrives at the destination. Sets day 1 of the HBH. | `fldIWYVS5NvkwsyGV` |
| Program End Date \| SOT | Date | **Source of truth.** Day the group departs the destination. Sets the last day of the HBH. | `fldx4I2JhZ4gqcgFS` |
| Number of Ground Days \| SOT | Formula | Days in the field — the days covered by the HBH. | `fldis9573Bigv5htf` |
| Number of Nights | Formula | Nights of accommodation OPS needs to book. | `fldtGJUv0Tb7Nhb5n` |
| School Flight Departure | Date & time | When the group leaves the point of origin. Differs from the start date because of flight time and layovers. | `fldNDfqXSFeaxTkN3` |
| School Flight Return | Date & time | When the group lands back at the point of origin. Differs from the end date for the same reason. | `fldplgZRTVF4ObW35` |
| Days until program start date | Formula | Countdown to the start date. | `fldCkHpKZ3XlFMRxC` |
| Preparation Days | Number | **Source of truth**, set by S&R. Paid prep days allocated to field staff. | `fldzcB0R6cJSTYvU6` |

## POD assignments — who owns this program

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| POD \| PT Lead | Link → ENVOYS HQ | Partnerships lead. | `fldHvKbOtsL5jczAT` |
| POD \| OPS Lead | Link → ENVOYS HQ | Operations lead. | `fldShyX4JHUR74VHE` |
| POD \| EM Lead | Link → ENVOYS HQ | Experience Management lead. | `fldk47f2z0T09GDxn` |
| POD \| S&R Lead | Link → ENVOYS HQ | Staffing & Risk lead. | `fldlSKotDK5jLB8O6` |
| POD \| HQ Lead | Link → ENVOYS HQ | HQ emergency contact for the program. | `fldc1LamtaUblbiLs` |
| POD \| HQ Blackouts Lead | Link → ENVOYS HQ | HQ contact covering blackout periods. | `fldATSYP8XxXOCeaO` |
| EM Lead Assigned Status | Lookup | Whether an EM lead has been assigned, from the EM QC record. | `fldrjl0PhI9FohMlF` |

## Documents and links

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Itineraries & Budgets Document Link | URL | The program's I&B Google Sheet. | `fldVipY1gN62F4WUk` |
| Program Notes Link | URL | The program notes document. | `fldhSb5A373aX6wzF` |
| Whatsapp HQ Field Link | URL | WhatsApp group connecting HQ and the field team. | `fldK1k8Heji1VkgVm` |
| Field Program Folder Link | URL | The Field Program Folder (FPF) for this program. | `flde0gDNEBOLM9S6S` |

## Connections to other tables

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Staff Assignments | Link → Program Field Staff Assignments | Field staff assigned to this program. | `fldKMuL9giep7xO4e` |
| Staff Assignment Status | Lookup | Assignment status pulled from those records. | `fldGwZlT054mdwlM5` |
| Program Pricing Tiers | Link → Program Pricing Tiers | Confirmed price tiers for this program. | `fldhj85oEIxZZxhg7` |
| Itinerary Days | Link → HBH Days | The day-by-day skeleton of the itinerary. | `fldgaVunKx3NvC2Jg` |
| Program Versions | Link → Program Versions | Budget / Operational / Executed snapshots and their headcounts. | `fldWZlcbND9mh00eg` |
| HBH Blocks | Link → HBH Blocks | Every itinerary line item. **Don't touch** — managed by automation. | `fldfHLsLX1drGMNI0` |
| School Participant Profiles | Link → School Participant Profiles | Registrations coming in from Jotform. **Don't touch.** | `fldB1devDP01WiO7X` |
| Associated Costs | Link → Associated Costs | Non-itinerary costs (prep days, essentials, staffing). | `fldhLGcigVKBBlYKp` |
| I&B Requests | Link → I&B Requests | The original request this program came from. | `fldW07KzAtQAEWjX4` |
| EM QC Checks Link | Link → EM QC Checks | The EM quality-control checklist record. | `fldNEMhZ1nhTa1PUL` |
| OPS QC Checks | Link → OPS QC Checks | The OPS quality-control checklist record. | `fld7nSBodi5qVFvW8` |
| OPS QC Checks Status | Lookup | Overall OPS QC status. | `fldSYetyTsIViZ6wH` |
| Program Meetings | Link → Program Meetings | Meetings scheduled for this program. | `fld0F5xjXRGZUvSKx` |
| Program Documents | Link → **Program Dashboard** | ⚠️ Despite the name, links to the Program Dashboard table (school-facing resources). | `fld0ZflZ0h8fqhepG` |
| Program Dashboard | Link → **Program Documents** | ⚠️ Despite the name, links to the Program Documents table (internal documents). | `fldQcwuOnjk8DadFq` |
| School's Directory Contacts | Link → School Faculty & Staff Directory | School-side contacts for this program. | `fldsAiDXwwhppAnUi` |
| Vendor Payments | Link → Vendor Payments | Payment requests raised against this program. | `fld98q3iI9nO2sPoC` |
| School Invoices | Link → Invoices | Invoices issued to the school. | `fld8sXcIeOTis6Vi7` |
| Allocations | Link → Allocations | Expense allocations charged to this program. | `fldYJWISd1tM3ek0H` |
| Expenses | Link → Expenses | Expenses linked directly to this program. | `fldsrqWpfo2HnWlXJ` |
| Income | Single line text | Leftover from the deleted Income table. No longer connected to anything — safe to ignore. | `fldRyyVBOBKBieXEu` |
| Staff Salaries | Single line text | Leftover stub, no longer connected to anything. | `fldeO0b4RjKDW9fcV` |

## Pricing and revenue

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Final Land Price Student in USD | Lookup | Price per student from the pricing tier, set by Finance and agreed with the school. Changes with the SOT student count. | `fldidAFOCkK4GjqXH` |
| Final Land Price Student in Local Currency | Formula | The same price converted into the school's local currency. | `fldxydkKPJ2nUbqYt` |
| School's Local Currency | Lookup | Currency to quote the school in. Reference only. | `fld03PBYzja9MZ2ls` |
| School's Currency Exchange Rate to USD | Lookup | Exchange rate used for that conversion. | `fld0CfwqirNL13drp` |
| Estimaded Total Revenue | Formula | Land price per student × SOT student count. *(Field name is misspelled in the base.)* | `fldEyvs807PDE0QMg` |
| I&B Price Tier Range Finance | Lookup | Pricing tiers from the original I&B request, for reference only — not binding. | `fldOsIuR5Pp3hmjM6` |
| Flight Estimate Per Person | Lookup | Manually entered estimate of the flight price charged per student, in USD. | `fldxrEfN88TzoSt1u` |

## Cost rollups — Budget version

Everything below sums HBH Blocks or Associated Costs filtered to the **Budget** Program Version. All are read-only.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Budget \| USD Total | Rollup | Total budgeted cost across all categories. | `fldl4HPa4pgzfNEgC` |
| Budget \| Accommodations | Rollup | Budgeted accommodation costs. | `fldWoJ962bYNl7woh` |
| Budget \| Meals | Rollup | Budgeted meal costs. | `fldSCNKTGUx2Xptw1` |
| Budget \| Transportation | Rollup | Budgeted ground transport costs. | `fldNRidi9rVUjtxmE` |
| Budget \| Activities | Rollup | Budgeted activity costs. | `fldXtDRizANoeHRuF` |
| Budget \| Internal Flights | Rollup | Budgeted in-country flight costs. | `fldGKDJUpVgbLy7n3` |
| Budget \| Other | Rollup | Budgeted costs not in another category. | `fldSLvEfeIGUiaUfE` |
| Budget \| Flights | Rollup | Budgeted flight costs; should match the I&B Sheet. | `fldm7H0FGDhDNFjL4` |
| Budget \| AC Preparation Days | Rollup | Budgeted preparation-day costs from Associated Costs. | `fldPpHdkmG9Y41pxi` |
| Budget \| AC Essentials | Rollup | Budgeted essentials costs from Associated Costs. | `fld2WLEBigAuPim97` |
| Budget \| AC Staffing | Rollup | Budgeted staffing costs from Associated Costs. | `fldQEBNbv7frM5Nk9` |
| Budget \| AC Other | Rollup | Budgeted other Associated Costs. *(Base description mistakenly says Preparation Days.)* | `fld3Qom7GRcoAiYTf` |
| Budget \| AC Total USD | Rollup | Total budgeted Associated Costs. | `fld31UXm7DRbilSWr` |

## Cost rollups — Operational version

Same categories, filtered to the **Operational** Program Version. Read-only.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Operations Budget \| USD Total | Rollup | Total operational cost across all categories. | `fldagy7xJhxFJWXQk` |
| Operations Budget \| Accommodations | Rollup | Operational accommodation costs. | `fldRsKp5NRcSv7oal` |
| Operations Budget \| Meals | Rollup | Operational meal costs. | `fldiFALmpynncwKnB` |
| Operations Budget \| Transportation | Rollup | Operational ground transport costs. | `fldJjRtGRtNB2R1Iy` |
| Operations Budget \| Activities | Rollup | Operational activity costs. | `fldsZBDaD2F32aXX2` |
| Operations Budget \| Internal Flights | Rollup | Operational in-country flight costs. | `fld9r08rtvYd21UNm` |
| Operations Budget \| Other | Rollup | Operational costs not in another category. | `fldWf2kwz5Sf5J1UA` |

## Cost rollups — Executed version (Closing)

Actuals, filtered to the **Executed** Program Version. Read-only.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Closing \| USD Total | Rollup | Total actual cost across all categories. | `fldtiW41JU5U9NIR4` |
| Closing \| Accommodations | Rollup | Actual accommodation costs. | `fldch1PlNgQaTPHb3` |
| Closing \| Meals | Rollup | Actual meal costs. | `fldEhfiX3EaEKXAD7` |
| Closing \| Transportation | Rollup | Actual ground transport costs. | `fldnFcXV2CRifpE3J` |
| Closing \| Activities | Rollup | Actual activity costs. | `fldRxOAjJBqTsLqQD` |
| Closing \| Internal Flights | Rollup | Actual in-country flight costs. | `fld00eBtzxFPdO9CM` |
| Closing \| Other | Rollup | Actual costs not in another category. | `fldYTzNNVjTCYjpYy` |
| Closing \| Flights | Rollup | Actual flight costs. | `fldvQsU51qS3tZRRF` |
| Closing \| AC Total USD | Rollup | Total actual Associated Costs. *(Base description still says "Quote version" — check before relying on it.)* | `fldpzvcAG4jeghAMT` |
| Closing \| AC Preparation Days | Rollup | Actual preparation-day costs. | `fldxRUGfdsTgdfGNq` |
| Closing \| AC Essentials | Rollup | Actual essentials costs. | `fldCJdsf49aztIqiU` |
| Closing \| AC Staffing | Rollup | Actual staffing costs. | `fldFq6mz0QAsaaGIA` |
| Closing \| AC Other | Rollup | Actual other Associated Costs. *(Base description mistakenly says Staffing/Quote.)* | `fldyUiFE8z5tVPUta` |

## Cost rollups — Forecast

Associated Costs used for forecasting. Read-only.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Forecast \| AC Total USD | Rollup | Total forecast Associated Costs. | `fldN3UJnUPwYrthZT` |
| Forecast \| AC Preparation Days | Rollup | Forecast preparation-day costs. | `fldGxjhvu0HGe0Sp0` |
| Forecast \| AC Essentials | Rollup | Forecast essentials costs. | `fld3pfZzZdLt4ImpM` |
| Forecast \| AC Staffing | Rollup | Forecast staffing costs. | `fldKtcteVZrEWSVom` |
| Forecast \| AC Other | Rollup | Forecast other Associated Costs. | `fldJSajg9G0x5GpR7` |

## Quoted totals

What was actually quoted or paid per category, from HBH Blocks. Read-only.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Quoted Total Cost \| USD Total | Rollup | Total quoted cost across all categories. | `fldqIzVpJ28ATvlrQ` |
| Quoted Total Cost \| Accommodations | Rollup | Quoted accommodation costs. | `fldepGn9g8OKTtVJt` |
| Quoted Total Cost \| Meals | Rollup | Quoted meal costs. | `fldRr1NenC1SRjM0i` |
| Quoted Total Cost \| Transportation | Rollup | Quoted ground transport costs. | `fldJiy4SnJFwirwIY` |
| Quoted Total Cost \| Activities | Rollup | Quoted activity costs. | `fldQbi05utJ81BBb5` |
| Quoted Total Cost \| Internal Flights | Rollup | Quoted in-country flight costs. | `fldqRCdG2lEuJzLTX` |
| Quoted Total Cost \| Other | Rollup | Quoted costs not in another category. | `fldQQQRRz9lJcm3eW` |
| Quoted Total Cost \| Flights | Rollup | Quoted flight costs. | `fldcSf2uOhQqmcM3f` |
| Quoted Total Cost \| Tour Operator | Rollup | Quoted tour-operator / DMC costs. | `fldnFlmSswQocxPjp` |

## Finance — income and invoicing

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| FIN \| Income Ground Program | Formula | Expected ground income: land price per student × SOT students. | `fldwAGiyd0wRspP2x` |
| FIN \| Income Flights Estimate | Formula | Expected flights income: flight estimate per person × SOT students. | `fldNg1wgxbftvaI3S` |
| FIN \| Additional Ground Invoiced | Rollup | Sum of linked invoices that are **not** categorised as Flights. | `fld8bKRkL8VncpCgc` |
| FIN \| Additional Flights Invoiced | Rollup | Sum of linked invoices categorised as Flights. | `fld1tvT6eIB0iwLAt` |
| FIN \| Program Income | Formula | Total expected income: ground + flights + both additional invoiced figures. | `fld0KsmHa0Z1pHCpO` |
| FIN \| Ground Income | Formula | Ground share of expected income. Used for ground margin. | `fldfyIFSthgTscIAk` |
| FIN \| Flights Income | Formula | Flights share of expected income. Used for flights margin. | `fld8E3FWkOW4aIl83` |
| FIN \| Total Invoiced | Rollup | Sum of invoiced amounts across all linked invoices. | `fldKxRfPyDgtGXkN8` |
| FIN \| Total Paid | Rollup | Sum of invoices marked Complete. | `fldFofscJsDr0Cizo` |
| FIN \| Unpaid Invoices Total | Rollup | Sum of invoices marked Sent & Pending. | `fldjpUpvsb6nEhMOw` |
| FIN \| Invoice Pending | Formula | Expected income not yet invoiced: Program Income − Total Invoiced. | `flddlmwACJW5GtMtv` |
| FIN \| School Unpaid Balance | Formula | Expected income not yet paid: Program Income − Total Paid. | `fldpBMpEuoYIrWawz` |
| Finance Closing Comments | Long text (rich) | Finance's notes when closing out the program. | `flds6XWgny6Wjmudw` |

## Finance — performance by category

For each category: **Forecast Performance $/%** compares budget against forecast or quote; **Performance $/%** compares budget against actual (Closing). All are read-only formulas.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| FIN \| Accommodations Forecast Performance $ | Formula | Forecast variance in dollars, accommodations. | `fldc5ox1774pLUwnp` |
| FIN \| Accommodations Forecast Performance % | Formula | Forecast variance as a percentage, accommodations. | `fldD1NbHp0ijFM5aC` |
| FIN \| Accommodations Performance $ | Formula | Actual variance in dollars, accommodations. | `fldjxV2A0DLIRvO8g` |
| FIN \| Accommodations Performance % | Formula | Actual variance as a percentage, accommodations. | `fld9GjeqJ6hU50xz5` |
| FIN \| Activities Forecast Performance $ | Formula | Forecast variance in dollars, activities. | `fldNpF2ljJD7CIVav` |
| FIN \| Activities Forecast Performance % | Formula | Forecast variance as a percentage, activities. | `fldB9d3F7j02SLMxG` |
| FIN \| Activities Performance $ | Formula | Actual variance in dollars, activities. | `fld2RgXTzmgtNiTdK` |
| FIN \| Activities Performance % | Formula | Actual variance as a percentage, activities. | `fldA6aV7uwdWPUznC` |
| FIN \| Transportation Forecast Performance $ | Formula | Forecast variance in dollars, transportation. | `flduHtl76PXXWpuLk` |
| FIN \| Transportation Forecast Performance % | Formula | Forecast variance as a percentage, transportation. | `fldr0eJPE5lezekF8` |
| FIN \| Transportation Performance $ | Formula | Actual variance in dollars, transportation. | `fldeO4wJ5GHrcdjfK` |
| FIN \| Transportation Performance % | Formula | Actual variance as a percentage, transportation. | `fldBuWbfIyWNi6N1s` |
| FIN \| Meals Forecast Performance $ | Formula | Forecast variance in dollars, meals. | `fldkQXv0FRlOHSJ9X` |
| FIN \| Meals Forecast Performance % | Formula | Forecast variance as a percentage, meals. | `fldV9pi6G4hTzDJzS` |
| FIN \| Meals Performance $ | Formula | Actual variance in dollars, meals. | `fldIq6GJ0QFXRKa1q` |
| FIN \| Meals Performance % | Formula | Actual variance as a percentage, meals. | `fldn0QRDSsIRS2FUz` |
| FIN \| Other Forecast Performance $ | Formula | Forecast variance in dollars, other. | `fldBYN6r8F8OZfGxY` |
| FIN \| Other Forecast Performance % | Formula | Forecast variance as a percentage, other. | `fldrEz97nVIFM1UQo` |
| FIN \| Other Performance $ | Formula | Actual variance in dollars, other. | `fldJFVggaaoUO0elI` |
| FIN \| Other Performance % | Formula | Actual variance as a percentage, other. | `fldXHW4NlE4ChCk53` |
| FIN \| Internal Flights Forecast Performance $ | Formula | Forecast variance in dollars, internal flights. | `fld5hPm7D2FUR0mob` |
| FIN \| Internal Flights Forecast Performance % | Formula | Forecast variance as a percentage, internal flights. | `fldvzlBvZBRN9QrNm` |
| FIN \| Internal Flights Performance $ | Formula | Actual variance in dollars, internal flights. | `fldHw4NuiUKGsnij0` |
| FIN \| Internal Flights Performance % | Formula | Actual variance as a percentage, internal flights. | `fldp5wM97zQeXLY2F` |
| FIN \| Flights Performance $ | Formula | Actual variance in dollars, flights. | `fldGR6xo8evVwJ76P` |
| FIN \| Flights Performance % | Formula | Actual variance as a percentage, flights. | `fld6Fk57CPk8Zv2UL` |
| FIN \| Preparation Days Forecast Performance $ | Formula | Forecast variance in dollars, preparation days. | `fldNlJxFhg5ZHs5bI` |
| FIN \| Preparation Days Forecast Performance % | Formula | Forecast variance as a percentage, preparation days. | `fldBRIO9dr7rqrFQp` |
| FIN \| Preparation Days Performance $ | Formula | Actual variance in dollars, preparation days. | `fldramxR5gOSqLPC3` |
| FIN \| Preparation Days Performance % | Formula | Actual variance as a percentage, preparation days. | `fldks1s1xIyBqePQD` |
| FIN \| Essentials Forecast Performance $ | Formula | Forecast variance in dollars, essentials. | `fldK6rhBrig2EDPkU` |
| FIN \| Essentials Forecast Performance % | Formula | Forecast variance as a percentage, essentials. | `fld7zlprVkH5lt0Fb` |
| FIN \| Essentials Performance $ | Formula | Actual variance in dollars, essentials. | `fldzJZR2e9LDc3Zhh` |
| FIN \| Essentials Performance % | Formula | Actual variance as a percentage, essentials. | `fldxgz6d2DhE46Q7k` |
| FIN \| Staffing Forecast Performance $ | Formula | Forecast variance in dollars, staffing. | `fldjiU6WHXUkZ73UA` |
| FIN \| Staffing Forecast Performance % | Formula | Forecast variance as a percentage, staffing. | `fldhP7bXX3k8WcJYo` |
| FIN \| Staffing Performance $ | Formula | Actual variance in dollars, staffing. | `fldhvDJY9FVzTtWER` |
| FIN \| Staffing Performance % | Formula | Actual variance as a percentage, staffing. | `fldEcUwXIZwNbR24N` |
| FIN \| Other AC Forecast Performance $ | Formula | Forecast variance in dollars, other associated costs. | `fldyBlaGVg1k3CViT` |
| FIN \| Other AC Forecast Performance % | Formula | Forecast variance as a percentage, other associated costs. | `fldIJKyDPa1SFZjlC` |
| FIN \| Other AC Performance $ | Formula | Actual variance in dollars, other associated costs. | `fld9gXC0oCKU9EGHS` |
| FIN \| Other AC Performance % | Formula | Actual variance as a percentage, other associated costs. | `fldXNUuukboHkuewg` |

> Most of these fields share a copy-pasted description in the base ("Forecasted Performance $ Accommodations"). The descriptions above reflect what each field actually calculates.

## Booking progress

Counts and status formulas showing how far OPS has got with bookings. Read-only unless noted.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| # of Bookings Completed | Count | HBH records marked Booking Completed on the Quote version. | `fldEI2AwavAxf0CJb` |
| # of Bookings Needed | Count | HBH records that still need OPS to book something. | `fldKprk67vZ3hdqyD` |
| % Bookings Completed | Formula | Share of HBH records with a completed booking. | `fldNWmokeMDo6CRK2` |
| Flights \| Booked | Count | Program flights (arrival/departure plus internal) already booked. | `fldV4MxTTh4QF9ves` |
| Flights \| # of Program Flights | Count | Total program flights needing a booking. | `fldbRnrIJ1BdJdOgz` |
| Program Flights Completion Status | Formula | Overall booking status for flights. | `fldKj2WkBDzvBGOQY` |
| Transportation \| Booked | Count | Ground transport items booked. | `fldK7evLe8IpDI5Zj` |
| Transportation \| # of Bookings | Count | Ground transport items needing a booking. | `fldi0NMetrPYKPkzC` |
| Transportation Completion Status | Formula | Overall booking status for transportation. | `fld4ixspY34MXqzHa` |
| Meals \| Booked | Count | Meals booked. | `flddaLePMHOB12KG2` |
| Meals \| # of Bookings | Count | Meals needing a booking. | `fldc3C26RODYTiSS0` |
| Meals Completion Status | Formula | Overall booking status for meals. | `fld2C7Sbf21mfiCei` |
| Accommodations \| Booked | Count | Accommodation items booked. | `fld7E82xEehJpVA60` |
| Accommodations \| # of Bookings | Count | Accommodation bookings needed on the Quote version. | `fld77KmA7mSiy6PMM` |
| Accommodations Completion Status | Formula | Overall booking status for accommodation. *(Base note flags the conditions need revising.)* | `fldaKMGYN1EFn899U` |
| Other \| Booked | Count | Other items booked. | `fldSwXbnxds7SbxXD` |
| Other \| # of Bookings | Count | Other items needing a booking. | `fldfb8sxumrx4SNff` |
| Other Completion Status | Formula | Overall booking status for other items. | `fldee9fAdI1lEcfqQ` |
| Arrival/Departure Flights Status | Single select | Manual status for the school's international flights. | `fldzoPaCTKOdnxUCa` |
| In-Country Flights Status | Single select | Manual status for in-country flights. | `fldiywvxT5eo3hcHf` |

## Payment and refund deadlines

Enter the number of days in the "Days Prior" field; the matching date is calculated back from the program start date.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Days Prior for 100% Refund Rate | Number | Days before start when a 100% refund still applies. | `fldT32dNKCNO3YwY8` |
| 100% Refund Rate Date | Formula | The resulting 100% refund cut-off date. | `fld4FeYPqQr5TvRCm` |
| Days Prior for 50% Refund Rate | Number | Days before start when a 50% refund still applies. | `fldsZin6uXaZcaZYy` |
| 50% Refund Rate Date | Formula | The resulting 50% refund cut-off date. | `flduewrlwMKaXcaFY` |
| Days Prior for Deposits | Number | Days before start the deposit is due. | `fldT5keAdNG0RavMi` |
| Date For Deposit | Formula | The resulting deposit due date. | `fldcLpmQG3kUZ8G5J` |
| Days Prior for Balance Payment | Number | Days before start the balance is due. | `fld5ejbDTMbN2sQDB` |
| Balance Payment Date | Formula | The resulting balance due date. | `fld11Xs0NmgkIKa7t` |
| Days Prior for Confirmed Flights | Number | Days before start flights must be confirmed. | `fldkICKMkNHQaGnTr` |
| Confirmed Flights Date | Formula | The resulting flight confirmation deadline. | `fldMrGhPAylzgoB77` |
| Days Prior for Registration Deadline | Number | Days before start registration closes. | `flddvqazTyyQNK6wK` |
| Registration Deadline Date | Formula | The resulting registration deadline. | `fldkUHQJUMcK7zGvN` |

## Program content, staffing and automation flags

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Program Themes | Long text (rich) | Themes the program explores. Free text. | `fldaLBe2XvU3NY050` |
| Program Lenses of Inquiry | Long text (rich) | Lenses of inquiry framing the program. Free text. | `fld85Wr38YKCob6On` |
| Staffing Requirements | Long text (rich) | Staffing requirements requested by OPS or EM. | `fldQ8EOiUUFYRpeCC` |
| Staffing Rooming | Single select | Staff rooming setup decided by S&R. | `fldtfSHUxgpa77OdQ` |
| Staffing Rooming Notes | Single line text | Extra notes on the rooming setup. | `fldq0SjNfBQGLUUu6` |
| Debrief General Program Notes | Long text (rich) | Notes captured at the post-program debrief. | `fldbtCw51KJt4hJhw` |
| Executed version created? | Checkbox | Triggers the automation that creates the Executed version. **Do not delete.** | `flds9Kj9tSWxKd6mr` |
| Pre-ops costs executed version created? | Checkbox | Marks that Executed-version pre-ops costs have been generated. | `fldHJ7mbAKJ5O2hEN` |

---

# 4. Program Pricing Tiers

`tbl6x64qvGqKZXop2` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tbl6x64qvGqKZXop2)

Confirmed price tiers for a live program — the equivalent of I&B Pricing Tier, once the program exists.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Program Pricing Tier | Formula | Tier name: cleaned-up program name plus the student, faculty and field staff numbers. | `fldT4dzI6oj5NsqOx` |
| Program | Link → Programs | The program this tier belongs to. | `fldq0qs0yco1gt95v` |
| Program Name | Lookup | Program name from the linked record. | `fldkRjQ9MCvlSpak1` |
| I&B Price Tier Finance Linked to Program | Lookup | The original I&B tiers, shown as a reference when setting these. Confirm the PT/EL Lead hasn't changed them. | `fldSuv9PlZTewHVEx` |
| Tier Min Number Students | Number | Lowest student count this tier applies to. | `fldZJKsEvAYZBCTn9` |
| Tier Max Number Students | Number | Highest student count this tier applies to. | `fldMzSh4FqALbHe9m` |
| Tier Number of Faculty | Number | Faculty assumed in this tier. | `fldV6IOqjt5DRjBmb` |
| Tier Number of Field Staff | Number | Field staff assumed in this tier. | `fldK2ZHnHHHrsoYcJ` |
| Tier Land Price USD | Currency | Land price per student at this tier. | `fldUn34EMX2oESsZJ` |
| Tier Flight Price USD | Currency | Flight price per student at this tier. | `fldS3xlIcbVPlicus` |
| Tier Total Price | Formula | Land price plus flight price. | `fldx8eh2WO2eExoub` |
| Price Tier Notes | Long text (rich) | Notes on this tier. | `fldx7ovGgokMdZ6qQ` |
| Number of Students \| SOT | Lookup | Current SOT student count on the program. | `fldkIz7mhwze8Uaf2` |
| Active Price Range | Formula | Flags whether the current student count falls inside this tier. | `fldxYXemYBI8N16GK` |
| School's Local Currency | Lookup | The school's currency, for quoting. | `fldUG78PcyG72a7KS` |

---

# 5. Reconciliation Accounts

`tble9kx6Vx71TfLto` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tble9kx6Vx71TfLto)

The chart of accounts. Used to categorise allocations and vendor payments for finance reporting.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Chart of Accounts Reference | Long text | The account name as it appears in the chart of accounts. | `fldTcVUeHGJRgikRF` |
| COA Code | Long text | Account code. | `fldHMaI4xCvoVhu7n` |
| COA Group | Single select | Top-level grouping for the account. | `fldB5LVyBhByMGq0Z` |
| COA Sub-Group | Single select | Sub-grouping within the COA group. | `fld3KjtqK78UCcIj6` |
| Airtable Finance Reference | Long text | How this account is referred to inside Airtable finance views. | `fldmmuqKYyak8cTB3` |
| Airtaible Reconciliation Visibility | Single select | Controls where this account shows up during reconciliation. *(Field name is misspelled in the base.)* | `fldovpJ5TuZLP8Iu0` |
| COA Description | Long text | What this account covers. | `fldCso8YcYNteNO8E` |
| Allocations | Link → Allocations | Expense allocations tagged to this account. | `fldi8ljcsTwpRxdmS` |
| Vendor Payments | Link → Vendor Payments | Vendor payments classified against this account. | `fldjzJTgVOYAv4MtA` |
| Income | Single line text | Leftover from the deleted Income table. Safe to ignore. | `fld2PiYOwQFwDPMJ2` |
| Visible For HQ Office Expenses | Checkbox | Show this account when categorising HQ office expenses. | `fldzLazdIjqT9C6Iz` |
| Visible For Program Related Expense | Checkbox | Show this account when categorising program expenses. | `fldswcAJJm7paAnno` |

---

# 6. Invoices

`tbljwk03ELmACzM6f` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tbljwk03ELmACzM6f)

Invoices issued to schools. Previously called "School Invoices". Now also covers payments handled directly by parents.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Income Record ID | Formula | Program name and invoice number, separated by a bar. | `fldlPIiRkXtTvvsfk` |
| Program | Link → Programs | The program being invoiced. | `fldGuc5inLNV0s0v9` |
| School | Lookup | School name, from the linked program. | `fldiGeikA6k6nkwDn` |
| Date | Date | Invoice date. | `fldLCX35PE9ulV9VQ` |
| Invoice Number | Single line text | Your invoice reference. | `fldevSXTdM4kgFuyp` |
| Invoiced Amount | Currency | Amount invoiced. | `fldkI9DaWcYC44Kzw` |
| Invoice Uploaded | Attachment | The invoice document itself. | `fld5r6Iw8KKBd3pXj` |
| Categories | Single select | Flights or ground. Determines which income rollup on the program this feeds. | `fldJbvEXjQn8qfffe` |
| Proof Of Payment | Attachment | Receipt or transfer confirmation. | `fldobVTwyRsoA6eav` |
| Invoice Destination Email | Single line text | Where the invoice was sent. | `fldvYxxVzQ84JyRAu` |
| Invoice Sent | Checkbox | Tick once the invoice has gone out. | `fldvShy8jc3uml3k5` |
| Invoice Payment Status | Single select | Sent & Pending, Complete, etc. Drives the paid/unpaid rollups on Programs. | `fldGBE0H9tz65pmET` |
| Invoice Payment Status Last Updated | Last modified | When the record last changed. | `fld1xcy1uLvw818II` |
| Payment Category | Single select | Whether the school handles payment or individual parents do. | `fldDC2baDMRXRnKCu` |

---

# 7. Statements

`tbl1OCGK3Lx1PRkSG` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tbl1OCGK3Lx1PRkSG)

Bank and card statement uploads. Start of the finance chain: Statements → Expenses → Allocations → Programs.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Generated identifier for the statement. | `fldRS3sSsNaMp1l0O` |
| Type | Single select | Which account or card the statement is for. | `fldpopv4dUjM7W5QF` |
| Period | Single select | The month the statement covers. | `fldzpxFSCA7y8tMDV` |
| CSV | Attachment | The statement file. Uploading it creates the Expense records automatically. | `fldJgPMclM4LG2C4n` |
| Created | Created time | When the statement was uploaded. | `fldwjLW1zeaLNmk5o` |
| Autonumber | Autonumber | Internal sequential number. | `fldid12EadQbUTLsU` |
| Expenses | Link → Expenses | The expense lines parsed out of this statement. | `fldKShYVbnXoXCx8v` |
| Field Staff Profiles | Link → Field Staff Profiles | The staff member responsible for reconciling this statement. | `fldyjIK8Df35Epwxf` |
| Email (from Field Staff Profiles) | Lookup | That person's email address. | `fldh46ONezOo17jIh` |
| Reconciler Name | Lookup | That person's name. | `fldekFGeyqYMJ9fTu` |
| Reconciler Type | Lookup | What kind of staff member they are. | `fldCVqEnGA3uS2bJm` |
| Reconciliation Visibility | Formula | Controls who sees this statement during reconciliation. | `fldjDVZbtKeFvZaWP` |
| # of Pending+Partial | Rollup | How many expense lines are still unreconciled or only partly done. | `fld1ifsfoKdAFMiRx` |
| Status | Formula | Overall reconciliation status for the statement. | `fld0PwpEWNnJc7j72` |
| Record Id | Formula | Airtable record ID, used to build links into the Softr portal. | `fldoglTrEPJWQ9ui3` |
| Allocations | Link → Allocations | Allocations made against this statement. | `fldyiUSgAG8qEuCt0` |
| CC Last 4 Digits | Single line text | Last four digits of the card, where relevant. | `fldx5iiVgnVwQrzOR` |
| Income | Single line text | Leftover from the deleted Income table. Safe to ignore. | `fldJXa1LswEU3M0LT` |

---

# 8. Expenses

`tblYSe7VSGePSfD7s` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblYSe7VSGePSfD7s)

Individual transactions parsed from statements. Each one gets reconciled by splitting it into Allocations.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Generated identifier for the expense line. | `fldkmVFcZ7CsP75IA` |
| Description | Long text | Transaction description from the statement. | `fldb21J2ZHIwHjzxl` |
| Date | Date | Transaction date. | `fldDlhRvpKy4CHeS6` |
| Post Date | Date | Date the transaction posted to the account. | `fldWAoE92UZXLIySf` |
| Amount (USD) | Currency | Amount in US dollars. | `fldzhAL8hECADZ1zD` |
| Amount (Local Currency) | Number | Amount in the currency it was charged in. | `fldLB7X2xGGJXcRfI` |
| Exchange Rate | Formula | Cost of 1 USD in local currency — local amount ÷ USD amount. | `fldmfYfG8HqwfDa3j` |
| Local Currency | Link → Currencies | The currency the transaction was made in. | `fldTtwvfqQODoFH1g` |
| Balance | Currency | Account balance after the transaction. | `fldojONAPoXJviCXn` |
| Category | Single line text | Category as it came from the statement file. | `fldUDNB5Qh4odIVJh` |
| Type | Single line text | Transaction type from the statement file. | `fldOtDlQkSD9nfDNl` |
| Cardholder | Single line text | Name on the card. | `fldJgfyOn9W3Jy2iJ` |
| Card Last4 | Single line text | Last four digits of the card used. | `fldCaro9YVWsRBJJn` |
| Reference Number | Single line text | Bank reference for the transaction. | `fldvJJbPlsur1xWLV` |
| Memo | Long text | Memo line from the statement. | `fldQo2UiWCqaZHFLc` |
| Source CSV | Single select | Which uploaded file this line came from. | `fld54mvSOpOjq0Kaa` |
| Statement Link | Link → Statements | The statement this line belongs to. | `fld4Oc1orR6A9ELLy` |
| Statement Period | Lookup | Period of the linked statement. | `fldssZCiXPcskDgP8` |
| Field Staff Profiles from Statement | Lookup | Reconciler inherited from the statement. | `fldmmP3x5KMgQyhPL` |
| Record Id (from Statement Link) | Lookup | Record ID of the linked statement. | `fldXPTILDR0PrXotG` |
| Back to Statements | Formula | Clickable link back to the statement in the Softr portal. | `fld64k7XRLkln08G0` |
| Reconciler Name | Lookup | Who is responsible for reconciling this line. | `fldsUki3nFJ9fz9ld` |
| Field Staff Profiles | Link → Field Staff Profiles | Staff member the expense is attributed to. | `fldJEompkRYgDuGJN` |
| Email (from Field Staff Profiles) | Lookup | That person's email. | `fldtHG5FK1Zx2t5WX` |
| Staff Type | Lookup | That person's staff type. | `fldiR3y6CczVvsNeS` |
| Status | Single select | Reconciliation status of this expense. | `fldH4JVCC9rYVWWz9` |
| Allocations | Link → Allocations | How this expense has been split across programs and accounts. | `fldz4ew2CUez44kO4` |
| Allocated Amount Rollup | Rollup | Total already allocated. | `fldzIKmdrXiJvtLbo` |
| Amount Pending Reconciliation | Formula | Local amount minus what's been allocated — what's still outstanding. | `flduIeN23iCXEqg5v` |
| transferred_check | Formula | Internal check flag for transfers. | `fldlOovYNC9Ut9uyu` |
| Expense Reconciliation Type | Single select | How this expense should be reconciled. | `fldARBLX4knvuyYOz` |
| Revised by Finance | Checkbox | Finance has reviewed this line. | `fldDjpVSbpF9FJ0em` |
| Program Placehodler | Link → Programs | Program the expense relates to. *(Field name is misspelled in the base.)* | `fldZ5X4yal05KhEKl` |
| Direction | Single select | Whether money went out or came in. | `fldw2EbD4FY9keGte` |

---

# 9. Allocations

`tblggMoh3XJ2gLxiJ` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblggMoh3XJ2gLxiJ)

Where reconciliation actually happens: each record charges part of an expense to a program and an account.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Allocation ID | Formula | Generated identifier for the allocation. | `fld00Bst2K8vdR86E` |
| Allocated Amount | Currency | How much of the expense this allocation covers. | `fldzahvF10AkIhkhS` |
| Expenses | Link → Expenses | The expense being allocated. | `fldIOQt07ubgAa0fh` |
| Program Linked | Link → Programs | The program being charged. | `fldAK6v3CZ03Rq5aL` |
| Category | Link → Reconciliation Accounts | The chart-of-accounts line being charged. | `fldcdc3MA6hKz1JnI` |
| Airtable Finance Reference (from Category) | Lookup | Finance reference for the selected account. | `fldJIpLFovxXQ9QwY` |
| Statements | Link → Statements | The statement the expense came from. | `fldO1M5ABOO2mzexF` |
| Status | Formula | Whether this allocation is complete. | `fldXclMPIVqlW8Glh` |
| Description (from Expenses) | Lookup | Description of the underlying expense. | `fld3GYYlfBRldeaAj` |
| Amount Pending Reconciliation (from Expenses) | Lookup | What's still unallocated on the underlying expense. | `fldg6MJ1Ibfgcvf5G` |
| Field Staff Profiles (from Expenses) | Lookup | Staff member the expense belongs to. | `fld5MkH1oQ9nVTP0Q` |
| Email (from Field Staff Profiles) (from Expenses) | Lookup | That person's email. | `fldaRWRZiCTioomXq` |
| Reconciliation Visibility (from Statements) | Lookup | Visibility setting from the statement. | `fldfRE8Pn1eI8dmH1` |
| text Reconciliation Visibility (from Statements) | Formula | The same value as plain text, for filtering. | `fldJm8mrTwqyyexmT` |
| Receipt | Attachment | Receipt backing this allocation. | `fldCKpJKfe8Wd3fxI` |
| I don't have a receipt. | Checkbox | Tick if no receipt exists — explain in Observations. | `fldfbb1imO31qS5BD` |
| Observations | Long text (rich) | Notes about the allocation, including missing receipts. | `fld31uA07SHmJ8CrH` |
| ID | Autonumber | Internal sequential number. | `fldxbPR2KXOpUlPNr` |

---

# 10. Associated Costs

`tblzAFVX2QJM0opqv` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblzAFVX2QJM0opqv)

Costs that sit outside the day-by-day itinerary — preparation days, essentials, staffing and other. Snapshotted per Program Version.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Generated identifier for the cost line. | `fldybzEk0yxvH5Fd1` |
| Type | Single select | Which cost bucket this belongs to (Preparation Days, Essentials, Staffing, Other). | `fldceWUq9UQ2Gq2KA` |
| Program | Link → Programs | The program this cost belongs to. | `fldPLwZpQoadopE0I` |
| Program Versions | Link → Program Versions | Which version (Budget / Operational / Executed) this cost counts towards. Shown as "Pre-Ops Costs" on the other side. | `fldshPWjk5jKLRt7Q` |
| Version (from Program Versions) | Lookup | The version name. | `fldKRNRsizwyicyYt` |
| Name | Single line text | What the cost is. | `fldDVoZdnJTSlXaFz` |
| Comments | Long text | Notes on the cost. | `fldKBcqwQGGCA7z1o` |
| Unit Price | Currency | Price per unit. | `fldQelftGoWlKKH2S` |
| Cost Basis | Single select | How the cost scales — per person, per day, flat, etc. | `fldEZCaaYNxWLmxwE` |
| No. Pax | Number | Number of people the cost applies to. | `fldVrW6zkKLaZ09Bo` |
| # Days | Number | Number of days the cost applies for. | `fldBOsSvysdpGvMNw` |
| Budget Cost USD | Formula | Calculated budget cost from unit price, basis, pax and days. | `fldCAdHZnGxACrxBy` |
| Closing Cost USD | Currency | Actual cost at closing. | `fldcqGFsokCI11ewH` |
| Included? | Single select | Whether this cost is included in the price to the school. | `fld9K9Ygz5TQLXnVr` |
| Number of Students (from Program) | Lookup | Student count on the program. | `fldnB2QHMGr7BzBeo` |
| Number of Faculty (from Program) | Lookup | Faculty count on the program. | `fldzewQi1oDn6qbum` |
| Number of Field Staff (from Program) | Lookup | Field staff count on the program. | `fldigNoa1Oqa34ryb` |
| Total No. of Participants (from Program) | Lookup | Total headcount on the program. | `fldR1qzP6XRrhfAU0` |
| Total No. of Participants (from Program Versions) | Lookup | Total headcount on the selected version. | `fldqQ65Bb4WkKaq0A` |
| Students (from Program Versions) | Lookup | Student count on the selected version. | `fld1vaAu4ggjRJEZs` |
| Teachers (from Program Versions) | Lookup | Faculty count on the selected version. | `fldAbgS2qtaoxXQz7` |
| Staff (from Program Versions) | Lookup | Staff count on the selected version. | `flddjcEw1hancp0CQ` |
| Manual sort | Manual sort | Drag-and-drop ordering. | `fld2ttPZXUCJB7Qm9` |
| manual_sorting_executed | Single line text | Internal helper for sort order on the Executed version. | `fld3zEj7lF2SQvdlc` |

---

# 11. Vendor Payments

`tblaoj8Gq0FKqL9N9` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblaoj8Gq0FKqL9N9)

Payment requests raised against vendors. Most banking details are pulled from the Vendors record — update them there, not here.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Payment Request ID | Formula | Requester and program, separated by a bar. | `fldIAnA6bmrpPlOZ5` |
| Payment Request Label | Single line text | Short label so people can spot the request, e.g. "Quito Hotel". | `fld7DrJGnDCVHRpE2` |
| Program | Link → Programs | The program being charged. | `fldGEtinlxbi6t5Sn` |
| Program Name | Lookup | Program name from the linked record. | `fldYOTBsNK9eHV32P` |
| Destination | Lookup | Destination of the linked program. | `fld4i3SFIhmQvpX4l` |
| Requested By | Link → ENVOYS HQ | Who raised the request. | `fldepVL52bECM3lqg` |
| Vendor | Link → Vendors | Who is being paid. | `fldWVGJ7wQfZTECSS` |
| Form of Payment | Single select | Wire Transfer, Gusto, Paypal, Check or Zelle. | `fldi8asA5OXBkL1Ld` |
| Payment Classification | Link → Reconciliation Accounts | Which chart-of-accounts line this payment sits under. | `fldaqReovsxsVkPWl` |
| Transfer Currency | Link → Currencies | Currency the money is sent in. | `fldyJNpyvMsiWGdIA` |
| Transfer Amount | Currency | Amount to send. | `fldvMA42rRe8jGPIT` |
| Confirm Transfer Amount | Number | Re-enter the amount as a check against typos. | `fld2yQPnoSBpwLvvD` |
| Transfer Amount Match Check | Formula | Shows OK if the two amounts match, a warning if they don't. | `fldhailSndLnoDE7l` |
| Amount in USD | Currency | Equivalent amount in US dollars. | `fldD1ulhVsfd2NSug` |
| Payment Request Attachments | Attachment | Invoice, quote or other supporting files. | `fld920VVq2xk2DaZo` |
| Payment Request Information | Long text (rich) | Anything else Finance should know about this payment. | `fldToGW8JydhyW1Yi` |
| Payment Date | Date | Date the payment was made or is scheduled for. | `fldg27aWOwlK6zyRF` |
| Work Days Until Payment Due | Formula | Working days between today and the payment date. | `fldueeXkPFZGNGcAl` |
| Status | Single select | Where the request sits in Finance's queue. | `fldec1Ikuzc9GUZJp` |
| Proof Of Payment | Attachment | Transfer confirmation once paid. | `fldZVnQGn9Gi7rIb5` |
| ID | Autonumber | Internal sequential number. | `fldAqrpBcn9B0Gt6z` |
| Created By | Created by | Who created the record. | `fld9VFX3YYKqnoXoa` |
| Beneficiary Name | Lookup | Who actually receives the money, from the vendor record. | `fldMZZ8esKrx4oIHo` |
| Country (Financial Details) | Lookup | Beneficiary's country, from the vendor record. | `fldRoUnqad8UvRQKn` |
| Currency (Financial Details) | Lookup | Vendor's preferred currency. | `fldtODDTehhOHe54z` |
| Address (Financial Details) | Lookup | Beneficiary's address. | `fldEppzj5enVwvQXH` |
| Account Type | Lookup | Vendor's account type. | `fldJbb6cldijLDLKp` |
| Account Number | Lookup | Vendor's account number. | `fldiwFPWXlAdBM424` |
| SWIFT/BIC Code | Lookup | Vendor's SWIFT/BIC. | `fld5srSGUvnziaDxN` |
| IBAN Number | Lookup | Vendor's IBAN. | `fldOOaU1W0Z8IxeYy` |
| Routing Number (from Vendor) | Lookup | Vendor's routing number (US accounts). | `fldCKujpVqURtnARn` |
| Payment Information Additional Notes | Lookup | Extra payment notes held on the vendor record. | `fldznp6B3Ttov2sc5` |
| Vendor Payment Information Timestamp | Lookup | When the vendor's payment details were last updated. | `fldfnSol38YtKUWX9` |
| Finance Information Update | Lookup | When Finance last touched the vendor's details. | `flduzQJf0rBBP6Z04` |
| Vendor Registered In Bank | Lookup | Whether the vendor is already set up with the bank. | `fldyXd2iD6IEyytli` |
| Vendor Registration Timestamp | Lookup | When the vendor was registered with the bank. | `fldVW9H3U9izxqkMc` |

---

# 12. Currencies

`tblmkRh6koyreHTBf` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblmkRh6koyreHTBf)

Currency reference, linked from most financial tables.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Currency | Single line text | Currency code, e.g. USD, EUR, COP. | `flddxeIfPk9OhasvZ` |
| Currency Name | Single line text | Full name of the currency. | `fldNKCbazst7lDQJ6` |
| Exchange Rate to USD | Number | Conversion rate to US dollars. Keep this current. | `fld5j01z8aAarm9IW` |
| Associated Country | Link → Countries | Country or countries using this currency. | `fldYr6466UMFLP0kS` |
| Field Staff Profiles | Link → Field Staff Profiles | Staff paid in this currency. | `fldN15nrpZK3YJsiX` |
| Schools | Link → Schools | Schools quoted in this currency. | `fldBvS4VL7RDCMp6J` |
| Vendors | Link → Vendors | Vendors paid in this currency. | `fldWQSbwn8GFFZsPb` |
| Program Field Staff Assignments | Link → Program Field Staff Assignments | Staff contracts denominated in this currency. | `fldJhF2ESD83mynro` |
| Vendor Payments | Link → Vendor Payments | Payments sent in this currency. | `fldIJ00jTaapBEcVf` |
| Expenses | Link → Expenses | Expenses charged in this currency. | `fld8cv3is6TVyICjZ` |

---

# 13. Program Versions

`tblN0T3xogc2JVCiJ` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblN0T3xogc2JVCiJ)

Budget, Operational and Executed snapshots of a program. Every cost record points at one of these so the rollups land in the right column.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Generated identifier for the version. | `fldrjnh3H3CJ8ZZZp` |
| Programs | Link → Programs | The program this version belongs to. | `fld4mklXQLUw7CT6o` |
| Version | Single select | Budget, Operational or Executed. | `fldarii6tSq5m1WO7` |
| Students | Number | Student count used for calculations in this version. | `fldkeNRhxx4UbSl1V` |
| Faculty | Number | Faculty count used for calculations in this version. | `fldf1OI2mSXzpzKrL` |
| Staff | Number | Staff count used for calculations in this version. | `fldyxtoMGCZlbPBHU` |
| Total No. of Participants | Formula | Total headcount for this version. | `fldxRpR6PfMA8SNxP` |
| HBH Blocks | Link → HBH Blocks | Itinerary line items priced against this version. | `fld8SsdDSvq3tzEY7` |
| Pre-Ops Costs | Link → Associated Costs | Associated costs counted in this version. | `fldITBKItq1I5pPBx` |
| Allocations | Single line text | Leftover stub, not a working link. Safe to ignore. | `fld49YJDkcTkPcRkr` |

---

# 14. HBH Days

`tblJOmZlbOdmY9Wxk` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblJOmZlbOdmY9Wxk)

One record per day of the itinerary. Parent of HBH Blocks. Shown on Programs as "Itinerary Days".

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Day number, date (e.g. Tue Jan 3) and program name combined. | `fldY8wE0Yl9nUwbYU` |
| Day # | Formula | Display version of the day number. | `fld6EMV7edFUYYpQI` |
| Day Number | Number | The day's position in the itinerary. | `fldc68lhqNHJqRHfg` |
| Date | Date | Calendar date of this day. | `fldaIIGfT1X5jUziK` |
| Date Formula | Formula | Date derived from the program start date and day number. | `fldxsEjtP5XcNKJwN` |
| Program | Link → Programs | The program this day belongs to. | `fldz1aRYmlyGKtcro` |
| Program Name (from Program) | Lookup | Program name. | `fldtcyvdZAtW4x58K` |
| Start Date (from Program) | Lookup | The program's start date. | `fldF7Z60I2UwYnKrQ` |
| HBH Blocks | Link → HBH Blocks | The itinerary items scheduled on this day. | `fldBRPGihj3S89EV5` |
| # of Activities | Count | How many items are scheduled on this day. | `fld0VdKdGaV0OB3VJ` |

---

# 15. HBH Blocks

`tblvPtVueeYxN7me7` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblvPtVueeYxN7me7)

The Hour-By-Hour: one record per itinerary line item, carrying its timing, vendor, booking status and cost. This is where day-to-day operations and program costing meet.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Generated identifier for the itinerary item. | `fldOhvs0jasj2KgrA` |
| Name | Single line text | What the item is. | `fld5DaZBmA4lH3nje` |
| Booking Name | Formula | Display name used on booking views. | `fldEnZKtNt78v8xk6` |
| Itinerary Day | Link → HBH Days | The day this item sits on. | `fldUOOoVYBexX6XHj` |
| Day # | Lookup | Day number, from the linked day. | `fldrhg8fWPX1ympB6` |
| Date | Lookup | Calendar date, from the linked day. | `fld8mWJLDlkyhybKu` |
| Start Time | Single line text | When the item starts. | `fldLTfeCjgtIDobjM` |
| End Time | Single line text | When the item ends. | `fldna6lO0xJhDouOo` |
| Categories | Link → HBH Categories | Accommodation, Meals, Transportation, Activities, Internal Flights or Other. | `fldapdOoIAEcy3jGA` |
| Location | Link → Locations | Where the item takes place. | `fldvWQon1kff3Igkl` |
| Destination | Lookup | Destination of that location. | `fldvWOfoK80fbgntj` |
| Vendor | Link → Vendors | Supplier delivering this item. | `fldqIyBNA2nwAck4T` |
| Programs | Link → Programs | The program this item belongs to. | `fldx7e0qkUYpI30KS` |
| Program | Lookup | Program name, via the itinerary day. | `fldq3f3jtGD79vgSJ` |
| Version (Link) | Link → Program Versions | Sets whether this item counts as Budget, Quote or Executed. **Do not touch.** | `fld6eu5MPmwBOT5Sh` |
| Version | Lookup | The version name. | `fld9pqlUePnqRlJaL` |
| Booking Status | Single select | Where the booking has got to. | `flddjrWgN34mkAXTW` |
| Booking Priority | Single select | How urgent this booking is. | `fldnPw87rL2EOyK9L` |
| Payment Status | Single select | Where payment for this item has got to. | `fldyUvbsiLShW6Tq0` |
| Cost Basis | Single select | How the cost scales — per person, per day, flat, etc. | `fldY1VF7GYBDY64fl` |
| Unit Cost USD | Currency | Cost per unit in US dollars. | `fldi01mUNDoSTmeNu` |
| Total Forecast Cost USD | Formula | Estimated total, calculated from unit cost, basis and headcount. | `fld0o4gLhX2CaQ3ky` |
| Quoted Total Cost | Currency | The actual total quoted or paid. | `fldxBDuS2qqCS74pe` |
| Estimate / Quote Difference | Formula | Gap between the forecast and the quoted cost. | `fldxHsk6CTBYkEqyy` |
| Local Amount | Currency | Cost in the local currency. | `fldHW6q7bXzh3kZaX` |
| Fx Rate Used | Currency | Exchange rate applied to that local amount. | `fldZCguwHPq8r41MI` |
| Local Amount USD | Currency | The local amount converted to US dollars. | `fldyI4Kal0XGA8O8s` |
| Confirmed Payment Date | Date | When payment was confirmed. | `fldXd3CcEFqbXNsIr` |
| AdvancePaidFlag | Formula | Internal flag showing whether an advance has been paid. | `fld9zh5FWP7SCUseS` |
| BookingFlag | Formula | Internal flag used by booking-progress counts on Programs. | `fldHgVMVqB38eCgiV` |
| Supporting Link | URL | Booking confirmation, quote or reference link. | `fldUqK95YSbsFzSzX` |
| Total No. of Participants (Versions) | Lookup | Headcount from the linked version, used in cost formulas. **Do not touch.** | `fldIwXg4HFgGWYXST` |
| Students (Versions) | Lookup | Student count from the linked version. | `fld0B9abKywWoEYPx` |
| Faculty (Versions) | Lookup | Faculty count from the linked version. **Do not touch.** | `fldPrU5q7vBC5oZtX` |
| Staff (Versions) | Lookup | Staff count from the linked version. **Do not touch.** | `fldY73iqKTDNNTMtA` |
| Visible To School | Checkbox | Tick to show this item to the school. | `fldiihwwMddbmShbd` |
| Visible For Staff | Checkbox | Tick to show this item to field staff. | `fldqww6zVJwV8zY3u` |
| Notes | Long text | Internal notes on the item. | `fldnU8DHj1WZvdd8a` |
| Notes for School | Long text (rich) | Notes written for the school to read. | `fldrCVxt5Hb8KqIar` |
| Program Debrief Required | Checkbox | Tick if this item needs reviewing at the debrief meeting. | `fldQjYH57zAT1Tzvt` |
| Debrief Rating | Single select | Highlight (include every time) / Recommended / Acceptable / Caution (don't repeat). | `fldz3sysLrUVGtngg` |
| Program Debrief \| Notes | Long text | Debrief notes for this item. | `fldaA2RUrTV6gVHaG` |
| autonumber | Autonumber | Internal sequential number. | `fldCEnCDhEV32HPhH` |
| manual_sorting | Number | Internal sort order. | `fldHYHTFsk75PR7v5` |
| Manual sort (Quote) | Manual sort | Drag-and-drop ordering on the Quote version. | `fld8YxQ3K8XIsbCz5` |
| sequence_order | Number | Internal ordering helper. | `fldL10swMIj4blBC3` |

---

# 16. HBH Categories

`tbldUztqyoepRaoKx` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tbldUztqyoepRaoKx)

The category list behind HBH Blocks, also used to categorise vendors.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Name | Single line text | Category name — Accommodations, Meals, Transportation, Activities, Internal Flights, Other. | `fldfkANp6ORXTAh9t` |
| HBH Blocks | Link → HBH Blocks | Itinerary items in this category. | `fldziR5Tnz9TOU50T` |
| Vendors | Link → Vendors | Vendors that supply this category. | `fldvVkoYcPx7G4Ck6` |
| Record ID | Formula | Airtable record ID. | `fldtGi5QLpRDE2TLp` |
| Vendor Listings | Single line text | Leftover stub, not a working link. Safe to ignore. | `fldMY7mjLmtOyxIEr` |

---

# 17. Destinations

`tblJP7qwM5lswBRUa` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblJP7qwM5lswBRUa)

The destination knowledge base — everything the team should know before running a program somewhere.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Formula | Generated identifier for the destination. | `fld9LIDOFfmFUO30a` |
| Destination Name | Single line text | Name of the destination — a country, city or region. | `fldQXJ6GcCEKyUfyv` |
| Country | Link → Countries | Country the destination sits in. | `fldkCxhIHSrgYGnQo` |
| Country Code | Lookup | Phone country code, from the linked country. | `fldjnp3fnliYY77Kh` |
| Locations | Link → Locations | Specific sites and venues within this destination. | `fld54KMdUJCwIf9Vg` |
| Vendors | Link → Vendors | Vendors operating here. | `fld5ApFyA1TKpk15D` |
| Programs | Link → Programs | Programs that have run or will run here. | `fldHF0kXGGokiSrpL` |
| I&B Requests | Link → I&B Requests | Requests asking for this destination. | `fld3fJ5JE2kUkCggm` |
| Field Staff \| Country Coordinator | Link → Field Staff Profiles | The country coordinator for this destination. | `fldjQTxWSe4VkJRYg` |
| Field Staff with Experience | Link → Field Staff Profiles | Staff who have worked here before. | `fldZmkko9MD2kcFlC` |
| Overall Summary | Long text (rich) | General overview of the destination. | `fldbtm9BEzkePYADk` |
| Travel & Logistics | Long text (rich) | Visas, arrival, departure and permits. | `fldkusEqBwTFZq5nc` |
| Weather Seasons | Long text (rich) | Year-round weather conditions and patterns. | `fld7HFOFl0N9E74OR` |
| Peak / High Seasons to Avoid | Long text (rich) | Times of year to steer clear of. | `fldxB9b0fSKKy820F` |
| Safety Considerations | Long text (rich) | Safety notes for this destination. | `fldnHhiyPIKcfhk09` |
| Cultural Considerations | Long text (rich) | Cultural notes and sensitivities. | `fldI3fzyywHdLUCez` |
| Other Notes | Long text | Anything else worth recording. | `fldeUjkZ8cHXBLq07` |
| Destination Attachments | Attachment | Supporting documents, maps and photos. | `fld9zAva1bKdBFWxT` |

---

# 18. Countries

`tblRLokIjJBvwKzUf` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblRLokIjJBvwKzUf)

Country reference. Also doubles as the phone country-code list, which is why several near-identical "Field Staff Profiles" links exist — each one is the reverse of a different link on the staff record.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Counties | Formula | Display name for the country. *(Field name is misspelled in the base.)* | `fldF1qFhC6r6xli1z` |
| Name | Single line text | Country name. | `fldzsSGoldqC2DMOQ` |
| Region | Single line text | Region the country belongs to. | `fldqMBK3p4VK3VE76` |
| Country Code | Single line text | International dialling code. | `fldk59hS8t6NvqGgK` |
| Destinations | Link → Destinations | Destinations in this country. | `fldHQPJRJY8W8w2Cc` |
| Schools | Link → Schools | Schools based in this country. | `fldsO000MCpJcIhLV` |
| Currencies | Link → Currencies | Currencies used here. | `fldfCioJ9mxIQhhyT` |
| Vendors | Link → Vendors | Vendors whose banking country this is. | `flds7bs1TS4XnEP73` |
| Field Staff Profiles 3 | Link → Field Staff Profiles | Staff who live in this country. | `fld6B6WNmRyowvw9M` |
| Field Staff Profiles 4 | Link → Field Staff Profiles | Staff whose phone number uses this dialling code. | `fldbESjFJrjbthBrY` |
| Field Staff Profiles 5 | Link → Field Staff Profiles | Staff whose emergency contact uses this dialling code. | `fldmf5PNfFKa01hec` |
| ENVOYS HQ | Link → ENVOYS HQ | HQ staff whose phone number uses this dialling code. | `fldVwy6wJNb0Bm7xE` |
| School Faculty & Staff Directory | Link → School Faculty & Staff Directory | School contacts using this dialling code. | `fldmbHcINmMBhWCQd` |
| Field Staff Profiles | Single line text | Leftover stub, not a working link. Safe to ignore. | `fldsNyflQGWqv1uY1` |
| Field Staff Profiles 2 | Single line text | Leftover stub, not a working link. Safe to ignore. | `fldCouyI3kcoOYnNu` |
| School Participant Profiles | Single line text | Leftover stub, not a working link. Safe to ignore. | `fldIGpxaznf3LVJaz` |
| Scouting | Single line text | Leftover from the deleted Scouting table. Safe to ignore. | `fldCAh862XIPAkQ6z` |

---

# 19. Locations

`tblwGliFqmasmwJGm` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblwGliFqmasmwJGm)

Specific places within a destination — towns, sites, venues — used when building the itinerary.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Name | Single line text | Name of the location. | `fldnQABnGr1rQUSW8` |
| Destinations | Link → Destinations | The destination this location sits inside. | `fldmZfcNMEqsXQt7O` |
| HBH Blocks | Link → HBH Blocks | Itinerary items happening here. | `fldhOvhvfBjoFDXuS` |
| Vendors | Link → Vendors | Vendors operating at this location. | `fld1wUVUSWSN7QR8r` |
| Description | Long text (rich) | What the location is and why it matters. | `fld7Z7ZBLBQ8PT7UI` |
| Program Relevance & Associated Themes | Long text (rich) | Which program themes this location supports. | `fldUTEbwrQZBvNCNx` |
| Access & Travel Time | Long text (rich) | How to get there and how long it takes. | `fldNgIiHvMbBWtqOO` |
| Seasonal Trends: Weather & Tourism | Long text | Weather and tourist volume through the year. | `fldD4dZSCjQvHef2W` |
| Activities Trends | Long text (rich) | What activities work well here. | `fldTuPgqB1QkR43v5` |
| Safety & Cultural Considerations | Long text (rich) | Safety and cultural notes specific to this location. | `fldmEaE5SSw0meIlu` |
| Additional Notes | Long text (rich) | Anything else worth recording. | `flds6Ad5QY5a6gMRI` |
| Scouting | Single line text | Leftover from the deleted Scouting table. Safe to ignore. | `fldF2BGVtYmP9PAfx` |

---

# 20. Vendors

`tblLyek7Rc1Qs1Cof` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblLyek7Rc1Qs1Cof)

The vendor directory. **This is the source of truth for banking details** — Vendor Payments reads them from here, so update the vendor record rather than the payment request.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Vendor Name | Single line text | Trading name of the vendor. | `fldh0ZN5UrI4Lxj8g` |
| Id | Formula | Unique code from vendor name, destination, category and record ID. | `fldugTXn0Yt2bIPks` |
| Category | Link → HBH Categories | What the vendor supplies. | `fldJq7A0ah4PmAq9C` |
| Destinations | Link → Destinations | Destinations the vendor covers. | `fldghhEqKs8IJdXRX` |
| Location | Link → Locations | Specific location the vendor operates from. | `fldwmHZyl5EvSoukl` |
| Country | Lookup | Country, from the linked destination. | `fldllycnSkDXaHOCE` |
| Full Address | Long text (rich) | Street address: line 1, line 2, city/state, ZIP, country. | `fldsWhF1F3DDsnGJg` |
| Google Maps Location Link | URL | Google Maps link. Search the place, tap Share, then Copy link. | `fldNRQ86GBLH7rFl2` |
| Contact Name | Single line text | Main contact at the vendor. | `fldmcpGQ5jkBo0FFG` |
| Email | Email | Contact email. | `fldkAc0pp6eLjiP5D` |
| Country Code | Lookup | Dialling code for the vendor's country. | `fld5FDxJNinolGsJ3` |
| Phone Number | Phone | Contact phone. **Don't include the country code** — it comes from the field above. | `fld0B2m9OdZdpdSdv` |
| Website | URL | Vendor's website. | `fldyvQX8kytb9R3n4` |
| Vendor Status | Single select | Whether the vendor is active and approved. | `fldtcAgzJswEHxDAk` |
| Vendor Rating | Single select | How well the vendor performs. | `fldi9f7AUMtsC4aVg` |
| Price Range | Single select | Rough price bracket. | `fldetyv92y1tbvXZw` |
| Vendor Notes | Long text (rich) | General notes on working with this vendor. | `fldSj4Z4jMMhKLVwY` |
| Vendor Debrief Notes | Long text | Feedback captured after programs. | `fldpbc35GeqpoHOVW` |
| Vendor Files | Attachment | Contracts, insurance certificates, menus and similar. | `fldFYYy9eHjg32S2k` |
| Vendor Review Timestamp | Last modified | When the vendor record last changed. | `fldamgo9fFgVGTD7j` |
| HBH Link | Link → HBH Blocks | Itinerary items supplied by this vendor. | `fldLgQX7S9UjTYFWs` |
| Programs (Link) | Lookup | Programs that have used this vendor. | `fld7Xk8kGWazAoNso` |
| Vendor Listings | Link → Vendor Listings | Priced items this vendor offers. | `fld0kzZmPtJzCLda3` |
| Vendor Payments | Link → Vendor Payments | Payments made to this vendor. | `fldiUHVm4zPaOqRnk` |
| Beneficiary Name | Single line text | The person or entity that actually receives payment. | `fld5GnqtKw5gEjo2F` |
| Country (Financial Details) | Link → Countries | Country the beneficiary is located in. | `fldNL0RXS3170Dqul` |
| Currency (Financial Details) | Link → Currencies | Currency money should be transferred in. | `fldqAx9Nf1OgYYzKY` |
| Address (Financial Details) | Long text (rich) | Beneficiary address — at minimum street, city and ZIP. | `fldA5YBkK1cLOntYU` |
| Account Number | Single line text | Bank account number. | `fldLWyRxNzkWZ7sQv` |
| Account Type | Single select | Checking, savings, etc. | `fldxDiDqtE54TaYtC` |
| Routing Number | Single line text | Routing number, for US accounts. | `fldYlG05iOlxwVhZS` |
| SWIFT/BIC Code | Single line text | SWIFT or BIC code for international transfers. | `fld8BwR3xuguTa81L` |
| IBAN Number | Single line text | IBAN, where applicable. | `fld5qpaf1TIdGRPsb` |
| Payment Information Additional Notes | Long text (rich) | Extra payment details — mailing address for checks, Paypal or Gusto details if different from the above. | `fld5H7QPvasJMOaQS` |
| Finance Information Update | Last modified | When Finance last updated the payment details. | `fldhW7NGzZ7kmRlZf` |
| Timestamp \| Vendor Payment Information Update | Last modified | When the payment information last changed. | `fldpImwreNcQlFiuO` |
| Vendor Registered In Bank | Checkbox | Vendor is set up with the bank. If they haven't been used in a while, compare the two timestamps above before relying on this. | `fldiJxgWUyXHvDbkM` |
| Vendor Registration Timestamp | Last modified | When the vendor was registered with the bank. | `fldHSaehDUsQzQqe8` |
| Pre-Ops Costs | Single line text | Leftover stub, not a working link. Safe to ignore. | `fldud0ErzQySPFzcE` |
| Scouting | Single line text | Leftover from the deleted Scouting table. Safe to ignore. | `fldnUVI92HfpOGP65` |

---

# 21. Vendor Listings

`tblbcnI552v4ZgKHp` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblbcnI552v4ZgKHp)

The priced catalogue behind cost estimates — individual items each vendor offers.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Vendor Listing ID | Formula | Code built from category, vendor name, destination, location, country code and identifier. | `fld16BCeh2oH8MUY1` |
| Item Name | Single line text | What the item is. | `fldUe5OoCtCt862Hq` |
| Unit Final Cost (USD) | Currency | Final cost per unit in US dollars. | `fldjhtb3hw5SMoswx` |
| Quote Date | Last modified | When this price was last updated. | `fldp9lhLYFGtkOH8T` |
| Category | Single select | What kind of item this is. | `fldF0u2GIokeAgbDG` |
| Item Description | Long text | What's included. | `fldSWRtdk8jeuIwoU` |
| Item Notes | Long text | Caveats, minimums or conditions on the price. | `fldsDOXkuEnISF7a3` |
| Vendor | Link → Vendors | Who supplies this item. | `fldlm7s3n8ekzJH5y` |
| Vendor Name (from Vendor) | Lookup | Vendor name. | `fldl10O9nzeg4FVuh` |
| Destinations | Lookup | Destinations the vendor covers. | `fldWU3D8afjLthYFj` |
| Location | Lookup | Vendor's location. | `fldyWkgBCuMgLvYnd` |
| Country Code (from Vendor) | Lookup | Vendor's country code. | `fldcqSFjSRjjE20aS` |
| Identifier | Autonumber | Internal sequential number used in the listing ID. | `fldy7fUgJ0OGemNeq` |

---

# 22. Schools

`tblQiA1cYuiGnrOBx` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblQiA1cYuiGnrOBx)

Client schools.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| School | Formula | Unique identifier combining the autonumber and school name. | `fldCKBsXbDIAn7Sw9` |
| autonumber | Autonumber | Sequential number that makes each school unique, even if names are similar. | `fldAy1KJvlUDE8vZn` |
| School Name | Single line text | Name of the school. | `fldf9cNjpfAXbCkTn` |
| School Type | Single select | What kind of school it is. | `fld3L7uQIY2MpvKhk` |
| City | Single line text | City the school is in. | `fldH1uxg5uMsN1LBa` |
| Country | Link → Countries | Country the school is in. | `fldvZE2GO8nLQLtvE` |
| Address | Long text (rich) | Mailing address: line 1, line 2, city/state, ZIP — one per line. | `fldAJkhbjQAXVxYvk` |
| Main Contact Name | Single line text | Primary contact at the school. | `fld5VfVrJey9r3WnQ` |
| Main Contact Email | Email | Primary contact's email. | `flde6eJuTjdJRRIMq` |
| Main Contact Phone | Phone | Primary contact's phone. | `fldBBEowHkezLPiAG` |
| Current Account Lead | Link → ENVOYS HQ | The Envoys person who owns this relationship. | `fldAraY181s8RYTxu` |
| Programs | Link → Programs | Programs run for this school. | `fldZFMp9DHV7wEHFb` |
| I&B Requests | Link → I&B Requests | Itinerary and budget requests from this school. | `fldZgCpWx71u9JWrt` |
| School's Local Currency | Link → Currencies | Currency this school is quoted in. | `fld1rS9V39OoR6lvW` |
| Exchange Rate to USD | Lookup | Conversion rate for that currency. | `fldZIZYpkNLpJpxSC` |
| School People Directory | Link → School Faculty & Staff Directory | Contacts at this school. | `fldLq23ggmeSEB30V` |
| School Image Banner | Attachment | Logo or banner image for school-facing materials. | `fldbqw5leTFuPk787` |

---

# 23. School Faculty & Staff Directory

`tblqanKzz66DWh68m` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblqanKzz66DWh68m)

Contacts on the school side — faculty, administrators and trip leaders.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Full Name | Formula | First, middle and last name, with the position title after a dash if there is one. | `fldkuetykPZoiDV4R` |
| First Name | Single line text | Given name. | `fldKFZTFvtrSJefhO` |
| Middle Name | Single line text | Middle name. | `fldk72rAVOEyODPib` |
| Last Name | Single line text | Family name. | `fld16XMxIkkj9ocZi` |
| Preferred Name | Single line text | What they'd like to be called. | `fldNjvLMJtJwHLKXS` |
| Preferred Pronoun | Single line text | Their pronouns. | `fld5TuSvNVHGbmmRC` |
| Position Title | Single line text | Their role at the school. | `fldQXr5JiroXj7EhN` |
| Email | Email | Email address. | `fldxy36qhD25Vy7Qj` |
| Phone | Phone | Phone number. | `fldJfKaIfaNZkMqVj` |
| School Directory Country Code Phone | Link → Countries | Dialling code for their phone number. | `fldHWeAYXm3trKWqZ` |
| Address | Long text | Postal address. | `fldfFxA92weHPJunH` |
| Contact's School | Link → Schools | The school they work at. | `fldS8CdCiroj63b4l` |
| Primary contact for Programs | Link → Programs | Programs where they are the main school-side contact. | `fldrfRPs0B0oa94wN` |
| Notes | Long text | Notes about this contact. | `fldFWwCGqY4eX7NdF` |
| Notes Section | Long text (rich) | Longer formatted notes. | `fldBN4BppETDEx68G` |

---

# 24. School Participant Profiles

`tblTHvRz63OCD0AuZ` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblTHvRz63OCD0AuZ)

Participant registrations arriving from Jotform.

> 🔒 **Sensitive data.** This table holds passport numbers, dates of birth, home addresses, parent contact details and full medical histories. Only share what a task actually needs, and think carefully before adding these fields to any interface or export.

## Identity and registration

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Participant ID | Formula | Participant name, passport number and date of birth combined. | `fldnROd2dpWwvVs10` |
| Participant Full Name | Formula | Full name, including middle name if given. | `fldMSWdt80B1ngDnG` |
| Participant First Name | Single line text | Given name. | `fld8cemL49p7sD8qp` |
| Participant Middle Name | Single line text | Middle name. | `fldCqLA1RMld0U0IC` |
| Participant Last Name | Single line text | Family name. | `fldy3nD6jOlAAaNxQ` |
| Preferred Name | Single line text | What they'd like to be called. | `fldBDJCUXgTXe3eM7` |
| Preferred Pronoun | Single line text | Their pronouns. | `fldGcj2Shryyr2pNv` |
| Date of Birth | Date | Date of birth. | `fldfUxrnZAkImiD3K` |
| Participant Age During Program Start Date | Formula | Their age in years on the day the program starts. | `fldGeMuGfQlemB7lT` |
| Gender | Single line text | Gender as submitted on the form. | `fldGH17u1IfeoaqRC` |
| Travelers Email | Email | Participant's own email. | `fldzjItRQGWF2jcqD` |
| T-Shirt Size | Single select | Size for program merchandise. | `fldds283HuinmCWRU` |
| Participant Type | Formula | Whether they are a student or faculty, derived from the form answer. | `fldwtlLwlh9gb2xik` |
| Participant Type (From Form) | Single select | The raw participant type submitted on the form. | `fldTjjg605JHPmJoS` |
| Programs (Link to Database) | Link → Programs | The program they're registered for. | `flddqjcTU67QyZP7A` |
| Program Name | Single line text | Program name as typed on the form. | `fldrazKnUPsEbEQpr` |
| Start Date of Program | Date | Program start date as submitted. | `fldQXTSpUvNlPp4pk` |
| Start Date of Program (From Database) | Lookup | The real start date from the linked program. | `fldTTcWi4vfsWpPyp` |
| School (From Database) | Lookup | School name from the linked program. | `fldTjpKROQ6pRmpVH` |
| Submission Timestamp | Date & time | When the form was submitted. | `fldACTAscr7N4SqEK` |
| Registration Date | Formula | Registration date derived from the submission. | `fldpUAm4btVtvz0FP` |
| Created | Created time | When the record was created in Airtable. | `fldO35CuOFLp2ET2R` |
| Jotform Registration Link | URL | Link to the registration form used. | `fldKDEXlIgMSFFDNC` |
| Jotform Submission Form ID | Single line text | Jotform's own submission reference. | `fldYF7NrHSJp1TxSN` |

## Parent or guardian

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Parent First Name | Single line text | Parent's given name. | `fldMJ4XZqPLPPixeg` |
| Parent Last Name | Single line text | Parent's family name. | `fldn7ed0swdHXdUAL` |
| Parent Full Name | Formula | Parent's full name. | `fldMU7hoWhVXTJfCG` |
| Parent Email | Email | Parent's email — the main channel for registration comms. | `fld4ukth9m3x1q1hz` |
| Parent/Student Address | Long text | Home address. | `fldX61AXmv91ZnRhE` |

## Passport and travel documents

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Passport Number | Long text | Passport number. | `fldtImTf23WX0JqOi` |
| Passport Country | Single line text | Country that issued the passport. | `fldfxYAE8ilrX8HJD` |
| Passport Expiration Date | Date | When the passport expires. | `fldUyyrf34xdf0KCf` |
| Expiration Date Flags | Formula | Flags passports expiring within 180 days of the program start. | `fldVMAwtlLU1QMdUb` |
| Days Until Passport Expiration | Number | Days remaining on the passport. | `fldnWMWu1CgsI9H2M` |
| Passport Upload | Attachment | Scan or photo of the passport. | `fldE4d5EmQaJHTOLY` |

## Health and dietary — sensitive

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Physical Activity Ability | Single line text | Fitness and mobility level. | `fldNutncg4pYFupVi` |
| Swimming Ability | Single line text | Swimming competence. | `fldM4Cabm3adDQ13d` |
| Food Allergies | Single line text | Whether they have food allergies. | `fld5NciNEnUuZiK78` |
| Food Allergy Severity | Single line text | How severe those allergies are. | `fld1XSIxBjgl4yiK7` |
| Food Allergies Details | Long text | Which foods are involved. | `fldm451dTLJXyRzkR` |
| Food Allergies Symptoms | Long text | What a reaction looks like. | `fldz3Yuz8q3Drj2GD` |
| Food Allergies Treatment | Long text | How to treat a reaction. | `fldWOnOfad2QhgJTX` |
| Non-food Allergies | Single line text | Whether they have non-food allergies. | `fldN7PHP2xyZTh3kp` |
| Non-Food Allergies Severity | Single line text | How severe those allergies are. | `fldkbivc4ozpNOSaz` |
| Non-Food Allergies Symptoms | Long text | What a reaction looks like. | `fldQOf7ptUjc6WbE3` |
| Non-Food Allergies Reaction | Long text | Description of past reactions. | `fldzbFKvQqPIR6G2s` |
| Non-Food Allergies Treatment | Long text | How to treat a reaction. | `fldz6k4Yd5rZ1HytC` |
| Carries EpiPen | Single line text | Whether they carry an EpiPen. | `fldOIyg3lIiplvX15` |
| Dietary Restrictions | Single line text | Whether they have dietary restrictions. | `fld1cDy1BubsNP6Wz` |
| Dietary Restrictions Details | Long text | What those restrictions are — share with meal vendors. | `flddmiK1QGXJz6m26` |
| Current Medications | Single line text | Whether they take regular medication. | `fld5IRYOSOURVrISO` |
| Medication Information | Long text (rich) | Which medications, doses and timing. | `fldyot5FPJAfz0jAm` |
| Medications Not Taken During Program | Single line text | Whether any medication will be paused. | `fldxVQOO3n6UMkFgN` |
| Medications Not Taken During Program Explanation | Long text | Why, and what that means for the field team. | `fldNgQUFILOwYALEp` |
| Respiratory Issues | Single line text | Whether they have respiratory conditions. | `fldwRTf4q512AQaXp` |
| Details of Respiratory Issues | Long text | Detail of those conditions. | `fld7SB0chnnqv4RdB` |
| Diabetes | Single line text | Whether they are diabetic. | `fldaCs7t0PsvZhWcw` |
| Details of diabetes | Long text | Type, management and what to watch for. | `fldMqNr5rnxYywbY8` |
| Neurological Conditions | Single line text | Whether they have neurological conditions. | `fldn3YPEGHju80f0T` |
| Details of neurological conditions | Long text (rich) | Detail of those conditions. | `fldGoPoOKthGVxZLX` |
| Chronic / Recurring Medical Conditions | Single line text | Whether they have ongoing conditions. | `fldlGCQGa69WEHOtL` |
| Chronic / Recurring Medical Conditions Details | Long text | Detail of those conditions. | `fldol24h7638xgQq7` |
| Medical Devices | Single line text | Whether they use medical devices. | `fldeHIuvyT04ikYN7` |
| Medical Devices Details | Long text | Which devices and any handling notes. | `fldaTfjp2k4LuKPPL` |
| Head Injury | Single line text | History of head injury. | `fld5LILzv1vsMe4bz` |
| Head Injury Details | Long text | Detail and any ongoing effects. | `fldrTdaSWr4rxb5zt` |
| Mental Health Treatment | Single line text | Whether they are receiving mental health treatment. | `fldrHwGOVE2k2XyBu` |
| Mental Health Treatment Details | Long text | Detail relevant to supporting them in the field. | `fld0TVHnW7nxKd4eH` |
| Hospitalized / Crisis Center Admittance | Single line text | History of hospitalisation or crisis-centre admission. | `fldyx0GkCU06wJH7g` |
| Hospitalized / Crisis Center Details | Long text | Detail of those admissions. | `fldBK0DePoDKeSWOc` |
| Eating Disorders | Single line text | History of eating disorders. | `fldVObWlAbSTdIdiw` |
| Eating Disorders Details | Long text | Detail relevant to meals and supervision. | `fld9ByUfUj6euyPY9` |
| Additional Medical Information | Long text | Anything else the field team should know. | `fldwE4dRWc8WKlYSl` |
| Medical information Acknowledgment / Consent | Checkbox | Confirms the medical declaration was acknowledged. | `fld1I3cWSZaWRXqUN` |

## Emergency, consent and payment

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Emergency Contact Name | Single line text | Who to call in an emergency. | `fldyTc8QxBv1dP4nL` |
| Emergency Contact Phone | Long text | Their phone number(s). | `fldIfzDYx8QVDIknP` |
| Photo Release Permission | Single line text | Whether photos of this participant may be used. | `fld0hISEXd8xtmGE0` |
| Signature Assertion | Single line text | Confirms the forms were signed. | `fldZuwTuLYZwkbPKR` |
| Payment Status | Single select | Where this participant's payments stand. | `fldq24ZCe91TJZW86` |
| Total Paid | Currency | Total received from this participant. | `fldroRjEiicdfNsey` |
| Financial Aid Details | Long text | Financial aid arrangements. | `fldIjGaj2fYVppLMi` |
| Financial Aid Payments | Long text | Payments made under those arrangements. | `fldJFdIaXNm6A2sy1` |
| Flights \| Deviations | Single select | Whether they're travelling separately from the group. | `fld3vRvyTjGIpRMbh` |
| Flights \| Notes on Deviations | Long text | Detail of the deviation — arrival, departure or both. | `fldSxqBFkOsswnZB4` |

---

# 25. ENVOYS HQ

`tblINfoWQFO10skMw` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblINfoWQFO10skMw)

The internal staff directory. Every POD assignment on a Program points here; the fields below are the reverse view — "which programs does this person own".

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Name | Formula | Team, first, middle and last name combined. | `fldL1QYagvyBbEsAU` |
| First Name | Single line text | Given name. | `fldjsT8K8JhaO4Ae7` |
| Middle Name | Single line text | Middle name. | `fldkJOV9nykxWHSVX` |
| Last Name | Single line text | Family name. | `fldLQePhECztZWaDd` |
| Team | Single select | Which team they sit on (PT, OPS, EM, S&R, Finance…). | `fldRVQsZ6S1XyHjAK` |
| Email | Email | Work email. | `fld4CuFxoYYXn5CZy` |
| Phone Country Code | Link → Countries | Dialling code for their phone. | `fld4xy1tjbueRUuMd` |
| Phone | Phone | Phone number, without the country code. | `fld6f6FvwgkobnCj5` |
| Slack ID | Single line text | Slack member ID, used by notification automations. | `fldA4glEd0vqoUM3W` |
| Programs PT Pod | Link → Programs | Programs where they are PT Lead. | `fldQd4sWf8tjWi8Xr` |
| Programs OPS Pod | Link → Programs | Programs where they are OPS Lead. | `fldp9mlQf51TkgNXM` |
| Programs EM Pod | Link → Programs | Programs where they are EM Lead. | `fldz6nzs4wWyHLJCC` |
| Programs S&R Pod | Link → Programs | Programs where they are S&R Lead. | `fldXLaQI2DdOq2NJW` |
| POD \| HQ Lead | Link → Programs | Programs where they are the HQ emergency contact. | `fldISgsjZTkunTz46` |
| POD\| HQ Blackout Lead | Link → Programs | Programs where they cover blackout periods. | `fldK97OGhA7kM05n4` |
| I&B Requests Owner | Link → I&B Requests | Requests where they are OPS Lead. | `fld8GkFwH8EnO5eZE` |
| I&B Requests PT Lead | Link → I&B Requests | Requests where they are PT Lead. | `fld6SU6S61SD7eenB` |
| Vendor Payments | Link → Vendor Payments | Payment requests they raised. | `fldOY4vKQ3IquLmpM` |
| Schools | Link → Schools | Schools where they are the account lead. | `fldmrGVM4tzt3i3HO` |
| Statements | Single line text | Leftover stub, not a working link. Safe to ignore. | `fld7JV7oAqRLtPRZa` |

---

# 26. Field Staff Profiles

`tblexpAj1gv5PTPYq` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblexpAj1gv5PTPYq)

Field staff records — certifications and their expiry tracking, rates, equipment, and the Softr portal login fields.

## Identity and contact

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Staff ID | Formula | Generated unique identifier for the staff member. | `fldK2JekYPAEsN0PQ` |
| Full Name | Formula | First, middle and last name combined. | `fld4emWtSTjCuxIVB` |
| First Name | Single line text | Given name. | `fldF0qJblMnSaFIhc` |
| Middle Name | Single line text | Middle name. | `fldu9cPlBE0LSswfs` |
| Last Name | Single line text | Family name. | `fldqiGWCDwviw1MWC` |
| Preferred Name | Single line text | What they'd like to be called. | `fld7Pziszmh1yRYfW` |
| Sex (match travel document) | Single select | Must match the travel document, for flight bookings. | `fld8D8faRlxunxBV8` |
| Date of Birth | Date | Date of birth. | `fld41MuUOczg17odW` |
| Email | Single line text | Email address. | `fldvEtx9ZgnvG8owA` |
| Phone Country Code | Link → Countries | Dialling code for their phone. | `fldEsVg5URyMk06VT` |
| Phone Number | Phone | Phone number, without the country code. | `fldunMzNsdmeLtECX` |
| Location | Single line text | Where they're based, as free text. | `fldLrMplUZZbOURZK` |
| Residence Address | Long text (rich) | Full address: line 1, line 2, neighbourhood/city, ZIP, country. | `fldDpOzvvSnfjlhrm` |
| Country of Residence | Link → Countries | Country they live in. | `flduY5lw41Xwz2UOG` |
| Profile Description | Long text | Short bio used when introducing them to schools. | `fldg8L1wdDfu1Y2Rt` |
| Field Staff Photo | Attachment | Profile photo. | `fldPc2niiCKp8QwUE` |
| CV | Attachment | Their CV. | `fldqVU9P2dBFKywV7` |

## Role and expertise

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Staff Type | Single select | What kind of field staff they are. | `fldWYqCOB7BvaMReI` |
| Staff Tier | Single select | Seniority tier, which drives their rate. | `fldKzjxgIuSNhDz9Z` |
| Country Coordinator Status | Single select | Whether they act as a country coordinator. | `fld9YoX3V5pChgFnp` |
| CC Destinations | Link → Destinations | Destinations they coordinate. | `fldt6F3SqULUS1hvu` |
| Experience in Destinations | Link → Destinations | Destinations they've worked in before. | `fld62ejCZOpRNEpCV` |
| Languages | Multiple select | Languages they speak. | `fldnWJ0MH8KU24BHu` |
| Theme Preference | Long text | Program themes they prefer to work on. | `fldnzFBTK6JBnVUKI` |
| Able to drive? | Single select | Whether they can drive on programs. | `fldPrnjuBcCVMn9Y2` |
| Swimming Ability | Single select | Swimming competence. | `fld9wUPZr1ryzHmCh` |
| Allergies & Dietary Restrictions | Long text (rich) | Their own allergies and dietary needs. | `fldjRibmiIrqQ1n8U` |
| T-Shirt Size | Single select | Size for kit and merchandise. | `fldcoBfiau1RBpENU` |
| Staff Availability Observation | Long text | Notes on when they're available. | `fldTjySpVTE15ERa6` |

## Documents and certifications

Each document has an upload, an expiry date and a status formula that flags missing, expired, valid, or expiring within 183 days.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Passport | Attachment | Passport scan. | `fldQrzBLliG9Eyiap` |
| Passport Number | Single line text | Passport number. Used by the program roster automation. | `fldaJKQF1Z0rUjGK9` |
| Passport Expiration Date | Date | Passport expiry. | `fldlUVhlGMK8UmHeS` |
| Passport Expiration Status | Formula | Missing / expired / valid / expiring within 183 days. | `fldTNDv7Tqpd4QXtk` |
| Background Check | Attachment | Background check document. | `fldXsWYnsP9gjNCKu` |
| Background Expiration Date | Date | When the background check expires. | `fldvOKmMkWsLvJrYL` |
| Background Check Expiry Status | Formula | Missing / expired / valid / expiring within 183 days. | `fldG0auaksuHW6EYJ` |
| Driver License | Attachment | Driving licence. | `fldUp5pWq0GJoxR4V` |
| Driver License Expiration Date | Date | Licence expiry. | `fldVAVUWnZQPbz4NN` |
| Driver License Status | Formula | Missing / expired / valid / expiring within 183 days. | `fld4YtdPrNvM14xlB` |
| Highest Medical Training | Single select | Their highest medical qualification. | `flduTTTiMtOkauBrx` |
| Medical Certification Expiration Date | Date | When that certification expires. | `fldFlf0W7brTpCE3E` |
| Medical Certification Expiry Status | Formula | Whether the first aid certificate is valid, expired or missing. | `fldU8qhPI8oQXQrjE` |
| Life Guard Certification? | Single select | Whether they hold a lifeguard certificate. | `fld6ZshZS7mot7HeY` |
| Lifeguard Certificate | Attachment | The certificate itself. | `fldC5346EdpMOYQU0` |
| Lifeguard Certificate Expiration Date | Date | Certificate expiry. | `fldF3fWpxYQbm1Odx` |
| Lifeguard Certificate Status | Formula | Missing / expired / valid / expiring within 183 days. | `fldQ1yCtv1sg8EdEk` |

## Pay and finance

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Payment Currency | Link → Currencies | Currency they're paid in. | `fldWxFFgzKVkqLjsJ` |
| Current Daily Rate | Currency | Their standard daily rate in that currency. | `fldEorlRiepGgWQCl` |
| Rate USD | Currency | The same rate in US dollars. | `fldDW2aNekFBVgjDn` |
| Payment Detail Notes | Long text (rich) | Bank or payment platform details and notes. | `fld4yPKbbBGMC7Ugq` |
| Statements | Link → Statements | Statements they're responsible for reconciling. | `fldMiJKaPfdglIBRk` |
| Associated Expenses | Link → Expenses | Expenses attributed to them. | `fldC0Nk00w3bFzOGK` |
| Pending Associated Expenses | Count | How many of their expenses are still unreconciled. | `fld9SSMttJGmfHlcg` |
| Total Associated Expenses | Count | Total expenses attributed to them. | `fldg6qaWlToDykILb` |
| Has Credit Card? | Single select | Whether they hold a company card. | `fldyd8fIC9sVo34X6` |
| CC Last 4 Digits | Number | Last four digits of that card. | `fldMAO725J6NiM8qZ` |
| Revolut Card | Single select | Whether they have a Revolut card. | `fldVeKSEnRc98nM3m` |
| Gusto Set Up | Checkbox | Whether they're set up for payroll in Gusto. | `flds9FDV5XyT3C3LA` |

## Emergency contact

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| PEC Name | Single line text | Personal emergency contact's name. | `fldiPF718gqq5yNBj` |
| PEC Country Code | Link → Countries | Dialling code for their emergency contact. | `fld4ajj59yYGEygpl` |
| PEC Phone | Phone | Emergency contact's phone number. | `fldnOlHudrCrFFEmC` |

## Equipment and training

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Has Medical Kit? | Single select | Whether they hold a medical kit. | `fldj7BBTR1Sdug2C7` |
| Has Radios? | Single select | Whether they hold radios. | `flddrm6MFWfHbYtPH` |
| Has SPOT? | Single select | Whether they hold a SPOT satellite tracker. | `fldc0jOJydzSrYmjg` |
| SPOT ESN Number | Single line text | Serial number of that tracker. | `fldrtAkWOo1sLTomp` |
| Other Equipment | Single line text | Any other kit they hold. | `fldipOLY9mvVdaIHK` |
| Has SWAG? | Single select | Whether they hold branded merchandise. | `fldKSSAzV7siEyLAX` |
| Training Completed? | Checkbox | Whether they've completed staff training. | `fldZTK19hiaP7Mcno` |
| Training Completion Date | Date | When they completed it. | `fldxyMinIazEvNBiQ` |
| Career Ladder Folder | URL | Their career development folder. | `fldhFAeLtBkn3erVy` |

## Assignments and portal access

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Assigned Programs | Link → Program Field Staff Assignments | Programs they're assigned to. | `fld0P2RFcEVDZOGUD` |
| I&B Built | Link → I&B Requests | Itineraries and budgets they've built. | `fldXz9dbHvtnHO6sH` |
| SOFTR Permanent Login Link | URL | Their permanent login link for the Softr portal. | `fldpCN9p0e6G7YuoU` |
| Magiclink | URL | One-time login link for the portal. | `fldB5pss2hTYXRmrX` |
| Is Admin | Checkbox | Whether they have admin rights in the portal. | `fldR8i0mJT1UuCwD0` |
| Avatar | Attachment | Profile picture used in the portal. | `fldK3nmbrTnl1xHVE` |
| Softr User Created Time | Date | When their portal account was created. | `fldVZ7V3mxM3vihPA` |
| Softr User Last Seen Time | Date & time | When they last used the portal. | `fldEfzxVWJbpmjNs5` |

---

# 27. Program Field Staff Assignments

`tblx3IsFspsgOczfc` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblx3IsFspsgOczfc)

Connects a staff member to a program, and carries their contract, salary, flights and payment tracking.

## Program and staff

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Program Staffing ID | Formula | Program name, role type and staff member combined. | `fldlSGw64K8SCRhsB` |
| Program | Link → Programs | The program they're assigned to. | `fldlcxUS0NjPNmKMQ` |
| Program Name | Lookup | Program name. | `fldLsFCxkdrCmDyO7` |
| Destination (from Program) | Lookup | Where the program takes place. | `fldsKA55j2Ekn5luv` |
| Country of Program | Lookup | Country the program takes place in. | `fldvQZGMyDBRLtn3K` |
| Program Start Date | Lookup | Program start date. | `fldcG7ZBPQW9Z7ujD` |
| Program End Date | Lookup | Program end date. | `fld0KU8v6dfVc81cC` |
| Number of Ground Days | Lookup | Days in the field, used to calculate salary. | `fldWgNJ1XHwADYLpy` |
| Preparation Days | Lookup | Prep days allocated, used to calculate salary. | `fldadzJ3gZhz5qPH2` |
| Selected Field Staff | Link → Field Staff Profiles | Who is assigned. | `fldMtkl2CFIUaEOrS` |
| Program Role Type | Single select | The role they're filling on this program. | `fldyT0ZH2gc3L2Z74` |
| Staff Assignment Status | Single select | Where the assignment stands. | `fldVYSLr3IVUx2oWx` |

## Salary

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Staff's Current Daily Rate | Lookup | Their standard daily rate. | `fldnYsyuvXug8zT2H` |
| Staff's Current Daily Rate USD | Lookup | That rate in US dollars. | `fldghs5nCXKFlk3Z6` |
| Staff's Accepted Currencies | Lookup | Currencies they can be paid in. | `fldDOtLncuweFEONx` |
| Currency for Program Negotiated Staff Salary | Link → Currencies | Currency agreed in this program's contract — what they'll actually be paid in. | `fldUZlYmQhKpoK4h9` |
| Program Negotiated Daily Staff Salary | Currency | Daily rate agreed and signed for this program. | `flds67ULskRbLRJaY` |
| Solo Program | Checkbox | Tick if they're the only staff member — adds a 10% bonus. | `fldvvnSToHkNnVqns` |
| Program Director | Checkbox | Tick if they're program director — adds a 10% bonus. | `fld9GVJVrJUxVzYbb` |
| Program Negotiated Daily Salary with Applied Bonuses | Formula | Daily rate plus any solo or director bonus. Equals the base rate if neither applies. | `fldaQWQGQSDqPOsTa` |
| Negotiated Total Salary | Formula | (Daily rate with bonuses × ground days) + one extra day + (half the daily rate × prep days). Training completion is added to the second payment, not here. | `fldCzyyJM9mdrQuAl` |
| Negotiated Total Salary USD | Formula | The same total converted to US dollars. | `fldkT8ooXRinUePRE` |
| Exchange Rate | Lookup | Rate used for that conversion. | `fldBpu7fhFcVSRJFn` |
| Training Completion | Checkbox | Tick once training is done — adds a day's rate to the second payment. | `fldDndcMZtMjgCNxE` |
| Salary Deduction | Currency | Any deduction applied to their pay. | `fldvuz3r5HgAqfDiS` |
| Staff Salary Notes | Long text (rich) | Notes on this person's pay for this program. | `fldoJmOdfxBmF2kyh` |

## Payments

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Current Payment Date Due | Formula | Next payment date: 10 working days before start if the first payment hasn't gone, or 10 days after the program ends if it has. | `fldxHQxhdTlOTl8Vp` |
| First Payment Amount | Formula | 50% of the negotiated total salary. | `fldZn1PXw3427SoDc` |
| First Payment Requested | Checkbox | S&R has asked Finance to pay. | `fldqnuZCeWqEewmzm` |
| First Payment Sent | Checkbox | **Finance only.** Tick once paid so S&R can notify the staff member. | `fld43AUvX0146CXq5` |
| Second Payment Ready | Checkbox | The second payment is cleared to go. | `fld34b0i7jtL2vZB8` |
| Second Payment Amount | Formula | The remaining balance, plus a day's rate if training is complete. | `fldh1jWquTAXAFv4F` |
| Second Payment Sent | Checkbox | Tick once the second payment has been made. | `fldSKTZIiVzZSnLSs` |
| Second Payment Sent TimeStamp | Last modified | Timestamp used to archive salary requests in the Finance dashboard. | `fldMsZNrSyVj2MoJd` |

## Flights and preparation

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Departure Flight Location | Single line text | Airport code they fly out from. | `fld8erClcfDoJX2ip` |
| Return Flight Location | Single line text | Airport code they return to. | `fldfasRf0eDKHNwjN` |
| Staff Flight Arrival at Destination | Date & time | When they land at the destination, before the program starts. | `fldGzg6bqX1Cp51at` |
| Staff Flight Departure from Destination | Date & time | When they leave the destination after the program ends. | `fldN5WeZtE6G2qUWc` |
| Staff Flight Cost | Currency | Actual cost of the ticket in US dollars. | `fldGeLhw5G7EoJXFn` |
| Flight Document | Attachment | Flight confirmation document. | `fldN6fwvNHkz9zE0X` |
| Flight Ticket Purchased | Checkbox | Ticket has been bought. | `fldATHWJ0Ss1tWUPh` |
| Flight Email Sent | Checkbox | Confirmation document has been sent to the staff member. | `fldM6ChjfW0arQFh3` |
| Staff First Full Preparation Day | Date | Their first full prep day. | `fldfaTk1Yov8LbiMt` |
| Preparation Days Email Sent | Checkbox | Prep days email has gone to the staff member. | `fld2i2Dm7HzuaIZUK` |

## Contract, cash and meetings

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Contract Status | Single select | Where the contract stands. | `fldC1m2FsohFKHphK` |
| Contract URL | URL | Link to the signed contract. | `fld7AkJs2Y8vEDHed` |
| Program Terms | URL | Link to the program terms they agreed to. | `fldNFtxK8kdKD3Hus` |
| Selected for Cash Instructions | Checkbox | They're carrying program cash. | `fldan6Y8fkoGa5SsW` |
| Cash Instructionss | Long text (rich) | Instructions for handling that cash. *(Field name is misspelled in the base.)* | `fldYzMiZfkCQ50Wgr` |
| Confirmed Leftover Cash | Currency | Cash returned at the end of the program. | `fldhKcBWw3WeNkzfF` |
| Confirmed Personal Funds | Currency | Their own money spent that needs reimbursing. | `fld8urhT6yimRr0f2` |
| Program Meetings | Link → Program Meetings | Meetings they're expected at. | `fld4EJaVJfepgRMIn` |
| Program Participants | Single line text | Leftover connector stub. Safe to ignore. | `fldwlyPZ8ukvCKQfw` |

---

# 28. EM QC Checks

`tbllT9IPUc6zLtOlB` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tbllT9IPUc6zLtOlB)

The Experience Management quality-control checklist — one record per program. Most fields are simple gates; the formulas at the top summarise them into a readiness status.

## Status summaries (all calculated)

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| EM Checks Status | Formula | Overall readiness across setup, logistics and registration. | `fld28BQcaLRYsfaKQ` |
| LOI Registration Period Status | Formula | Complete or Pending for the LOI registration period. | `fldqsY8C4rajWkppF` |
| Program Confirmed: Minimums Met Status | Formula | Whether the essential pre-departure steps confirm minimums are met. | `fld0npqlkiauFY8K9` |
| Program Confirmed: Numbers Finalized Status | Formula | Whether registration steps confirm final numbers. | `fldZEyIeZDMzxIOCZ` |
| Program Confirmed: Registration Complete Status | Formula | Whether registration is fully complete. | `fldvWftyIbMnuq49V` |
| Program Launch Status | Formula | Whether all QC sign-offs and launch emails are done. | `fldTwyex2VP44roMX` |
| Post Program Status | Formula | Whether post-program surveys and debriefs are complete. | `fldXeVP6wxQPh3Nsy` |

## Program context

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Programs | Link → Programs | The program being checked. | `fldQDGudw247dkSyb` |
| Record | Link → OPS QC Checks | The matching OPS checklist record. | `fldqHYnOtdDhYRLdl` |
| Program Start Date | Lookup | Program start date. | `fld3nhzxh5HGHNk6L` |
| School Flight Departure | Lookup | When the school group leaves the point of origin. | `fldzReNHKxJfhLVJI` |
| School Flight Return (from Programs) | Lookup | When the group arrives back home. | `fldS7ziT84rguVYRW` |
| Days until program start date | Lookup | Countdown to departure. | `fldlw1TFFiPrrijWB` |
| Program Notes | Lookup | Link to the program notes document. | `fldrjZEbQBkvnmxXp` |
| Jotform Registration Link | Lookup | Registration form for this program. | `fldoh2ONFk48iDl2O` |
| POD \| PT Lead | Lookup | Partnerships lead. | `fldel1SOUUnENBjD9` |
| POD \| OPS Lead | Lookup | Operations lead. | `fldWL5oP47ZUeaGMf` |
| POD \| S&R Lead | Lookup | Staffing & Risk lead. | `fldi9lmf4gZX6CRxM` |
| POD \| EM Lead | Lookup | Experience Management lead. | `fldQDcloKB2VPXADa` |
| EM Lead | Lookup | The assigned EM lead. | `flduCcGt3rAwY2ZGL` |
| EM Lead Assigned Status | Single select | Whether an EM lead has been assigned yet. | `fldWpXvmjybQ9vP9O` |
| Handover Status | Single select | Where the handover from PT to EM stands. | `fldO6YuoWljTOV6in` |
| Link to Program Dashboard | URL | The school-facing dashboard for this program. | `fldaIkC7mJvZ4EwLm` |
| Program Website | URL | The program's public website. | `fld3bfavVRkajjErK` |
| LOI Email | URL | The letter-of-intent email thread. | `fldvqpTWtlXV35OD5` |
| Link to RAMP Folder | URL | Folder holding the risk assessment documents. | `fldUFFdQbpfotDddP` |

## School-facing deliverables

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Registration Management | Single select | Who is running registration. | `fldDq44GvSzLOP3Ls` |
| Transportation to Program Management | Single select | Who arranges transport to the destination. | `fld08bUG0sprJGpTp` |
| Program Dashboard Sent to School | Checkbox | Dashboard has been shared. | `fldBCfjRKf2YIl0kg` |
| Program Website Sent to School | Checkbox | Website has been shared. | `fldcc48wPGjQBqB9j` |
| Travel Policies Created and Added to Dashboard | Checkbox | Travel policies published to the dashboard. | `fld1YaLcAYZMd8zCT` |
| Travel Policies Complete and Signed | Single select | Policies signed off by the school. | `fldtTPn11VS8cGuUP` |
| Hotel Information Document Sent to School | Checkbox | Hotel information shared. | `fldLoqZdM5s2mHh2V` |
| Rooming List | Single select | Rooming list status. | `fldTLPsJlDHtJV3Y6` |
| Packing List | Single select | Packing list status. | `fld8Lr23VunERFhjG` |
| Contract | Single select | School contract status. | `fldzuJBHHBGR5RCeh` |
| Pre Departure Learning Resources | Single select | Pre-departure learning material status. | `fldZZ9ybOiLoHu4ym` |
| Flight Information | Single select | Flight information status. | `fldBJPkIC8jpouzNw` |
| Flight Information Document Sent to School & Linked in Dashboard | Checkbox | Flight document shared and linked. | `fldc2acNOMfU0O1uk` |
| Final Flight Information in Envault/Dashboard Share with School | Checkbox | Final flight details shared. | `fld51P25IaJN25QOP` |
| Program website updated with latest itinerary (Canva) | Single select | Website reflects the current itinerary. | `fldlTrIZB9ttZqHeF` |
| Envoys Photo Album on Website/Dashboard | Single select | Photo album published. | `fldFYTiBh1gj8e887` |
| Final HBH Shared with School | Single select | Final hour-by-hour shared. | `fldJYKdeRglyS2967` |

## Risk, safety and staffing

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| RAMPS | Single select | Risk assessment and management plans status. | `fldEnvBaxqqIc6PO6` |
| Medical RAMP | Single select | Medical risk plan status. | `fldVvwg4P3j0Dbrwi` |
| Field RAMP Ready | Checkbox | Field risk plan is ready. | `fldufCISA6pCv0B7n` |
| Destination Report | Checkbox | Destination report completed. | `fldWg7ADNppQM6Q6F` |
| Health Safety and Security Manual | Checkbox | Manual prepared for this program. | `fldpSmsY2bVpNqFLZ` |
| Global Rescue | Single select | Global Rescue coverage arranged. | `fldAHhqvBMMVze2er` |
| SWAG | Single select | Branded merchandise organised. | `fldINVLHm69a2aR3y` |
| Envoys Staff Confirmed | Single select | Field staff confirmed for the program. | `fldanlrT5Ns7x3XD9` |
| Envoys Staff Profiles | Single select | Staff profiles shared with the school. | `fldxuInXLMFho2iRH` |

## Registration completeness

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Basic Information | Single select | Participant basic details collected. | `fldUP3QxDc7SeOyy2` |
| Dietary Restrictions | Single select | Dietary information collected. | `fldRwM2sFJeIfokGt` |
| Medical Information | Single select | Medical information collected. | `fldQIXkfJ7wdaFpwI` |
| Emergency Contacts | Single select | Emergency contacts collected. | `fldQNQD8AaQclRBEw` |
| Participant Agreements | Single select | Agreements signed. | `fldR1Kbfvy9VIO0AA` |
| Passport Copies | Single select | Passport copies collected. | `fldX5ow1K3RhskJTb` |

## Invoicing and payment

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Status on Payment | Single select | Overall payment status for the program. | `fldw0AVJfRA6NfI5U` |
| Payment Method | Single select | How the school is paying. | `fldATXxpQlm6ngIyn` |
| Financial Aid | Single select | Whether financial aid is involved. | `fldIh34sbfFD1fUcw` |
| Deposit Invoice | Single select | Deposit invoice status. | `fldVvi5rQ0Ri9ycck` |
| Balance Invoice | Single select | Balance invoice status. | `fldRI8dsB23zkPkK6` |
| Additional Invoice | Single select | Any additional invoice status. | `fldLsyzu2qtEw9qGu` |

## Flights operations

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| TLT Ready and Shared with Flight Team | Checkbox | Traveller list ready and handed to the flight team. | `fld7u3502M3e1ZKPt` |
| Ticket Issued Document Ready | Single select | Ticket-issued document prepared. | `fldkHlBJtL4HRvnMg` |

## QC sign-off and meetings

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Regional Management QC | Checkbox | Regional management has signed off. | `fld4y1t0s6dGXEoAN` |
| Risk and Staff QC | Checkbox | Risk and staffing signed off. | `fld3Ujnk15dv3PTqB` |
| Flights QC | Checkbox | Flights signed off. | `fldGXrdcxlLYTfRqO` |
| OPS QC | Single select | Operations sign-off. | `flddSd0f0GL8jEMoH` |
| S&R QC | Single select | Staffing & Risk sign-off. | `fldKMgHhBZHFDh6AI` |
| FINANCE QC | Single select | Finance sign-off. | `fldu9LKMafBmDTP32` |
| Flights/Trains QC | Single select | Flights and rail sign-off. | `fldNZoWbNRgIV8czf` |
| EM QC Email Sent to AllHands | Single select | Launch email sent to the whole team. | `fldls56VmCo9P6wOf` |
| HQ Lead Email Sent to School | Single select | HQ lead introduced to the school. | `fld3Q31qyo9UvIQdi` |
| Check In Meeting (School) | Checkbox | Check-in meeting held with the school. | `fldEw5ZKQCGsFWMR3` |
| Optional Check-In Meeting w/ School | Checkbox | Optional extra check-in held. | `fldC7sJN9kpximDxn` |
| Orientation Meeting | Checkbox | Orientation meeting held. | `fldteX3273anydmor` |
| Team Traveler Meeting | Single select | Traveller team meeting status. | `fldIeXdlXZtH97Cgq` |
| Program Handover Meeting | Single select | Handover meeting status. | `fldYMqRQdEafZAwJg` |
| Program's WhatsApp Group | Single select | WhatsApp group set up. | `fldAtrsrmnVOoCVhA` |
| Email to Global Ed with Survey | Single select | Post-program survey sent. | `fldJKxQ6YREkeVCIm` |
| HQ Debrief Meeting | Single select | Internal debrief held. | `fldIIsDeNsiFkoheU` |
| School Debrief Meeting | Single select | Debrief held with the school. | `fldtQf4UB7dEHgNgX` |

## Notes

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| EM General Notes | Long text (rich) | General EM notes on this program. | `fldzV5ykzInTPxq1S` |
| EM Deadlines | Long text (rich) | Important EM deadlines. | `fldhAjaLVawjRAzHI` |

---

# 29. OPS QC Checks

`tbl33v2Jn59ABBXWE` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tbl33v2Jn59ABBXWE)

The Operations quality-control checklist — one record per program, grouped by booking category. Nearly every check is a single select. "FPF" means Field Program Folder; "HBH" means the Hour-By-Hour itinerary.

## Header

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Name | Formula | Program name with pending or complete QC status appended, based on any unchecked fields. | `flduUHQwHot0WCoxQ` |
| OPS QC Checks Status (Single Select) | Single select | Manual overall status for the checklist. | `fldVxOcEO2lfDalQ6` |
| Programs | Link → Programs | The program being checked. | `fldCpOg5BfhvHo22Z` |
| Program Name (Linked) | Lookup | Program name. | `fld9K65k1bAnYOBnI` |
| Program Start Date (Linked) | Lookup | Program start date. | `flduWh1UUKEYnY3bY` |
| Due Date | Formula | 15 days before the program start date. | `fld2lG58dVB19vlSO` |
| EM QC Checks | Link → EM QC Checks | The matching EM checklist record. | `fld6Y1ASgNzvw8U5Y` |

## OPS support and general

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Dates & No. of Travelers Match with OPS Support Program | Single select | Dates and headcount agree with the OPS support provider. | `fldGadykoXEkBytY6` |
| OPS Support final payment made | Single select | Final payment to the OPS support provider is done. | `fldv35DVjQxRAqfqD` |
| OPS Support Contract or Final Voucher Saved in FPF | Single select | Contract or voucher filed. | `flduM5fAi9oMlDHVV` |
| All Booking Fields 'Booking Made', 'No Booking Needed' or 'Field Booking Needed' | Single select | Every HBH item has a resolved booking status. | `fldMOkjkUn2Pa2ieb` |
| Petty Cash Requested to Finance | Single select | Petty cash requested. | `fldg3R3apjvPCevlt` |
| Expense Sheet Saved in FPF | Single select | Expense sheet filed. | `fldU0nWLi5PACoQGq` |
| Vendor Contact List Saved in FPF | Single select | Vendor contact list filed. | `fldRjQpiuXzFjewOf` |
| Printable HBH Saved in FPF | Single select | Printable itinerary filed. | `fldTwyub12tsSz5oh` |

## Accommodation

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Hotel Booking or Contract Saved in FPF | Single select | Booking or contract filed. | `fldbluP9Y821cpKR4` |
| Hotel Contract Dates Match HBH | Single select | Contract dates agree with the itinerary. | `fldCxlvE3lGpYmjOL` |
| Breakfast Included in Hotels or Breakfast Added to Staff Budget | Single select | Breakfast is either included or budgeted for. | `fld4adC7nX3L9W5Iq` |
| Dietary Restrictions Shared with Hotel for Breakfast | Single select | Hotel knows about dietary needs. | `fldNF62qQmIwDwDy8` |
| Room Distribution Matches Group Size and Gender Distribution | Single select | Rooming works for the group make-up. | `fld1OATiQQhCWr9CB` |
| Rooming List with Traveler Names Sent to Hotel | Single select | Named rooming list sent. | `fldASWWbEPzQKafCN` |
| Rooming List Saved in FPF | Single select | Rooming list filed. | `fldI32QIYgxWqqmeQ` |
| Hotel Price Added to HBH | Single select | Cost entered against the itinerary. | `fldGnsRe5k196X1rt` |
| Final Payment Made to Hotel | Single select | Hotel paid in full. | `flddZvST10Vu9FTub` |
| Hotel Quality Check Completed (Location, Reviews, Rating) | Single select | Hotel vetted on location, reviews and rating. | `fldFgqnXkLfmAvFPI` |
| Booking.com Reservations Updated with Group Names | Single select | Reservations show the correct traveller names. | `fldDpK2RYJxSHZVTa` |
| Hotel Vendor Contact Saved in Database | Single select | Hotel added to the Vendors table. | `fldAJaRugu4y5iWoG` |
| Hotel Vendor Linked to HBH | Single select | Hotel linked to the relevant itinerary items. | `fld7lEa2Y1RPcSrBQ` |
| Meeting Spaces Confirmed for Activities | Single select | Meeting rooms booked for program activities. | `fld9kU7T0WL7J2aVD` |
| Meeting Spaces Confirmed in Hotel | Single select | Hotel meeting spaces confirmed. | `fld6NXRhpjShG34Ea` |
| Night Watchers Booked and Payment Completed | Single select | Overnight security arranged and paid. | `fldWktjsNA8HBphgN` |
| Nurse Booked and Payment Completed | Single select | On-site nurse arranged and paid. | `fld0R9UKSVExtYSHK` |

## Transportation

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Transport Vendor Contract Dates Match HBH | Single select | Transport contract dates agree with the itinerary. | `fldcWfb15G39Jkm3S` |
| General Envoys Schedule Matches HBH Itinerary (Including Times) | Single select | Vendor's schedule matches ours, times included. | `fld7TYP7DInKPW3TU` |
| Vendor Booked Itinerary Matches HBH | Single select | What the vendor booked matches the itinerary. | `fldPakI6fWyw8paPZ` |
| Bus Size Works for Group Size | Single select | Vehicle is big enough for the group. | `fld63UcDq4j7lerug` |
| Transportation Price Added to HBH | Single select | Cost entered against the itinerary. | `fldgxNwn8be3SgEG5` |
| Final Payment Made to Transportation Provider | Single select | Transport provider paid in full. | `fldsUpVgqRo2W7eN1` |
| Transportation Vendor Contact Saved in Database | Single select | Provider added to the Vendors table. | `fldZc6a90brgSsaHf` |
| Transportation Vendor Linked to HBH | Single select | Provider linked to the relevant itinerary items. | `fldKc4fnfFMEpHcZK` |
| Hotel Rooms Booked for Bus Drivers | Single select | Driver accommodation arranged. | `fldgffleEdEPmxGwM` |
| COI or MOU Saved in Folder | Single select | Insurance certificate or MOU filed. | `fldCxPMNeCd08jHcO` |
| Metro Cards Purchased | Single select | Public transport cards bought. | `fldmsiJDlujxOzqpQ` |
| Metro Card Delivery or Pick Up Arranged | Single select | Delivery or collection arranged. | `fldjqVn7FJlGrJAff` |

## Trains

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Ticket Dates Match HBH | Single select | Ticket dates agree with the itinerary. | `fldNA7qzQoo6ANjKU` |
| One Ticket per Traveler Available (Students, Faculty, Staff) | Single select | Everyone travelling has a ticket. | `fldbaOj7dicUCu23J` |
| Train Numbers Added to HBH | Single select | Train numbers recorded in the itinerary. | `fldtRR1cMrchdfcJW` |
| Final Train Price Added to HBH | Single select | Cost entered against the itinerary. | `fld0J0XqwMHprl2xb` |
| Name Check Completed | Single select | Names on tickets checked against travel documents. | `fldDDtCdtPQlYkQTV` |
| Train Vendor Contact Saved in App | Single select | Rail operator added to the Vendors table. | `fldzkYxP7YHkGs1nD` |

## Activities

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Activity Booking Confirmation Document Saved in FPF | Single select | Confirmation filed. | `fldkWOztGXNDwAnBn` |
| Dates in Activity Booking Confirmations Match HBH | Single select | Confirmed dates agree with the itinerary. | `fldYTwyNA98IXcikc` |
| Times in Activity Booking Confirmations Match HBH | Single select | Confirmed times agree with the itinerary. | `fldPF8ubtvP6q42Z8` |
| Final Activity Price Added to HBH | Single select | Cost entered against the itinerary. | `fldXOUM5FYecp8ayl` |
| Final Payment Made to Vendor | Single select | Activity vendor paid in full. | `fld6faxJ1jnCeYhgK` |
| Vendor Contact Saved in Database | Single select | Vendor added to the Vendors table. | `fldX3Bzw4fiuoQIKv` |
| One Ticket per Traveler Available | Single select | Everyone has an activity ticket. | `flddy20eKUHAVulGu` |
| Core Activity Description Saved in FPF | Single select | Activity description filed for the field team. | `fldVqbiE3GWrqxT81` |
| Activity MOU Signed and Saved | Single select | MOU signed and filed. | `fldOLDvsFubOmhomo` |

## Meals

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Restaurant Booking Confirmation Saved in FPF | Single select | Confirmation filed. | `fldl1gNiGHOVCy2EX` |
| Dates in Restaurant Booking Confirmations Match HBH | Single select | Confirmed dates agree with the itinerary. | `fldiVOdwGeAGGtsQM` |
| Times in Restaurant Booking Confirmations Match HBH | Single select | Confirmed times agree with the itinerary. | `fld55jXmgw3MyJJOK` |
| Numbers in Confirmation Match Total Travelers | Single select | Covers booked match the group size. | `flde1bk8NRc2seI7w` |
| Final Meal Price Added to HBH | Single select | Cost entered against the itinerary. | `fldDbZVL63tRRYwtb` |
| Final Payment Made to Restaurant | Single select | Restaurant paid in full. | `fldvfwD0RrRqyesB0` |
| Dietary Restrictions and Allergies Shared with Vendor | Single select | Vendor briefed on dietary needs and allergies. | `fldMDnJ0EG0LHr9jd` |
| If Booked by Staff: Budget Document Shared with Staff | Single select | Field staff have the meal budget document. | `fldgHPhk00AmJyGP2` |
| If Booked by DMC: Restaurant Names and Menu Selection Received and Saved in FPF | Single select | DMC's restaurant and menu choices filed. | `fldBgV3svv566u4o1` |
| If Booked by RM: Meal Plan Document Completed and Saved in FPF | Single select | Regional manager's meal plan filed. | `fldwY50D6FR51PssR` |

## Notes

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| OPS QC Checks Notes | Long text (rich) | General notes on the checklist. | `fldNEgGNkOD80gQGR` |
| OPS Support Notes | Long text | Notes on the OPS support provider. | `fldv2KfgB5iFgdFSy` |
| General HBH & FPF Notes | Long text | Notes on the itinerary and program folder. | `fldQjgooCLjN1O9L6` |
| Meals - General Notes | Long text (rich) | General notes on meals. | `fld6INADxEOzw8clz` |
| Meals - Specific Notes | Long text | Notes on specific meals or venues. | `fldi1G5vf5b1wPm75` |
| Notes on QC Checks | Long text (rich) | Anything else about the QC process. | `fld3zqbsLflBStJcd` |

---

# 30. Program Meetings

`tblSoLVxvEuOxpinz` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblSoLVxvEuOxpinz)

Meetings scheduled around a program. All meetings are planned in Eastern Time.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Meeting Name | Formula | Program plus meeting type, or the optional name if the type is "Other". | `fldtk1MG4pGTyd7IV` |
| Programs | Link → Programs | The program this meeting is about. | `fldqvSERKjctR1Ebb` |
| Program Name | Lookup | Program name. | `fldOzNvkxDwKH4O9Y` |
| Program Start Date (from Programs) | Lookup | Program start date, used to propose a meeting date. | `fldjAM07r9EuLlkFI` |
| Program End Date (from Programs) | Lookup | Program end date. | `fldPkys9Hv5DlTscq` |
| Meeting Type | Single select | Which meeting this is — Kickoff, Introduction, Handover, Debrief and so on. Each has its own timing and attendee list. | `fld8oWqOcD5gDFYz7` |
| Optional Meeting Name | Single line text | Name to use when the meeting type is "Other". | `fldUen4g0OdZIRvcx` |
| PROPOSED \| Meeting Date | Formula | Suggested date based on the standard timing rules. **A suggestion only** — you must still set a real date. | `fld2CPm0MC93BfdcP` |
| SET \| Meeting Date | Date & time | **Source of truth.** The confirmed date and time, in Eastern Time. | `fldXegAOlGAD1LVfC` |
| Meeting Participants | Single line text | Attendee email addresses, separated by commas. | `fldrBJKXYuFC1nTtC` |
| Link to Program Meeting Notes | URL | Notes document for this meeting. | `fld29tuAjDYnRbnJ3` |
| Program Field Staff Assignments | Link → Program Field Staff Assignments | Field staff expected at this meeting. | `fldp7RjiTVn7sh6eI` |

---

# 31. Program Dashboard

`tblLpZaD9m60K5EN1` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblLpZaD9m60K5EN1)

Resources published to the school-facing program dashboard. **Previously called "Program Documents"** — the table ID hasn't changed, so existing scripts still work.

> ⚠️ On the Programs table, the link back to here is the field named **"Program Documents"**, not the one named "Program Dashboard".

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Dashboard Link | Formula | Program name and resource combined. | `fldpHWEx9uKhuFZbR` |
| Programs | Link → Programs | The program this resource belongs to. | `fldLlFGJxRy7hE2cZ` |
| Resource Name | Single select | Which standard resource this is. | `fldyVH7dOU2yOTrZJ` |
| Resource Description | Formula | Standard description for the selected resource. | `fldzmhd9BPzc0SE0G` |
| Other \| Resource Name | Single line text | Name to use when the resource isn't on the standard list. | `fldeegZ4sICGKJY7w` |
| Other \| Resource Description | Single line text | Description for that custom resource. | `fld6p0NhyCp1xx771` |
| Resource Link | URL | Where the resource lives. | `fldIEK8geGvAwjiqh` |
| Active in Dashboard | Checkbox | Tick to show this resource on the school's dashboard. | `fldm7hLBs8qwKm1ds` |

---

# 32. Envoys External Toolkit Base

`tblGTPzs39fuS5duf` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblGTPzs39fuS5duf)

A catalogue of external tools and resources the team uses. Stands alone — no links to other tables.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Tool Name | Single line text | Name of the tool or resource. | `fldHapVa9zJvkBrsA` |
| Tool Link | URL | Where to find it. | `fldH73L0s46HHUoYv` |
| Description of Tool | Long text (rich) | What it does and when to use it. | `fldK92MqoJZ6UIpKI` |
| Resource Category | Single select | What kind of resource it is. | `fldRE3QpNOGu8vgav` |
| Tags | Multiple select | Tags for searching and filtering. | `fldxEkGa0NkyCosvX` |
| Open URL | Button | Opens the tool link in a new tab. | `fldLR75iJvE5Teg13` |

---

# 33. Program Documents

`tblBCgjswoiTXYD3L` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblBCgjswoiTXYD3L)

Internal documents attached to a program. **This is a new table** that reuses a name previously used by what is now the Program Dashboard table — always check the table ID.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Documents ID | Formula | Program name and document combined. | `fldfUdNmwwWaHyYrB` |
| Programs | Link → Programs | The program this document belongs to. | `fldByWPyUTK0ux1sJ` |
| Docuemnt Name | Single select | Which document this is. *(Field name is misspelled in the base.)* | `fldo8Yg2bWer1Mqft` |
| Document Link | URL | Where the document lives. | `fldyR1h5BIHtJchG1` |
| Last Update Timestamp | Last modified | When the record last changed. | `fldckyUqPaCpXf0tc` |
| Document Ready | Checkbox | Tick when the document is finished and usable. | `fldk0LoUlrtsYYioS` |

---

# 34. Utilities

`tblLviiwRM35IOmlS` · [Open table](https://airtable.com/appi7EFBj8bLjhbHj/tblLviiwRM35IOmlS)

A helper table used by automations and scripts. **Do not delete.** No links to other tables.

| Field | Type | What it's for | Field ID |
|---|---|---|---|
| Id | Single line text | Identifier for the utility row. | `fldWmB7qba6l5QJ9o` |
| Type | Single select | What kind of helper row this is. | `fldm1C1yAVyD2Qs0S` |
| Day N° | Number | Day number used by itinerary-generation automations. | `fld58LqJYPbHcJP3v` |

---

*Generated from the live ENVOYS | V.0 base on 13 August 2026. Field IDs are stable; field names are not. If the base changes, re-generate rather than editing this file by hand.*
