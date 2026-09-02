# OPS QC Checks

**Primary field:** Name

> STILL BEING BUILT.

Operations quality-control checklist per program focused on bookings, vendors, and logistics. Each check field uses a consistent set of status options: Clear · Flag · Flag Cleared · Pending · N/A · Post-Program · Handled by Staff.

## Fields

### Status & program link

| Field | Type | Description |
|---|---|---|
| **Name** | formula | Program Name + OPS QC Checks Status (Pending or Complete). Primary display identifier. |
| **OPS QC Checks Status** | singleSelect | Manual overall status set by the OPS lead after reviewing all checks.<br>Options: Checks Pending · Checks Complete · Checks Pending \| URGENT |
| **Programs** | link → Programs | The Program this checklist belongs to. |
| **Program Start Date** | lookup | Program Start Date from the linked Program. |
| **Program Name** | lookup | Program Name from the linked Program. |
| **Due Date** | formula | 15 days before Program Start Date — the target completion date for all OPS QC checks. |
| **EM QC Checks** | link → EM QC Checks | The linked EM QC Checks record for this program. |

### General

| Field | Type | Description |
|---|---|---|
| **Dates & No. of Travelers Match with OPS Support Program** | singleSelect | Confirm that the OPS Support vendor has the right dates and traveler counts. |
| **OPS Support final payment made** | singleSelect | Whether final payment to the OPS Support provider is complete. |
| **OPS Support Contract or Final Voucher Saved in FPF** | singleSelect | Contract or voucher filed in the Field Program Folder. |
| **All Booking Fields 'Booking Made', 'No Booking Needed' or 'Field Booking Needed'** | singleSelect | Confirms all HBH Blocks have a resolved booking status. |
| **Petty Cash Requested to Finance** | singleSelect | Whether petty cash has been requested from Finance for field expenses. |
| **Expense Sheet Saved in FPF** | singleSelect | Expense sheet filed in FPF. |
| **Vendor Contact List Saved in FPF** | singleSelect | Vendor contact list filed in FPF. |
| **Printable HBH Saved in FPF** | singleSelect | Printable HBH document filed in FPF. |
| **OPS QC Checks Notes** | richText | General notes on OPS QC for this program. |
| **OPS Support Notes** | multilineText | Notes specific to the OPS Support provider relationship. |
| **General HBH & FPF Notes** | multilineText | Any additional HBH or FPF-related notes. |
| **Notes on QC Checks** | richText | Overall QC notes that don't fit the specific subsections. |

### Hotels

| Field | Description |
|---|---|
| **Hotel Booking or Contract Saved in FPF** | Hotel booking confirmation or contract filed. |
| **Hotel Contract Dates Match HBH** | Dates in hotel contract match HBH itinerary. |
| **Breakfast Included in Hotels or Breakfast Added to Staff Budget** | Breakfast arrangement confirmed. |
| **Dietary Restrictions Shared with Hotel for Breakfast** | Hotel notified of participant dietary needs. |
| **Room Distribution Matches Group Size and Gender Distribution** | Room allocation verified against participant list. |
| **Rooming List with Traveler Names Sent to Hotel** | Named rooming list sent. |
| **Rooming List Saved in FPF** | Rooming list filed in FPF. |
| **Hotel Price Added to HBH** | Final hotel price entered in HBH Blocks. |
| **Final Payment Made to Hotel** | Hotel payment confirmed. |
| **Hotel Quality Check Completed** | Location, reviews, and rating verified. |
| **Booking.com Reservations Updated with Group Names** | Group names added to online reservations. |
| **Hotel Vendor Contact Saved in Database** | Vendor record created/updated in Airtable. |
| **Hotel Vendor Linked to HBH** | Hotel linked in the relevant HBH Blocks. |
| **Meeting Spaces Confirmed for Activities** | Any required meeting/activity spaces at hotel confirmed. |
| **Meeting Spaces Confirmed in Hotel** | Meeting space booked and confirmed with hotel. |
| **Night Watchers Booked and Payment Completed** | Night watch service arranged if needed. |
| **Nurse Booked and Payment Completed** | Nurse arranged if required by the program. |

### Transportation

