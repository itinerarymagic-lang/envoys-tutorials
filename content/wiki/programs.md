# Programs

**Primary field:** Program ID

Center Database for Programs that enter the LOI stage. For previous stages refer to I&B Requests.

This is the main hub of the base. Once an I&B Request is approved, it becomes a Program record and everything else hangs off it — itinerary, costs, staffing, participants, QC checklists, invoices, and reconciliation. Roughly 230 fields, most of them computed.

---

## Understanding the cost prefixes

Costs appear four times over, once per stage of the program's life. Programs have 3 stages so that we can accurately track variations in itineraries without compromising flexibility. The prefix tells you which stage you're reading:

| Prefix | Stage | Source |
|---|---|---|
| **Budget \|** | Budget version | Imported from the I&B Sheet at proposal. Should be a mirror and uses I&B Sheet as a fallback. |
| **Operations Budget \|** | Operational / Quote version | Live-working itinerary throughout until basically program starts. |
| **Forecast \|** | Forecast | Working forecast of non-HBH costs |
| **Closing \|** | Executed version | Final actual costs after the program runs |

`| AC` in the name means the number comes from **Associated Costs** (non-itinerary costs: prep days, essentials, staffing). Everything without `AC` comes from **HBH Blocks** via Program Versions.

`FIN | Reconciled …` is different again — those read actual reconciled spend from Allocations, tagged by Chart of Accounts code.

---

## Identity & core

| Field | Type | Description |
|---|---|---|
| **Program ID** | formula | Concatenates the Start Date (MM/DD/YY) and Program Name for a unique ID. |
| **autonumber** | autoNumber | Automatic Number for ID and internal capabilities. DO NOT DELETE. |
| **Program Name** | singleLineText | Source of Truth Program Name. Use this exact name for any use outside Airtable.<br><br>Program Name is usually composed as School Name (or abbreviation), Destination, Year. If necessary, before Destination one can add an identifier for the student tier or after for seasonality.<br><br>(Ex. LREI Martinique 2026, PACE LS Peru 2026, Castilleja DC Fall 2026) |
| **School** | link → Schools | A unique School Identifier linked to the record number and school name. This field is to avoid duplicates of schools with the same or similar names. |
| **Destination** | link → Destinations | Destination refers to the place where the Program will be heading to. A destination can be a Country, a City, or a Region. (Ex. Japan, Marseille, America South)<br><br>Select one of the available options. If a Destination is not listed, create one in the Destination base and make sure all fields are completed. |
| **Country** | lookup | The country is associated to the Destination selected. This is necessary to link multiple bases and people. |

## Status & classification

| Field | Type | Description |
|---|---|---|
| **Program Status** | singleSelect | The Program Status is the timeline for the program, and sub-category of the Program Phase. It is to determine specific sections from a program in LOI, Confirmed, and Operated.<br>Options: Proposal Approved - Migrate to Programs · LOI \| Initial Stage · LOI \| Registration Period · Confirmed \| Min Numbers Met · Confirmed \| Numbers Finalized · Confirmed \| Registration Complete · Confirmed \| In The Field · Operated \| Closing · Operated \| Program Closed · Cancelled \| Proposal Rejected · Cancelled \| Registration Failed |
| **Program Category** | singleSelect | To determine the Program Category, use the Program Categorization Tool available here:<br>https://docs.google.com/spreadsheets/d/1S3ynU82o7_eAWC25p0AbsAuGC4S4LKJAK4eSxJMMrrM/edit?usp=sharing<br>Options: Core · Explore · Specialized · Gamble · Other |
| **Program Type** | singleSelect | Program type depending on the school's geographical location and type of program.<br>Options: US/CA School - Mandatory Program · International School - Mandatory Program · US/CA School - Optional Program · International School - Optional Program · Other |
| **Period** | singleSelect | Periods follow the American school year calendar. (Ex. 2026-2027 refer to programs from Summer/Fall 2026 and Winter/Spring 2027).<br>Options: 2025-2026 · 2026-2027 · 2027-2028 |
| **Student Ages** | singleSelect | Student Ages attending to the program based on US standards.<br><br>Upper School: Grades 9-12<br>Lower School: Grades 6-8<br>Faculty: Adult faculty Participants only<br>Mixed: Open to grades across educational stages.<br>Options: Upper School · Middle School · Lower School · Faculty · Mixed |

