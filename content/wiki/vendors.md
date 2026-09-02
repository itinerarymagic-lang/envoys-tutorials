# Vendors

**Primary field:** Vendor Name

Directory of all vendors used across programs — hotels, transport providers, activity operators, restaurants, and DMCs. Financial details (bank info, currency, payment method) are stored here and pulled through to Vendor Payment requests. Vendor Listings (priced line items) link back to this table.

## Fields

| Field | Type | Description |
|---|---|---|
| **Vendor Name** | singleLineText | Full vendor name as it appears on invoices and contracts. Primary field. |
| **Id** | formula | Returns the Airtable Record ID. Used internally for cross-table references. |
| **Category** | link → HBH Categories | HBH category (Accommodations, Meals, Transportation, Activities, etc.). Used to filter vendors by type. |
| **Destinations** | link → Destinations | The destination(s) where this vendor operates. |
| **Country** | lookup | Country pulled from the linked Destination. |
| **Country Code** | lookup | Dialing code pulled from the linked Destination's country. |
| **Full Address** | richText | Complete physical address of the vendor. |
| **Google Maps Location Link** | url | Google Maps link to the vendor's location. |
| **Location** | link → Locations | The specific location record for this vendor's site. |
| **Contact Name** | singleLineText | Primary contact person at this vendor. |
| **Email** | email | Primary contact email. |
| **Phone Number** | phoneNumber | Phone number excluding country code. |
| **Website** | url | Vendor website. |
| **Payment Information Additional Notes** | richText | Any special instructions for sending payment to this vendor (intermediary banks, reference fields, preferred method). |
| **HBH Link** | link → HBH Blocks | HBH Blocks where this vendor is booked. |
| **Programs (Link)** | lookup | Programs linked through the HBH Blocks. Reference only. |
| **Vendor Notes** | richText | General working notes on this vendor — relationship history, quirks, preferred contacts. |
| **Vendor Files** | multipleAttachments | Contracts, MOUs, or other documents related to this vendor. |
| **Vendor Payments** | link → Vendor Payments | Payment requests made to this vendor. |
| **Vendor Debrief Notes** | multilineText | Post-program debrief notes on this vendor's performance. Updated after each program. |
| **Vendor Status** | singleSelect | Whether this vendor is currently usable.<br>Options: Active · Inactive · Avoid |
| **Vendor Listings** | link → Vendor Listings | Priced line items (quotes) for this vendor's services. |
| **Vendor Review Timestamp** | lastModifiedTime | Last time the Vendor Debrief Notes or Vendor Status changed. Tracks when the vendor was last reviewed. |
| **Timestamp \| Vendor Payment Information Update** | lastModifiedTime | Last time any financial detail field changed. Pulled through to Vendor Payments so Finance can see if banking info is stale. |
| **Beneficiary Name** | singleLineText | Legal name on the vendor's bank account. Must match exactly for wire transfers. |
| **Country (Financial Details)** | link → Countries | Country where the vendor's bank account is held. |
| **Currency (Financial Details)** | link → Currencies | Currency the vendor accepts for payment. |
| **Address (Financial Details)** | richText | Bank or registered address for wire transfer purposes. |
| **Account Number** | singleLineText | Bank account number. |
| **Account Type** | singleSelect | Type of bank account.<br>Options: Checkings · Savings |
| **Routing Number** | singleLineText | US ACH routing number (US accounts only). |
| **SWIFT/BIC Code** | singleLineText | SWIFT or BIC code for international wire transfers. |
| **IBAN Number** | singleLineText | IBAN number (European and some international accounts). |
| **Finance Information Update** | lastModifiedTime | Last time any of the financial detail fields (Beneficiary Name, Account Number, SWIFT, etc.) changed. |
| **Vendor Rating** | singleSelect | Overall quality rating based on program experience.<br>Options: Highlight · Recommended · Acceptable · Caution · Avoid · NA |
| **Price Range** | singleSelect | Relative cost tier for this vendor.<br>Options: $ · $$ · $$$ · $$$$ · $$$$$ · NA |
| **Vendor Registered In Bank** | checkbox | Checked once Finance has registered this vendor's banking details in the company's bank portal. Required before the first wire transfer. |
| **Vendor Registration Timestamp** | lastModifiedTime | When the Vendor Registered In Bank checkbox was last changed. |

## Related tables

- **Destinations**, **Locations** — where the vendor operates
- **HBH Blocks** — where the vendor is booked in itineraries
- **Vendor Payments** — payment requests to this vendor
- **Vendor Listings** — priced service items for this vendor
- **HBH Categories** — the service type this vendor provides

## Notes

- Financial detail fields (Beneficiary Name through IBAN) are pulled through to Vendor Payment records automatically — keep them current.
- `Vendor Registered In Bank` must be checked before Finance can process the first payment. Flag new vendors for Finance review before booking them.
- `Scouting` and `Pre-Ops Costs` are orphaned `singleLineText` fields — they cannot be linked and are safe to remove from the UI.
