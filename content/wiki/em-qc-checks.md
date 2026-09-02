# EM QC Checks

**Primary field:** EM Checks Status

Experience Management quality-control checklist per program. One record per program, created automatically when the program record is created. The primary field is a formula that rolls up the five stage formulas and tells you exactly which stage has pending items.

The checklist is divided into six sequential stages: LOI Registration Period → Program Confirmed Minimums Met → Numbers Finalized → Registration Complete → Program Launch → Post Program. Each stage has its own status formula that returns ✅ (all done) or Pending.

## Fields

### Status formulas

| Field | Description |
|---|---|
| **EM Checks Status** | Overall status — shows the first stage that still has pending items, or "All Stages Complete". |
| **LOI Registration Period Status** | Stage 1 complete when all Stage 1 checklist items are checked. |
| **Program Confirmed: Minimums Met Status** | Stage 2 complete when all Stage 2 items are met. |
| **Program Confirmed: Numbers Finalized Status** | Stage 3 complete when all Stage 3 items are met. |
| **Program Confirmed: Registration Complete Status** | Stage 4 complete when all Stage 4 items are met. |
| **Program Launch Status** | Stage 5 complete when all QC and email steps are done. |
| **Post Program Status** | Stage 6 complete when post-program meetings and survey are done. |

### Program link & lookups

| Field | Type | Description |
|---|---|---|
| **Programs** | link → Programs | The Program this QC checklist belongs to. |
| **Program Start Date** | lookup | Program Start Date from the linked Program. |
| **School Flight Departure** | lookup | School Flight Departure from the linked Program. |
| **School Flight Return** | lookup | School Flight Return from the linked Program. |
| **POD \| PT Lead** | lookup | PT Lead from the linked Program. |
| **POD \| OPS Lead** | lookup | OPS Lead from the linked Program. |
| **POD \| S&R Lead** | lookup | S&R Lead from the linked Program. |
| **POD \| EM Lead** | lookup | EM Lead from the linked Program. |
| **EM Lead** | lookup | EM Lead pulled for display. |
| **EM Lead Assigned Status** | singleSelect | Whether an EM Lead has been confirmed for this program.<br>Options: Checks Pending · Checks Complete · Checks Pending \| URGENT |
| **Program Notes** | lookup | Program Notes Link from the linked Program. |
| **Days until program start date** | lookup | Days countdown from the linked Program. |
| **Jotform Registration Link** | lookup | Registration link from the linked Program. |
| **Program Status** | lookup | Program Status from the linked Program. |
| **School Invoices** | lookup | School Invoices from the linked Program. |
| **OPS QC Checks** | link → OPS QC Checks | The linked OPS QC Checks record for this program. |

### General

| Field | Type | Description |
|---|---|---|
| **Handover Status** | singleSelect | PT → EM handover completion status.<br>Options: Complete · Pending |
| **Link to Program Dashboard** | url | Direct link to the program's school-facing dashboard. |
| **EM General Notes** | richText | EM's working notes for the program — not stage-specific. |
| **EM Deadlines** | richText | Key upcoming deadlines for EM to track for this program. |
| **Program Website** | url | Link to the program's public-facing website (Canva or equivalent). |
| **LOI Email** | email | LOI communication email address. |
| **Payment Method** | singleSelect | How the school is paying for the program.<br>Options: Invoice · Payment Links · Both · TBD |
| **Financial Aid** | singleSelect | Whether any participants in this program have financial aid.<br>Options: Yes · No · TBD |

### Stage 1 — LOI Registration Period

| Field | Type | Description |
|---|---|---|
| **Program Dashboard Sent to School** | checkbox | Check once the program dashboard has been shared with the school. |
| **Program Website Sent to School** | checkbox | Check once the program website has been shared. |
| **Optional Check-In Meeting w/ School** | checkbox | Check if the optional check-in meeting has been held or confirmed N/A. |
| **Orientation Meeting** | checkbox | Check once the orientation meeting has been held. |
| **Final Flight Information in Envault/Dashboard Share with School** | checkbox | Check once final flight info has been shared with the school. |

### Stage 2 — Program Confirmed: Minimums Met

| Field | Type | Description |
|---|---|---|
| **Hotel Information Document Sent to School** | checkbox | Check once the hotel information document has been sent. |
| **Rooming List** | singleSelect | Rooming list status.<br>Options: Pending · Sent to School · Completed |
| **Packing List** | singleSelect | Packing list status.<br>Options: Pending · Sent to School and Linked in Website · N/A |
| **Contract** | singleSelect | Contract status.<br>Options: Pending · Requested to Legal · Sent to School for Legal · Signed by School & Envoys \| Placed in FPF |
| **Pre Departure Learning Resources** | singleSelect | Pre-departure resources status.<br>Options: Pending · PT Lead Pending · Sent to School and Linked in Website · N/A |
| **Flight Information** | singleSelect | Flight information document status.<br>Options: Pending · Final Flight Document Sent by PT · TLT Ready and Sent to Flight Team · FID Ready and Sent to School · N/A |
| **Status on Payment** | singleSelect | Invoice and payment status for the program.<br>Options: Pending · Invoices Requested · Invoices Sent to School · Deposit Paid · Balance Paid · Additional Paid · Payment Completed · Payment via Website |
| **Deposit Invoice** | singleSelect | Deposit invoice status.<br>Options: Pending · Sent to School · Paid · N/A |
| **Travel Policies Created and Added to Dashboard** | checkbox | Check once travel policies are live on the dashboard. |

### Stage 3 — Program Confirmed: Numbers Finalized