## HQ team (PODs)

| Field | Type | Description |
|---|---|---|
| **POD \| PT Lead** | link → ENVOYS HQ | Envoys HQ Pod responsable for PT. |
| **POD \| OPS Lead** | link → ENVOYS HQ | Envoys HQ Pod responsable for OPS |
| **POD \| EM Lead** | link → ENVOYS HQ | Envoys HQ Pod responsable for EM |
| **POD \| S&R Lead** | link → ENVOYS HQ | Envoys HQ Pod responsable for S&R |
| **POD \| HQ Lead** | link → ENVOYS HQ | Envoys HQ Emergency Contacts for the program. |
| **POD \| HQ Blackouts Lead** | link → ENVOYS HQ | HQ contact covering this program during blackout periods when the usual leads are unavailable. |

## Dates & duration

| Field | Type | Description |
|---|---|---|
| **Program Start Date \| SOT** | date | Source of Truth: The program Start Date refers to the day the group will arrive at the Program's Destination. It determines the first Day of the HBH. |
| **Program End Date \| SOT** | date | Source of Truth: The Program End Date refers to the day the group will depart from the Program's Destination. It determines the last Day of the HBH. |
| **Number of Ground Days \| SOT** | formula | The amount of days in the field for the program. These are the dates that are accounted for in the HBH. |
| **Number of Nights** | formula | The amount of nights for which OPS has to book accommodation for the program. |
| **Days until program start date** | formula | Automatically Calculates the number of days until Program Start Date. |
| **School Flight Departure** | dateTime | Departure Date is the date the group leaves from the point of origin. It differs from the Program Start Date, since travel factors such as flight duration or layovers may result in a different arrival date. |
| **School Flight Return** | dateTime | School Flight Return is the date the group arrives at point of origin from the program destination. It differs from the Program End Date, since flight duration or layovers may result in a later arrival date. |

## Participant counts (SOT = Source of Truth)

| Field | Type | Description |
|---|---|---|
| **Number of Students \| SOT** | number | SOURCE OF TRUTH. This is the number of Students that will be reflected in the active HBH and the amount that are expected to attend.<br><br>By the program Start Date, this number should match the records of Registered Students. |
| **Number of Faculty \| SOT** | number | SOURCE OF TRUTH. This is the number of Faculty that will be reflected in the active HBH and the amount that are expected to attend.<br><br>By the program Start Date, this number should match the records of Registered Faculty. |
| **Number of Field Staff \| SOT** | number | SOURCE OF TRUTH. This is the number of Field Staff that will be reflected in the active HBH and the amount that are expected to attend.<br><br>By the program Start Date, this number should match the records of Staff Assignments. |
| **Number of Participants** | formula | Participants in the program including Students, Faculty and Staff. |
| **Min Number Students** | rollup | Minimum Students is the lowest number of students required for the program to run.<br><br>This number comes from the minimum number of students set in the Pricing Ranges negotiated with the school. It is a fixed value and should only be changed if a new agreement with the school is reached. |
| **Max Number of Students** | rollup | This is the maximum number of Students that are expected to attend the program. This number is relevant for the OPS team to manage bookings.<br><br>It is determined from the maximum number of students determined in the Pricing Ranges negotiated with the school. It is a fixed value and should only be changed if a new agreement with the school is reached. |
| **Students Registered** | count | Counts the amount of registrations linked to this program that are Students submitted successfully through JOTFORM. If numbers don't match, submit a Tech Ticket. |
| **Faculty Registered** | count | Counts the registrations linked to this program that are Faculty submitted successfully through JOTFORM. If numbers don't match, submit a Tech Ticket. |
| **Staff Assigned** | count | Counts the number of records in the Staff Assignments Table currently linked to this program. |
| **Registration Probability** | percent | Estimated Registration Probability Percentage for program to reach Minimum Numbers and guarantee execution. Manual Input. |
| **Additional Participants Notes** | multilineText | Please provide details for any additional participants who are not included as Students, Faculty, or Staff. Specify their role and purpose, what costs are expected to be covered (such as accommodation, meals, activities, or transportation), and whether these costs should be billed separately to the school or included in the overall program budget. OPS will manage how these participants are integrated into the system for calculation purposes, so be sure to include all relevant details here. |

