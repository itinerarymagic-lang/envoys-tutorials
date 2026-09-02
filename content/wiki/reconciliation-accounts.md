# Reconciliation Accounts

**Primary field:** Chart of Accounts Reference

Chart-of-accounts tags provided by Finance, used across Allocations, Vendor Payments, and Income for reconciliation.

✍️ Each record is one COA line item. When a Transaction is allocated to a Program, it gets tagged with a Reconciliation Account so Finance can roll up spend by category. The two Visibility checkboxes control which records appear in the reconciliation interface for each expense type.

## Fields

| Field | Type | Description |
|---|---|---|
| **Chart of Accounts Reference** | multilineText | ✍️ Full chart of accounts line item name as defined by Finance. Primary identifier — must match the external accounting system exactly. |
| **COA Code** | multilineText | ✍️ Numeric code for this line item (e.g. 5110, 5210). Used to match rollup filters in the Programs table FIN \| Reconciled fields. |
| **COA Group** | singleSelect | ✍️ Top-level accounting category this line belongs to.<br>Options: Assets · Liabilities · Equity · Income · Cost of Goods Sold · General & Administrative · Labor Costs · Program Development · Other Income & Expenses |
| **COA Sub-Group** | singleSelect | ✍️ More granular classification within the COA Group.<br>Options: Cash & Bank Accounts · Accounts Receivable (A/R) · Other Current Assets · Fixed Assets · Other Assets · Accounts Payable (A/P) · Other Current Liabilities · Long-Term Liabilities · Equity · Transport (Air) · Travel Logistics · Staffing · Operations Assistance · Additional Participant Salary · Essentials · SWAG · Other · External Consulting · Insurance, Corporate Taxes, Fees & Permits · Equipment, Office & Systems · Training, Events & Program Development · Leadership & Teams · Sales & Marketing · Other G&A · Contractors & International Payroll · Payroll - US · Program Development · Other Income · Other Expenses |
| **Airtable Finance Reference** | multilineText | ✍️ Internal Airtable label used when referencing this account in automations or formulas. May differ slightly from the COA Reference. |
| **Airtable Reconciliation Visibility** | singleSelect | ✍️ Controls which team's reconciliation view this account appears in.<br>Options: Finance Team · Field Related · HQ Related |
| **COA Description** | multilineText | ✍️ Plain-language explanation of what expenses belong to this account. Written by Finance. |
| **Allocations** | link → Allocations | ✍️ All Allocation records tagged with this COA code. |
| **Vendor Payments** | link → Vendor Payments | ✍️ All Vendor Payment records classified under this COA code. |
| **Income** | singleLineText | ⚠️ ✍️ Orphaned. Was a link to the Income table, which no longer exists. |
| **Visible For HQ Office Expenses** | checkbox | ✍️ When checked, this account appears as an option when reconciling HQ office expenses. |
| **Visible For Program Related Expense** | checkbox | ✍️ When checked, this account appears as an option when reconciling program-related expenses. |

## Related tables

- **Allocations** — expense splits tagged with this COA code
- **Vendor Payments** — payment requests classified under this account
- **Programs** — the `FIN | Reconciled …` rollup fields on Programs each filter by a specific COA code from this table

## Notes

- The two-letter prefix on the COA Code (5xxx = program expenses, 6xxx = G&A, etc.) matches the numbering convention in the external accounting system.
- The `FIN | Reconciled` rollup fields on Programs each have a filter set to one specific COA code. If a code changes here, the rollup filter on Programs must be updated manually in the Airtable UI — the API cannot update rollup conditions.
- `Income` is orphaned (`singleLineText`) following the deletion of the Income table. Safe to remove from the UI if it causes confusion.