| Field | Description |
|---|---|
| **Transport Vendor Contract Dates Match HBH** | Transport contract dates align with itinerary. |
| **General Envoys Schedule Matches HBH Itinerary (Including Times)** | Full schedule including times is consistent. |
| **Vendor Booked Itinerary Matches HBH** | Vendor's booking confirmation matches HBH. |
| **Bus Size Works for Group Size** | Vehicle capacity is appropriate for group. |
| **Transportation Price Added to HBH** | Final transport price in HBH Blocks. |
| **Final Payment Made to Transportation Provider** | Transport payment confirmed. |
| **Transportation Vendor Contact Saved in Database** | Vendor record created/updated. |
| **Transportation Vendor Linked to HBH** | Transport vendor linked in HBH Blocks. |
| **Hotel Rooms Booked for Bus Drivers** | Driver accommodation arranged if needed. |
| **COI or MOU Saved in Folder** | Certificate of Insurance or MOU filed. |

### Metro / Transit

| Field | Description |
|---|---|
| **Metro Cards Purchased** | Metro cards procured. |
| **Metro Card Delivery or Pick Up Arranged** | Distribution logistics confirmed. |

### Trains

| Field | Description |
|---|---|
| **Ticket Dates Match HBH** | Train ticket dates align with itinerary. |
| **One Ticket per Traveler Available** | Correct number of tickets secured. |
| **Train Numbers Added to HBH** | Train route numbers in HBH Blocks. |
| **Final Train Price Added to HBH** | Final price in HBH Blocks. |
| **Name Check Completed** | Passenger names on tickets verified against TLT. |
| **Train Vendor Contact Saved in App** | Vendor record created/updated. |

### Activities

| Field | Description |
|---|---|
| **Activity Booking Confirmation Document Saved in FPF** | Booking confirmation filed. |
| **Dates in Activity Booking Confirmations Match HBH** | Activity dates match itinerary. |
| **Times in Activity Booking Confirmations Match HBH** | Activity times match itinerary. |
| **Final Activity Price Added to HBH** | Final price in HBH Blocks. |
| **Final Payment Made to Vendor** | Activity vendor payment confirmed. |
| **Vendor Contact Saved in Database** | Vendor record created/updated. |
| **One Ticket per Traveler Available** | Correct number of passes/tickets. |
| **Core Activity Description Saved in FPF** | Activity description document filed. |
| **Activity MOU Signed and Saved** | MOU signed and filed. |

### Restaurants

| Field | Description |
|---|---|
| **Restaurant Booking Confirmation Saved in FPF** | Booking confirmation filed. |
| **Dates in Restaurant Booking Confirmations Match HBH** | Dates align with itinerary. |
| **Times in Restaurant Booking Confirmations Match HBH** | Times align with itinerary. |
| **Numbers in Confirmation Match Total Travelers** | Reservation covers the full group. |
| **Final Payment Made to Restaurant** | Restaurant payment confirmed. |
| **Dietary Restrictions and Allergies Shared with Vendor** | Dietary needs communicated. |
| **Final Meal Price Added to HBH** | Final price in HBH Blocks (shared field with Activities). |
| **If Booked by Staff: Budget Document Shared with Staff** | Budget shared if staff is booking. |
| **If Booked by DMC: Restaurant Names and Menu Selection Received and Saved in FPF** | DMC meal plan documented. |
| **If Booked by RM: Meal Plan Document Completed and Saved in FPF** | RM meal plan filed. |
| **Meals - General Notes** | General meal notes. |
| **Meals - Specific Notes** | Specific meal or vendor notes. |

## Related tables

- **Programs** — one OPS QC record per program
- **EM QC Checks** — linked for cross-reference; Stage 5 of EM QC reads the OPS QC status

## Notes

- One record is created per program, automatically. Do not create or delete OPS QC records manually.
- All check fields use the same options: Unchecked · Clear · Flag · Pending · N/A · Flag Cleared · Post-Program · Handled by Staff. "Flag" means there's an issue to resolve before launch. "Flag Cleared" means the flag was addressed.
- The overall `OPS QC Checks Status` is set manually by the OPS lead — it is not a formula. Set it to "Checks Complete" only after reviewing all subsections.
- The Due Date (15 days before program start) is a target, not a hard lock — but it anchors the Stage 5 Program Launch deadline in EM QC.
