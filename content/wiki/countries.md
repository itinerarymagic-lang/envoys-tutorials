# Countries

**Primary field:** Counties

Country reference table — the geographic backbone of the base. Links Destinations, Schools, Currencies, Vendors, and Field Staff together by country. Also used for phone country codes on ENVOYS HQ and School Faculty & Staff Directory contacts.

## Fields

| Field | Type | Description |
|---|---|---|
| **Counties** | formula | Mirrors the Name field. Primary display identifier. *(Field name "Counties" is a live typo in Airtable — do not rename without checking formula references.)* |
| **Name** | singleLineText | Full country name (e.g. Colombia, Japan, France). |
| **Region** | singleLineText | Geographic region (e.g. South America, East Asia, Western Europe). Used for grouping and reporting. |
| **Country Code** | singleLineText | International dialing code prefix (e.g. +1, +33, +57). Used for phone number formatting across contact tables. |
| **Country + Code** | formula | Concatenates Name and Country Code for display in dropdowns. |
| **Destinations** | link → Destinations | Destinations within this country. |
| **Schools** | link → Schools | Partner schools based in this country. |
| **Currencies** | link → Currencies | The currency record for this country. |
| **Exchange Rate to USD** | lookup | Exchange rate pulled from the linked Currency. |
| **Vendors** | link → Vendors | Vendors registered/based in this country (financial details country). |
| **Field Staff Profiles \| Country of Residence** | link → Field Staff Profiles | Field staff whose country of residence is this country. |
| **Field Staff Profiles \| Phone Country Code** | link → Field Staff Profiles | Field staff phone country code. |
| **Field Staff Profiles \| PEC Country Code** | link → Field Staff Profiles | Field staff whose personal emergency contact is in this country. |
| **ENVOYS HQ** | link → ENVOYS HQ | HQ team members whose phone country code is this country. |
| **School Faculty & Staff Directory** | link → School Faculty & Staff Directory | School contacts whose phone country code is this country. |