## Documents & links

| Field | Type | Description |
|---|---|---|
| **Itineraries & Budgets Document Link** | url | Link to Itineraries & Budgets Google Sheets Link |
| **Program Notes Link** | url | Link to Program Notes. |
| **Whatsapp HQ Field Link** | url | Link to Whatsapp HQ Field Group |
| **Field Program Folder Link** | url | Link to Field Program Folder. |
| **Jotform Registration Link** | url | JOTFORM registration form sent to participants. Submissions land in School Participant Profiles. |

## Content & themes

| Field | Type | Description |
|---|---|---|
| **Program Themes** | richText | Program Themes open field. |
| **Program Lenses of Inquiry** | richText | Programs Lenses of Inquiry. Open field to write text. |
| **Debrief General Program Notes** | richText | General Post-program notes captured at debrief, covering the program as a whole. Insights not tied to specific HBH Blocks. |

## Staffing

| Field | Type | Description |
|---|---|---|
| **Staff Assignments** | link → Program Field Staff Assignments | Link to Staff Assignment Records. |
| **Staff Assignment Status** | lookup | Staff Assignment Status from Linked records. |
| **Staffing Requirements** | richText | Staffing Requirements requested by OPS/EM for program. |
| **Preparation Days** | number | Source of Truth for Preparation Days. S&R sets the amount for Preparation Days determined. |
| **Staffing Rooming** | singleSelect | Staff Rooming setup determined by S&R.<br>Options: Single Rooms · Shared Rooms · Both · TBD |
| **Staffing Rooming Notes** | singleLineText | Notes on the staff rooming arrangement. |
| **S&R \| Staff Flights Total Budget** | rollup | Sum of Staff Flight Cost across all linked Staff Assignments. IMPORTANT - Uses staff assignments input and not Associated Costs. Make sure to match for FINANCE purposes. |
| **S&R \| Staff Salary Total Budget** | rollup | Sum of negotiated staff salaries across all linked Staff Assignments. IMPORTANT - Uses staff assignments input and not Associated Costs. Make sure to match for FINANCE purposes. |

## Flights status

| Field | Type | Description |
|---|---|---|
| **Arrival/Departure Flights Status** | singleSelect | ENVOYS process Arrival/Departure Flight Status.<br>Options: No Flights Needed · School Handles Flights · Estimate Request · Estimate Ready · Flight Options Requested 1 · Flight Options Ready 1 · New Flight Options Requested 2 · New Flight Options Ready 2 · School Initial Confirmation · Final Flight Document Ready · Flight Document Sent to School \| Waiting on TLT · TLT Ready · Ticket Issued Document Ready |
| **Internal Flights Status** | singleSelect | ENVOYS process Internal Flight Status.<br>Options: No In-Country Flights Needed · In-Country Flights Needed \| TLT Pending · TLT Requested · TLT Ready · Ticket Issued Document Ready |
| **Program Flights Completion Status** | formula | Booking Status |
| **Flights \| Booked** | count | Counts the number of Program Flights (Arrival/Departure + Internal) present in the HBH in the Quote version that have been Booked. |
| **Flights \| # of Program Flights** | count | Counts the total number of Program Flights (Arrival/Departure + Internal) present in the HBH in the Quote version that need booking. |

## Booking progress

| Field | Type | Description |
|---|---|---|
| **# of Bookings Completed** | count | Counts the records in HBH that have Booking Completed Status for the Quote Version. |
| **# of Bookings Needed** | count | Counts the records in HBH that need booking managed by OPS. |
| **% Bookings Completed** | formula | % the records in HBH that have Booking Completed Status. |
| **Transportation \| Booked** | count | Transportation items in the Quote-version HBH already booked. |
| **Transportation \| # of Bookings** | count | Transportation items in the Quote-version HBH requiring booking. |
| **Transportation Completion Status** | formula | Booking Status |
| **Meals \| Booked** | count | Meal items in the Quote-version HBH already booked. |
| **Meals \| # of Bookings** | count | Meal items in the Quote-version HBH requiring booking. |
| **Meals Completion Status** | formula | Booking Status |
| **Accommodations \| Booked** | count | Accommodation items in the Quote-version HBH already booked. |
| **Accommodations \| # of Bookings** | count | # of Bookings for Accommodations on Quote Version |
| **Accommodations Completion Status** | formula | Booking Status |
| **Other \| Booked** | count | Other-category items in the Quote-version HBH already booked. |
| **Other \| # of Bookings** | count | Other-category items in the Quote-version HBH requiring booking. |
| **Other Completion Status** | formula | Booking Status |

