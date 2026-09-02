# Statements

**Primary field:** Id

Uploaded credit card and bank statements -- the origin point for some Transactions. Each record is one monthly statement from one account. Transactions are created from the CSV rows and linked back here. Field staff also link their statements here for reconciliation tracking.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Auto-generated: Account Type + Period + Reconciler Name. Primary display identifier. |
| **Type** | singleSelect | The account or card this statement is from. |
| **Period** | singleSelect | Calendar month this statement covers (YYYY-M format, e.g. 2026-6). |
| **CSV** | multipleAttachments | The raw statement CSV file. Upload once -- the automation reads it to create Transaction records. |
| **Created** | createdTime | When this statement record was created. |
| **Autonumber** | autoNumber | System auto-increment. Used in the Id formula. |
| **Transactions** | link -> Transactions | Link to all transaction records created from this statement. |
| **Field Staff Profiles** | link -> Field Staff Profiles | The field staff member this statement belongs to, if it is a personal card/account reconciliation. Can be blank or manually updated through Airtable interfaces. |
| **Email (from Field Staff Profiles)** | lookup | Field staff email pulled from the linked Field Staff Profile. |
| **Reconciler Type** | lookup | Staff Type from the linked Field Staff Profile (Field Staff vs HQ). |
| **Reconciliation Visibility** | formula | Returns "HQ Related" or "Field Related" based on Reconciler Type. Controls which view the statement appears in. |
| **Reconciler Name** | lookup | Full name of the field staff member linked to this statement. |
| **# of Pending+Partial** | rollup | Count of linked Transactions with Status = Pending or Partial. When this reaches 0, the statement is fully reconciled. |
| **Status** | formula | Returns "Reconciled" when # of Pending+Partial = 0; otherwise "Pending". |
| **Record Id** | formula | Returns the Airtable Record ID. Used in the Softr reconciliation URL. |
| **Allocations** | link -> Allocations | Allocations linked to transactions from this statement. |
| **CC Last 4 Digits** | singleLineText | Last four digits of the credit card, if applicable. Used to distinguish multiple cards on the same account. |

## Related tables

- **Transactions** -- created from this statement's CSV
- **Field Staff Profiles** -- the person whose card/account this statement covers
- **Allocations** -- expense splits from transactions within this statement

## Notes

- Upload the CSV once and let the automation create Transaction records. Do not manually create transactions from a statement.
- Status becomes "Reconciled" automatically when all transactions from this statement have been allocated through the SOFTR Recon App.
