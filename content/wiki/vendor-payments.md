# Vendor Payments

**Primary field:** Payment Request ID

Finance vendor payment requests. Each record is one payment to one vendor for one program. Financial details (bank account, SWIFT, IBAN) are pulled automatically from the linked Vendor record. A double-entry check (Transfer Amount + Confirm Transfer Amount) catches data entry errors before Finance processes the wire.

## Fields

| Field | Type | Description |
|---|---|---|
| **Payment Request ID** | formula | Auto-generated: PR# + Payment Date + Autonumber + Label \| Program Name. |
| **Payment Request Label** | singleLineText | Short free-text label describing what this payment is for (e.g. "Quito Hotel", "All-Inclusive ECOS"). Appears in the primary field ID. |
| **Program** | link -> Programs | The Program this payment is for. |
| **Destination** | lookup | Destination pulled from the linked Program. Reference only. |
| **Program Name** | lookup | Program Name from the linked Program. |
| **Requested By** | link -> ENVOYS HQ | The HQ team member submitting this payment request. |
| **Form of Payment** | singleSelect | Payment method.<br>Options: Wire Transfer - Gusto - Paypal - Check - Zelle |
| **Vendor** | link -> Vendors | The vendor being paid. Linking the vendor auto-populates all financial detail fields below. |
| **Payment Information Additional Notes** | lookup | Special payment instructions pulled from the linked Vendor. |
| **Vendor Payment Information Timestamp** | lookup | Last time the vendor's financial details were updated. Helps Finance check if banking info is current. |
| **Beneficiary Name** | lookup | Legal name on the vendor's bank account, pulled from Vendor. Must match exactly for wire transfers. |
| **Country (Financial Details)** | lookup | Country of the vendor's payment details, pulled from Vendor. |
| **Currency (Financial Details)** | lookup | Vendor's accepted payment currency, pulled from Vendor. |
| **Address (Financial Details)** | lookup | Vendor's payment details address, pulled from Vendor. |
| **Account Type** | lookup | Account type (Checkings/Savings), pulled from Vendor. |
| **Account Number** | lookup | Bank account number, pulled from Vendor. |
| **SWIFT/BIC Code** | lookup | SWIFT or BIC code, pulled from Vendor. |
| **IBAN Number** | lookup | IBAN number, pulled from Vendor. |
| **Routing Number** | lookup | US routing number, pulled from Vendor. |
| **Finance Information Update** | lookup | Date the vendor's financial details were last changed. |
| **Vendor Registered In Bank** | lookup | Whether this vendor is already registered in the company's bank portal, pulled from Vendor. |
| **Vendor Registration Timestamp** | lookup | When the vendor was registered in the bank portal. |
| **Transfer Currency** | link -> Currencies | The currency to send the transfer in. May differ from the vendor's Financial Details currency if a conversion is applied. |
| **Transfer Amount** | currency | Amount to transfer in the Transfer Currency. |
| **Confirm Transfer Amount** | number | Re-enter the transfer amount to confirm. Must match Transfer Amount exactly. |
| **Transfer Amount Match Check** | formula | Returns "Amounts Match!" if Transfer Amount = Confirm Transfer Amount; otherwise returns an error message. Finance should not process until this shows a match. |
| **Amount in USD** | currency | Transfer amount converted to USD for reporting and budget comparison. |
| **Payment Request Attachments** | multipleAttachments | Supporting documents -- invoices, contracts, or quotes justifying this payment. |
| **Payment Classification** | link -> Reconciliation Accounts | The Chart of Accounts code classifying this payment. Determines which FIN \| Reconciled rollup on Programs it feeds. |
| **Payment Request Information** | richText | Additional context for Finance -- what the payment is for, any special instructions. |
| **Payment Date** | date | The date Finance should process the payment by. |
| **ID** | autoNumber | System auto-increment. Used in the Payment Request ID formula. |
| **Status** | singleSelect | Where this payment stands.<br>Options: Not submitted to Finance - Pending - Paid - Paid & Confirmation Sent |
| **Work Days Until Payment Due** | formula | Workday count from today to Payment Date. Negative means overdue. |
| **Proof Of Payment** | multipleAttachments | Finance uploads confirmation or receipt showing payment was sent. Submitter will receive email notification to process and have traceability. |
| **Created By** | createdBy | The Airtable user who created this record. |

## Related tables

- **Programs** -- the program this payment belongs to
- **Vendors** -- the vendor being paid (financial details auto-populate from here)
- **ENVOYS HQ** -- the team member who requested the payment
- **Currencies** -- the transfer currency
- **Reconciliation Accounts** -- the COA classification

## Notes

- **Always link the Vendor first** -- financial detail fields populate automatically. Verify they are correct before submitting to Finance (check the Vendor Payment Information Timestamp to ensure banking info is current). If the payment details are more than one and constantly change, make sure to include them in the payment request information.
- **Vendor Registered In Bank must show true** before Finance can process a wire. Flag new vendors for registration before submitting the payment.
- **Transfer Amount Match Check must show "Amounts Match!"** before Finance will process. The double-entry is a required data quality gate.
- Payment Date drives Work Days Until Payment Due -- set it accurately to give Finance enough lead time.