## Connectors to other tables

> Most of these are system links. Avoid editing them directly or deleting them.

| Field | Type | Description |
|---|---|---|
| **Program Versions** | link → Program Versions | Program Versions registers the participant (students, faculty & staff) numbers in each version to the respective Hour By Hour. |
| **HBH Blocks** | link → HBH Blocks | Links the program to each row of the HBH. DON'T TOUCH. |
| **Itinerary Days** | link → HBH Days | CONNECTOR FIELD: Link to records in HBH Days. |
| **Associated Costs** | link → Associated Costs | CONNECTOR FIELD: Links record to Associated Costs Base. |
| **Program Pricing Tiers** | link → Program Pricing Tiers | Connecting Field: Connects Programs to Pricing Tiers Base for Programs. |
| **School Participant Profiles** | link → School Participant Profiles | Links the program to each row of participants incoming from Jotform. Don't touch. |
| **School's Directory Contacts** | link → School Faculty & Staff Directory | School's Staff & Faculty linked to Directory base. |
| **I&B Requests** | link → I&B Requests | Links a Program to an I&B Request. |
| **I&B Price Tier Range Finance** | lookup | Links the Pricing Tiers from an Itinerary & Budget Request to a Program for reference. Reference information for quick look and not determinative. |
| **EM QC Checks Link** | link → EM QC Checks | Links Program to EM Checks record. |
| **EM QC Checks Status** | lookup | Dynamic EM QC status pulled from the linked EM QC Checks record. |
| **EM Lead Assigned Status** | lookup | Whether an EM Lead has been assigned, pulled from EM QC Checks. |
| **OPS QC Checks** | link → OPS QC Checks | Link to QC Checks Ops |
| **OPS QC Checks Status** | lookup | Dynamic OPS QC status pulled from the linked OPS QC Checks record. |
| **S&R QC Checks Status** | singleSelect | Manual status of the S&R QC pass for this program.<br>Options: Sent · Sent with Flags · Pending |
| **Program Meetings** | link → Program Meetings | Connecting Field: Links program to Program Meetings Base |
| **Program Dashboard Link** | link → Program Dashboard | Connecting Field: Connects Program Documents Associated to this Program. |
| **Program Documents Link** | link → Program Documents | Linked Program documents to this program. Distinct from Program Dashboard, which holds school-facing resources. |
| **Vendor Payments** | link → Vendor Payments | Linked Payment requests raised to Finance for this program's vendors. |
| **School Invoices** | link → Invoices | Linked Invoices issued to the school for this program. |
| **Allocations** | link → Allocations | Reconciled expenses linked to this program. |
| **Transactions** | link → Transactions | Transactions tagged directly to this program. |

## Currency

| Field | Type | Description |
|---|---|---|
| **School's Local Currency** | lookup | Reference field only to determine the currency expected to present the prices for the school. |
| **School's Currency Exchange Rate to USD** | lookup | Exchange rate for the school's billing currency, pulled from the School record. |
| **Currency** | lookup | Local currency of the destination country, pulled through Destination. Distinct from the school's billing currency. |
| **Program Currency Exchange Rate to USD** | lookup | Exchange rate for the destination's local currency, pulled through Destination. |

## Revenue & pricing

| Field | Type | Description |
|---|---|---|
| **Final Land Price Student in USD** | lookup | Cost per student determined by the Pricing Tier ranges set by Finance and negotiated with the school.<br><br>The price is dynamic depending on the SOT Number of Students set for the program. |
| **Final Land Price Student in Local Currency** | formula | Final land price per student converted into the school's billing currency. |
| **Flight Estimate Per Person** | lookup | Per-student flight price, pulled from the active Program Pricing Tier. |
| **Estimated Total Revenue** | formula | Calculation of set Land Price Per Student multiplied by Number of Students SOT. |

## Deadlines & refund dates

Each pair works the same way: enter a number of days in the "Days Prior for…" field, and the matching date field counts back from Program Start Date.

