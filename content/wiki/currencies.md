# Currencies

**Primary field:** Currency

Currency reference table. Each record is one currency with its exchange rate to USD. Linked across most financial tables — Schools, Vendors, Field Staff, Vendor Payments, Transactions, and Program Field Staff Assignments all pull currency and rate from here.

## Fields

| Field | Type | Description |
|---|---|---|
| **Currency** | singleLineText | ISO 4217 currency code (e.g. USD, EUR, COP, MXN). Primary field. |
| **Currency Name** | singleLineText | Full name of the currency (e.g. US Dollar, Euro, Colombian Peso). |
| **Exchange Rate to USD** | number | Current exchange rate: how many units of this currency equal 1 USD. Updated automatically via scheduled automation. Used for estimated calculations only. |
| **Associated Country** | link → Countries | The country where this currency is the primary currency. |
| **Field Staff Profiles** | link → Field Staff Profiles | Field staff whose preferred payment currency is this one. |
| **Schools** | link → Schools | Schools whose local billing currency is this one. |
| **Program Field Staff Assignments** | link → Program Field Staff Assignments | Active link — staff assignments where this currency is used for the negotiated salary. |
| **Vendor Payments** | link → Vendor Payments | Vendor payment requests made in this currency. |
| **Transactions** | link → Transactions | Transaction records posted in this local currency. |
| **Vendors** | link → Vendors | Vendors whose financial details are denominated in this currency. |

## Notes

- Exchange rates are **automatic** — a scheduled automation fetches the average daily exchange rate. Used for estimated calculations only. Source of truth for actual USD amounts is determined by Reconciled expenses.
