# Vendor Listings

**Primary field:** Vendor Listing ID

Priced line items tied to specific vendors — individual quotes or standing rates for a service (e.g. "Double Room per night", "City Tour for 30 pax", "Airport Transfer"). Used as a reference library of what vendors charge, independent of any specific program booking.

## Fields

| Field | Type | Description |
|---|---|---|
| **Vendor Listing ID** | formula | Auto-generated identifier combining Category, Country Code, Destination, and an autonumber. Primary field. |
| **Item Name** | singleLineText | Name of the specific service or product being priced (e.g. "Double Occupancy Room", "Half-Day City Tour"). |
| **Unit Final Cost (USD)** | currency | Quoted price per unit in USD. |
| **Quote Date** | lastModifiedTime | Last time the Unit Final Cost was changed — serves as a proxy for when this quote was last updated. |
| **Category** | singleSelect | Service type for this line item.<br>Options: Accommodations · Transportation · Meals · Activities · Other · All Inclusive |
| **Item Description** | multilineText | What exactly is included in this listing — scope, inclusions, exclusions, valid conditions. |
| **Item Notes** | multilineText | Working notes on this listing — seasonality, validity period, booking conditions, vendor contact for this rate. |
| **Vendor** | link → Vendors | The vendor this listing belongs to. |
| **Vendor Name** | lookup | Vendor name pulled from the linked Vendor. |
| **Destinations** | lookup | Destination(s) pulled from the linked Vendor. |
| **Location** | lookup | Location pulled from the linked Vendor. |
| **Country Code** | lookup | Country code pulled from the linked Vendor. Used in the Listing ID. |
| **Identifier** | autoNumber | Auto-incrementing number. Used in the Vendor Listing ID formula. |

## Related tables

- **Vendors** — each listing belongs to one vendor
- **Destinations**, **Locations** — inherited from the vendor for context

## Notes

- Vendor Listings are a **rate library**, not booking records. They are not directly linked to HBH Blocks or Programs — they are reference documents for OPS when building or pricing itineraries.
- The Quote Date updates automatically whenever the Unit Final Cost changes — always check it before using a rate, as vendor pricing drifts over time.