| Field | Type | Description |
|---|---|---|
| **Days Prior for 100% Refund Rate** | number | Days before start until which a full refund is available. |
| **100% Refund Rate Date** | formula | Calculates the date for 100% refund eligibility by subtracting days from the program start date. |
| **Days Prior for 50% Refund Rate** | number | Days before start until which a half refund is available. |
| **50% Refund Rate Date** | formula | Calculates the date for 50% refund eligibility by subtracting days from the program start date. |
| **Days Prior for Deposits** | number | Days before start that the deposit is due. |
| **Date For Deposit** | formula | Calculates the deposit due date by subtracting the specified number of days from the program start date. |
| **Days Prior for Balance Payment** | number | Days before start that the remaining balance is due. |
| **Balance Payment Date** | formula | Balance due date, counted back from Program Start Date. |
| **Days Prior for Confirmed Flights** | number | Days before start by which flights must be confirmed. |
| **Confirmed Flights Date** | formula | Flight confirmation deadline, counted back from Program Start Date. |
| **Days Prior for Registration Deadline** | number | Days before start that registration closes. |
| **Registration Deadline Date** | formula | Registration close date, counted back from Program Start Date. |

## Costs — Budget version (from HBH)

| Field | Type | Description |
|---|---|---|
| **Budget \| USD Total** | rollup | Sum of the total costs in the HBH for the Budget version. |
| **Budget \| Accommodations** | rollup | Sum of the Accommodations costs in the HBH for the Budget version. |
| **Budget \| Meals** | rollup | Sum of the Meals costs in the HBH for the Budget version. |
| **Budget \| Transportation** | rollup | Sum of the Transportation costs in the HBH for the Budget version. |
| **Budget \| Activities** | rollup | Sum of the Activities costs in the HBH for the Budget version. |
| **Budget \| Internal Flights** | rollup | Sum of the Internal Flights costs in the HBH for the Budget version. |
| **Budget \| Other** | rollup | Sum of the Other costs in the HBH for the Budget version. |
| **Budget \| Flights** | rollup | Sum of all costs associated to the program in terms of Flights in the Budget version that should match the I&B Sheet. |

## Costs — Operations Budget version (from HBH)

| Field | Type | Description |
|---|---|---|
| **Operations Budget \| USD Total** | rollup | Sum of the total costs in the HBH for the Quote version. |
| **Operations Budget \| Accommodations** | rollup | Sum of the Accommodation costs in the HBH for the Quote version. |
| **Operations Budget \| Meals** | rollup | Sum of the Meals costs in the HBH for the Quote version. |
| **Operations Budget \| Transportation** | rollup | Sum of the Transportation costs in the HBH for the Quote version. |
| **Operations Budget \| Activities** | rollup | Sum of the Activities costs in the HBH for the Quote version. |
| **Operations Budget \| Internal Flights** | rollup | Sum of the Internal Flights costs in the HBH for the Quote version. |
| **Operations Budget \| Other** | rollup | Sum of the Other costs in the HBH for the Quote version. |

## Costs — Closing version (from HBH)

| Field | Type | Description |
|---|---|---|
| **Closing \| USD Total** | rollup | Sum of the total costs in the HBH for the Execution version. |
| **Closing \| Accommodations** | rollup | Final Accommodations spend in the HBH for the Executed version. |
| **Closing \| Meals** | rollup | Final Meals spend in the HBH for the Executed version. |
| **Closing \| Transportation** | rollup | Final Transportation spend in the HBH for the Executed version. |
| **Closing \| Activities** | rollup | Final Activities spend in the HBH for the Executed version. |
| **Closing \| Internal Flights** | rollup | Final Internal Flights spend in the HBH for the Executed version. |
| **Closing \| Other** | rollup | Final Other-category spend in the HBH for the Executed version. |
| **Closing \| Flights** | rollup | Final international Flights spend in the HBH for the Executed version. |

## Costs — Quoted Total (per category)

Actual quoted or paid cost per category, taken from the Quoted Total Cost USD field on HBH Blocks rather than the forecast calculation.

