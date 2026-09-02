# Allocations

**Primary field:** Allocation ID

Connects a Transaction to a Program with a split amount and a Chart of Accounts code. Each transaction can have multiple allocations if the expense was shared across programs. The sum of all allocations for a transaction should equal that transaction's Amount (Local Currency). When it does, the transaction's Amount Pending Reconciliation reaches 0 and Status becomes Completed.

## Fields

| Field | Type | Description |
|---|---|---|
| **Allocation ID** | formula | Auto-generated: Transaction Description + Autonumber. Primary display identifier. |
| **Allocated Amount** | currency | The portion of the transaction amount assigned to this program and COA code. |
| **Transactions** | link -> Transactions | The Transaction this allocation splits. |
| **Staff** | lookup | Field Staff Profile linked through the Transaction. Reference only. |
| **Staff Email** | lookup | Staff email pulled through the Transaction. |
| **Amount Pending Reconciliation (from Transaction)** | lookup | Remaining unallocated amount on the linked Transaction. When this reaches 0, the transaction is fully reconciled. |
| **Status** | formula | Returns "Completed" when Amount Pending Reconciliation = 0; otherwise blank. |
| **Description (from Transaction)** | lookup | Transaction description pulled for context. |
| **Program Linked** | link -> Programs | The Program this portion of the expense is charged to. |
| **Category** | link -> Reconciliation Accounts | The Chart of Accounts code this expense is classified under. Determines which FIN \| Reconciled rollup on Programs it feeds. |
| **Airtable Finance Reference (from Category)** | lookup | Internal Airtable finance label from the linked Reconciliation Account. |
| **Statements** | link -> Statements | The Statement linked through the transaction. |
| **Reconciliation Visibility (from Statements)** | lookup | HQ Related or Field Related, pulled from the linked Statement. |
| **text Reconciliation Visibility (from Statements)** | formula | Plain-text version of Reconciliation Visibility for filtering. |
| **Receipt** | multipleAttachments | Receipt for this expense. Required for reconciliation unless the "I don't have a receipt" checkbox is checked. |
| **I don't have a receipt.** | checkbox | Check if no receipt is available. Acknowledged exception -- Finance reviews these. |
| **Observations** | richText | Notes explaining what this expense was for, why it was split this way, or any other reconciliation context. |
| **ID** | autoNumber | System auto-increment. Used in the Allocation ID formula. |

## Related tables

- **Transactions** -- the expense being split
- **Programs** -- the program this cost is charged to
- **Reconciliation Accounts** -- the COA code classifying this expense
- **Statements** -- accessible through the transaction

## Notes

- The data in this table comes from the SOFTR Recon App. Can be manually overridden and edited if needed. RECONCILIATION INTERFACE COMING SOON FOR FINANCE.
- A receipt is expected for every allocation. Finance reviews the "I don't have a receipt" exceptions.
- The Allocated Amount on this record should be in the same currency as the transaction's Amount (Local Currency) -- not USD, unless the transaction is a USD expense.
