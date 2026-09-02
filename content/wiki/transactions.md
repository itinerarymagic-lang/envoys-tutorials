# Transactions

**Primary field:** Id

Individual expense line items created from Statements. Previously named "Expenses." One record per transaction row from a statement CSV. Each transaction is allocated to one or more programs via the Allocations table -- the sum of its allocations should equal the transaction amount.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Returns the Airtable Record ID. Primary display identifier. |
| **Description** | multilineText | Merchant or transaction description as it appears on the statement. |
| **Date** | date | Transaction date (when the charge occurred). |
| **Post Date** | date | Settlement date (when the charge posted to the account). |
| **Amount (USD)** | currency | Transaction amount in USD. |
| **Amount (Local Currency)** | number | Transaction amount in local currency, if different from USD. Used for field expense reconciliation. |
| **Exchange Rate** | formula | Calculated exchange rate: Local Amount / USD Amount. Returns an error message if either is missing or zero. |
| **Local Currency** | link -> Currencies | The local currency of the transaction, if not USD. |
| **Balance** | currency | Running account balance at the time of the transaction (checking accounts only). |
| **Category** | singleLineText | Category as imported from the statement CSV. |
| **Type** | singleLineText | Transaction type as imported (e.g. Purchase, Credit, Fee). |
| **Cardholder** | singleLineText | Name on the card used, from the statement. |
| **Card Last4** | singleLineText | Last four digits of the card used. |
| **Reference Number** | singleLineText | Bank reference or check number for this transaction. |
| **Memo** | multilineText | Additional memo or description from the statement. |
| **Source CSV** | singleSelect | Which account this transaction came from (mirrors Statement Type for filtering). |
| **Statement Link** | link -> Statements | The Statement record this transaction was imported from. |
| **Statement Period** | lookup | Period pulled from the linked Statement. |
| **Field Staff Profiles from Statement** | lookup | Field staff linked to the Statement this transaction came from. |
| **Record Id (from Statement Link)** | lookup | Statement Record ID. Used to build the Softr reconciliation URL. |
| **Back to Statements** | formula | Direct URL to this transaction's statement page in the Softr reconciliation portal. |
| **Reconciler Name** | lookup | Staff member name pulled from the linked Statement. Non-editable. |
| **Field Staff Profiles** | link -> Field Staff Profiles | Direct link to the field staff member who made this expense (may differ from the Statement reconciler if manually overridden). |
| **Staff Email** | lookup | Email from the directly linked Field Staff Profile. |
| **Staff Type** | lookup | Staff Type from the directly linked Field Staff Profile. |
| **Status** | singleSelect | Reconciliation status of this transaction.<br>Options: Pending - Partial - Completed |
| **Allocations** | link -> Allocations | Allocation records to this transaction. Relationship between Transactions and allocations can be 1 to Many, and at least 1:1 for an expense to be Reconciled. |
| **Allocated Amount Rollup** | rollup | Sum of all Allocation amounts linked to this transaction. |
| **Amount Pending Reconciliation** | formula | Local Amount minus Allocated Amount. Should reach 0 when fully allocated. |
| **transferred_check** | formula | Returns "transferred" if the Field Staff Profile from Statement differs from the directly linked Field Staff Profile, indicating the expense was transferred between reconcilers. |
| **Expense Reconciliation Type** | singleSelect | Whether this is a program-related or HQ office expense.<br>Options: Program Related Expense - HQ Office Expense |
| **Revised by Finance** | checkbox | Check once Finance has reviewed and approved any manual adjustments to this transaction. |
| **Program** | link -> Programs | Direct program link (used when the transaction is allocated 100% to one program, as a shortcut). |
| **Direction** | singleSelect | Whether this is an outgoing expense or an incoming credit.<br>Options: Money Out - Money In |

## Related tables

- **Statements** -- the source statement this transaction came from
- **Allocations** -- how this transaction is split across programs and COA codes
- **Field Staff Profiles** -- the staff member who made the expense
- **Currencies** -- the local currency if not USD
- **Programs** -- direct link for single-program allocations

## Notes

- The reconciliation target: **Amount Pending Reconciliation = 0**. When all allocations are in, Status should be set to Completed.
- `transferred_check` returning "transferred" means the expense was submitted under one staff member's statement but should be reconciled under another. Finance reviews these cases.
- `Amount (Local Currency)` is the denominator for allocation -- allocate against this figure, not Amount (USD), for field expenses in non-USD currencies.