| Field | Type |
|---|---|
| **Quoted Total Cost \| USD Total** | rollup |
| **Quoted Total Cost \| Accommodations** | rollup |
| **Quoted Total Cost \| Meals** | rollup |
| **Quoted Total Cost \| Transportation** | rollup |
| **Quoted Total Cost \| Activities** | rollup |
| **Quoted Total Cost \| Internal Flights** | rollup |
| **Quoted Total Cost \| Flights** | rollup |
| **Quoted Total Cost \| Tour Operator** | rollup |
| **Quoted Total Cost \| Other** | rollup |

## Costs — Associated Costs (non-HBH), by version

| Field | Type | Description |
|---|---|---|
| **Budget \| AC Total USD** | rollup | Total Associated Costs for the Budget version. |
| **Budget \| AC Preparation Days** | rollup | Sum of the Preparation Days categorized costs from the Associated Costs for the Budget version. |
| **Budget \| AC Essentials** | rollup | Sum of the Essentials categorized costs from the Associated Costs for the Budget version. |
| **Budget \| AC Staffing** | rollup | Sum of the Staffing categorized costs from the Associated Costs for the Budget version. |
| **Budget \| AC Other** | rollup | Sum of the Other categorized costs from the Associated Costs for the Budget version. |
| **Forecast \| AC Total USD** | rollup | Total Associated Costs for the Forecast version. |
| **Forecast \| AC Preparation Days** | rollup | Preparation Days costs from Associated Costs, Forecast version. |
| **Forecast \| AC Essentials** | rollup | Essentials costs from Associated Costs, Forecast version. |
| **Forecast \| AC Staffing** | rollup | Staffing costs from Associated Costs, Forecast version. |
| **Forecast \| AC Other** | rollup | Other costs from Associated Costs, Forecast version. |
| **Closing \| AC Total USD** | rollup | Total Associated Costs for the Executed version. |
| **Closing \| AC Preparation Days** | rollup | Sum of the Preparation Days categorized costs from the Associated Costs for the Execution version. |
| **Closing \| AC Essentials** | rollup | Sum of the Essential categorized costs from the Associated Costs for the Execution version. |
| **Closing \| AC Staffing** | rollup | Sum of the Staffing categorized costs from the Associated Costs for the Executed version. |
| **Closing \| AC Other** | rollup | Other categorized costs from Associated Costs, Executed version. |

## Finance — Income

| Field | Type | Description |
|---|---|---|
| **FIN \| Income Ground Program** | formula | Expected ground income: Final Land Price Student in USD x Number of Students \| SOT. |
| **FIN \| Income Flights Estimate** | formula | Expected flights income: Flight Estimate Per Person x Number of Students \| SOT. |
| **FIN \| Additional Ground Invoiced** | rollup | Sum of linked School Invoices where Categories is NOT Flights. |
| **FIN \| Additional Flights Invoiced** | rollup | Sum of linked School Invoices where Categories IS Flights. |
| **FIN \| Program Income** | formula | Total expected income: Income Ground Program + Income Flights Estimate + Additional Ground Invoiced + Additional Flights Invoiced. |
| **FIN \| Ground Income** | formula | Ground share of expected income: Income Ground Program + Additional Ground Invoiced. Used for Ground margins. |
| **FIN \| Flights Income** | formula | Flights share of expected income: Income Flights Estimate + Additional Flights Invoiced. Used for Flights margins. |
| **FIN \| Total Invoiced** | rollup | Sum of Invoiced Amount across ALL linked School Invoices. |
| **FIN \| Total Paid** | rollup | Sum of Invoiced Amount for linked School Invoices with Invoice Payment Status = Complete. |
| **FIN \| Unpaid Invoices Total** | rollup | Sum of Invoiced Amount for linked School Invoices with Invoice Payment Status = Sent & Pending. |
| **FIN \| Invoice Pending** | formula | Expected income not yet invoiced: Program Income - Total Invoiced. |
| **FIN \| School Unpaid Balance** | formula | Expected income not yet paid: Program Income - Total Paid. |

## Finance — Performance by category

Two comparisons per category. **Forecast Performance** measures the Operations Budget / Forecast against the original Budget. **Performance** measures Closing against Budget. `$` is the variance in dollars, `%` the same as a percentage.