| Field | Type | Description |
|---|---|---|
| **Ticket Issued Document Ready** | singleSelect | Ticket issued document status.<br>Options: Pending · TTL ready and shared with Flights · FIT ready and shared with school · N/A |
| **Balance Invoice** | singleSelect | Balance invoice status.<br>Options: Invoice Pending · Sent to School · Paid · N/A |

### Stage 4 — Program Confirmed: Registration Complete

| Field | Type | Description |
|---|---|---|
| **Basic Information** | singleSelect | Basic participant information collection status.<br>Options: Pending · In Progress · Completed · N/A |
| **Dietary Restrictions** | singleSelect | Dietary restriction information collection status. |
| **Medical Information** | singleSelect | Medical information collection status. |
| **Emergency Contacts** | singleSelect | Emergency contact collection status. |
| **Participant Agreements** | singleSelect | Participant agreement completion status. |
| **Passport Copies** | singleSelect | Passport upload completion status. |
| **Medical RAMP** | singleSelect | Medical RAMP readiness status.<br>Options: Pending · Created and sent to Risk · Medical RAMP Ready |
| **Envoys Staff Confirmed** | singleSelect | Whether field staff assignments are confirmed.<br>Options: Yes · N/A |
| **Envoys Staff Profiles** | singleSelect | Staff profiles shared with school status.<br>Options: Pending · Requested to S&R · Under Creation · Sent to School and Linked · N/A |
| **SWAG** | singleSelect | SWAG delivery status.<br>Options: Pending · Requested · Sent to School · Received by School · N/A |
| **Final HBH Shared with School** | singleSelect | Whether the final HBH has been shared.<br>Options: In Progress · Yes · No · N/A |
| **Program Handover Meeting** | singleSelect | Program handover meeting status.<br>Options: Pending · Scheduled · Held |
| **Team Traveler Meeting** | singleSelect | Team traveling meeting status.<br>Options: Pending · Scheduled · Held |
| **Program's WhatsApp Group** | singleSelect | WhatsApp group setup status.<br>Options: Pending · Faculty, Staff & HQ Lead Added |
| **Global Rescue** | singleSelect | Global Rescue enrollment status.<br>Options: Pending · N/A · Completed and Sent |
| **Travel Policies Complete and Signed** | singleSelect | Whether travel policies have been signed by the school.<br>Options: Yes · No · N/A |
| **Additional Invoice** | singleSelect | Additional invoice status.<br>Options: Pending · Invoice Requested · Sent to School · Paid · N/A |
| **Flight Information Document Sent to School & Linked in Dashboard** | checkbox | Check once flight doc is shared and linked. |
| **TLT Ready and Shared with Flight Team** | checkbox | Check once TLT is prepared and sent. |
| **Field RAMP Ready** | checkbox | Check once the Field RAMP is complete. |
| **Destination Report** | checkbox | Check once the destination report is complete. |
| **Health Safety and Security Manual** | checkbox | Check once the HSSM is complete. |
| **RAMPS** | singleSelect | Overall RAMP status.<br>Options: Pending Medical RAMP · Medical RAMP Sent to Risk and Flight Team · Medical RAMP Ready · RAMPS Ready and Shared w/ Schools |
| **Link to RAMP Folder** | url | Link to the RAMP folder in the FPF. |

### Stage 5 — Program Launch

| Field | Type | Description |
|---|---|---|
| **OPS QC** | singleSelect | OPS QC completion status.<br>Options: Completed · Received w/ Flag · Pending · N/A |
| **S&R QC** | singleSelect | S&R QC completion status. |
| **FINANCE QC** | singleSelect | Finance QC completion status. |
| **Flights/Trains QC** | singleSelect | Flights/Trains QC completion status. |
| **EM QC Email Sent to AllHands** | singleSelect | Whether the EM QC all-clear email has been sent to the all-hands channel.<br>Options: Yes · In Progress · No · N/A |
| **HQ Lead Email Sent to School** | singleSelect | Whether the HQ Lead introduction email has been sent to the school.<br>Options: Yes · In Progress · No · N/A |
| **Regional Management QC** | checkbox | Check once Regional Management QC is complete. |
| **Risk and Staff QC** | checkbox | Check once Risk and Staff QC is complete. |
| **Flights QC** | checkbox | Check once Flights QC is complete. |
| **Check In Meeting (School)** | checkbox | Check once the check-in meeting with the school has been held. |
| **program website updated with latest itinerary (Canva)** | singleSelect | Whether the program website has the final itinerary.<br>Options: Yes · No · N/A |
| **Envoys Photo Album on Website/Dashboard** | singleSelect | Whether the photo album is live and linked.<br>Options: Yes · No · N/A |

### Stage 6 — Post Program

| Field | Type | Description |
|---|---|---|
| **Email to Global Ed with Survey** | singleSelect | Whether the post-program survey email has been sent to Global Ed.<br>Options: Yes · N/A · No |
| **HQ Debrief Meeting** | singleSelect | HQ debrief meeting status.<br>Options: Pending · Scheduled · Held |
| **School Debrief Meeting** | singleSelect | School debrief meeting status.<br>Options: Pending · Scheduled · Held · N/A |

## Related tables

- **Programs** — one EM QC record per program
- **OPS QC Checks** — linked for cross-reference at the QC stage

## Notes

- One record is created per program, automatically. Do not create or delete EM QC records manually.
- The six stage formulas are what drive the `EM Checks Status` rollup on Programs — keep the underlying checkboxes and selects accurate.
- Stage 5 (Program Launch) requires OPS QC, S&R QC, Finance QC, Flights QC, the all-hands email, and the HQ Lead email to all be complete before the formula marks done.