| Field | Type | Description |
|---|---|---|
| **FIN \| Accommodations Forecast Performance $** | formula | Forecast variance in USD for Accommodations. |
| **FIN \| Accommodations Forecast Performance %** | formula | Forecast variance as a percentage for Accommodations. |
| **FIN \| Accommodations Performance $** | formula | Closing variance in USD for Accommodations. |
| **FIN \| Accommodations Performance %** | formula | Closing variance as a percentage for Accommodations. |
| **FIN \| Activities Forecast Performance $** | formula | Forecast variance in USD for Activities. |
| **FIN \| Activities Forecast Performance %** | formula | Forecast variance as a percentage for Activities. |
| **FIN \| Activities Performance $** | formula | Closing variance in USD for Activities. |
| **FIN \| Activities Performance %** | formula | Closing variance as a percentage for Activities. |
| **FIN \| Transportation Forecast Performance $** | formula | Forecast variance in USD for Transportation. |
| **FIN \| Transportation Forecast Performance %** | formula | Forecast variance as a percentage for Transportation. |
| **FIN \| Transportation Performance $** | formula | Closing variance in USD for Transportation. |
| **FIN \| Transportation Performance %** | formula | Closing variance as a percentage for Transportation. |
| **FIN \| Meals Forecast Performance $** | formula | Forecast variance in USD for Meals. |
| **FIN \| Meals Forecast Performance %** | formula | Forecast variance as a percentage for Meals. |
| **FIN \| Meals Performance $** | formula | Closing variance in USD for Meals. |
| **FIN \| Meals Performance %** | formula | Closing variance as a percentage for Meals. |
| **FIN \| Internal Flights Forecast Performance $** | formula | Forecast variance in USD for Internal Flights. |
| **FIN \| Internal Flights Forecast Performance %** | formula | Forecast variance as a percentage for Internal Flights. |
| **FIN \| Internal Flights Performance $** | formula | Closing variance in USD for Internal Flights. |
| **FIN \| Internal Flights Performance %** | formula | Closing variance as a percentage for Internal Flights. |
| **FIN \| Flights Performance $** | formula | Closing variance in USD for international Flights. |
| **FIN \| Flights Performance %** | formula | Closing variance as a percentage for international Flights. |
| **FIN \| Other Forecast Performance $** | formula | Forecast variance in USD for Other HBH costs. |
| **FIN \| Other Forecast Performance %** | formula | Forecast variance as a percentage for Other HBH costs. |
| **FIN \| Other Performance $** | formula | Closing variance in USD for Other HBH costs. |
| **FIN \| Other Performance %** | formula | Closing variance as a percentage for Other HBH costs. |
| **FIN \| Preparation Days Forecast Performance $** | formula | Forecast variance in USD for Preparation Days. |
| **FIN \| Preparation Days Forecast Performance %** | formula | Forecast variance as a percentage for Preparation Days. |
| **FIN \| Preparation Days Performance $** | formula | Closing variance in USD for Preparation Days. |
| **FIN \| Preparation Days Performance %** | formula | Closing variance as a percentage for Preparation Days. |
| **FIN \| Essentials Forecast Performance $** | formula | Forecast variance in USD for Essentials. |
| **FIN \| Essentials Forecast Performance %** | formula | Forecast variance as a percentage for Essentials. |
| **FIN \| Essentials Performance $** | formula | Closing variance in USD for Essentials. |
| **FIN \| Essentials Performance %** | formula | Closing variance as a percentage for Essentials. |
| **FIN \| Staffing Forecast Performance $** | formula | Forecast variance in USD for Staffing. |
| **FIN \| Staffing Forecast Performance %** | formula | Forecast variance as a percentage for Staffing. |
| **FIN \| Staffing Performance $** | formula | Closing variance in USD for Staffing. |
| **FIN \| Staffing Performance %** | formula | Closing variance as a percentage for Staffing. |
| **FIN \| Other AC Forecast Performance $** | formula | Forecast variance in USD for Other Associated Costs. |
| **FIN \| Other AC Forecast Performance %** | formula | Forecast variance as a percentage for Other Associated Costs. |
| **FIN \| Other AC Performance $** | formula | Closing variance in USD for Other Associated Costs. |
| **FIN \| Other AC Performance %** | formula | Closing variance as a percentage for Other Associated Costs. |
| **Finance Closing Comments** | richText | Finance's written notes when closing out the program's books. |

## Finance — Reconciled actuals (by Chart of Accounts)

Actual reconciled spend pulled from Allocations, one rollup per Chart of Accounts code.

| Field | COA filter |
|---|---|
| **FIN \| Reconciled Transport (Air)** | 5110 Program Expense – Transport (Air) |
| **FIN \| Reconciled Accommodations** | 5210 Program Expense – Accommodations |
| **FIN \| Reconciled Food – Water – Snacks** | 5220 Program Expense – Food – Water – Snacks |
| **FIN \| Reconciled Transportation** | 5230 Program Expense – Transportation |
| **FIN \| Reconciled Activities** | 5240 Program Expense – Activities |
| **FIN \| Reconciled Internal Flights** | 5250 Program Expense – Internal Flights |
| **FIN \| Reconciled Other Travel Logistics** | 5260 Program Expense – Other Travel Logistics |
| **FIN \| Reconciled Staff Salaries** | 5310 Program Expense – Staff Salaries |
| **FIN \| Reconciled Staff Logistics** | 5320 Program Expense – Staff Logistics |
| **FIN \| Reconciled Staff Flights** | 5330 Program Expense – Staff Flights |
| **FIN \| Reconciled Staff Insurance** | 5340 Program Expense – Staff Insurance |
| **FIN \| Reconciled Staff Training** | 5350 Program Expense – Staff Training |
| **FIN \| Reconciled Other Staff Related** | 5360 Program Expense – Other Staff Related |
| **FIN \| Reconciled Communications** | 5510 Program Expense – Communications |
| **FIN \| Reconciled Supplies** | 5520 Program Expense – Supplies |
| **FIN \| Reconciled Medical Supplies** | 5530 Program Expense – Medical Supplies |
| **FIN \| Reconciled Participant Insurance** | 5540 Program Expense – Participant Insurance |
| **FIN \| Reconciled Staff SWAG** | 5610 Program Expense – Staff SWAG |
| **FIN \| Reconciled Participant SWAG** | 5620 Program Expense – Participant SWAG |
| **FIN \| Reconciled Incidentals** | 5710 Program Expense – Incidentals |
| **FIN \| Reconciled Non-Refundable Vendor Payments** | 5720 Program Expense – Non-Refundable Vendor Payments |

## FINOPS — Field cash

Tracks the cash Finance sends to field staff to spend on the ground.

| Field | Type | Description |
|---|---|---|
| **FINOPS \| Total Cash Needed** | currency | Input the Total Amount of Cash in USD for Finance to send over to the staff for the Program. Include Emergency Funds here or add an HBH Block with the amount. |
| **FINOPS \| Total Cash Sent Method** | singleSelect | Method used to send funds for Field Cash to Staff.<br>Options: Gusto · Wire Transfer · Zelle · Revolut · DMC |
| **FINOPS \| Field Cash Received** | checkbox | Checked once the field staff confirm the cash arrived. |
| **FINOPS \| Staff Assigned For Field Cash** | lookup | The staff assignment receiving the field cash. |
| **FINOPS \| Staff Arrival Date** | lookup | Staff's first full preparation day, pulled from Staff Assignments. Anchors the cash deadline. |
| **FINOPS \| Cash Deadline** | formula | Calculates the date 10 working days before the FINOPS Staff Arrival Date. |

## Automation flags

> Do not delete. Automations depend on these.

| Field | Type | Description |
|---|---|---|
| **Executed version created?** | checkbox | Check Box for Executed Version Automation. DO NOT DELETE. |
| **Associated costs executed version created?** | checkbox | Marks that the Executed version of Associated Costs has been generated. Automation flag — DO NOT DELETE. |

---

## Related tables

- **Schools**, **Destinations**, **Countries** — where and who
- **ENVOYS HQ** — the five POD leads plus the Blackouts lead
- **I&B Requests**, **Program Pricing Tiers** — proposal and pricing history
- **Program Versions** → **HBH Blocks**, **Associated Costs** — cost snapshots
- **HBH Days** — the day-level itinerary skeleton
- **School Participant Profiles**, **School Faculty & Staff Directory** — travellers and school contacts
- **Program Field Staff Assignments** → **Field Staff Profiles** — staffing
- **EM QC Checks**, **OPS QC Checks** — readiness checklists
- **Program Meetings**, **Program Dashboard**, **Program Documents** — coordination and resources
- **Invoices**, **Vendor Payments**, **Allocations**, **Transactions** — money in and out
