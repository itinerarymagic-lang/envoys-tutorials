# Schools

**Primary field:** School

Partner school directory. Each record is one school. Programs, I&B Requests, and School Participant Profiles all link back here. Financial information (local currency, exchange rate) and the school's faculty/staff directory are also stored here.

## Fields

| Field | Type | Description |
|---|---|---|
| **School** | formula | Auto-generated identifier: School Name \| City. Primary display field — use this when linking, not School Name alone, to avoid confusion between schools with similar names. |
| **autonumber** | autoNumber | System auto-increment. Used in the School formula. Do not delete. |
| **School Name** | singleLineText | Full official name of the school. |
| **School Type** | singleSelect | Whether the school is based internationally or in the US/Canada.<br>Options: International · USA & CA |
| **City** | singleLineText | City where the school is located. Used in the School formula identifier. |
| **Country** | link → Countries | Country where the school is located. |
| **Main Contact Name** | singleLineText | Primary point of contact at the school (e.g. the trip coordinator or department head). |
| **Main Contact Email** | email | Email for the primary contact. |
| **Main Contact Phone** | phoneNumber | Phone number for the primary contact. |
| **Address** | richText | Full mailing address of the school. |
| **Current Account Lead** | link → ENVOYS HQ | The ENVOYS HQ team member responsible for the relationship with this school. |
| **Programs** | link → Programs | All Programs associated with this school. |
| **I&B Requests** | link → I&B Requests | All I&B Requests submitted for this school. |
| **School's Local Currency** | link → Currencies | The currency the school uses for billing. Drives the Final Land Price in Local Currency on Programs. |
| **School People Directory** | link → School Faculty & Staff Directory | All faculty and staff contacts at this school. |
| **Exchange Rate to USD** | lookup | Exchange rate for the school's local currency, pulled from the linked Currency record. |
| **Logo** | multipleAttachments | School logo. Used in school-facing documents and dashboards. COMING SOON: AN AUTOMATIC LOGO RETRIEVER FOR SCHOOL FACING ELEMENTS. |

## Related tables

- **Countries**, **Currencies** — geography and billing currency
- **Programs**, **I&B Requests** — the program pipeline for this school
- **ENVOYS HQ** — account lead
- **School Faculty & Staff Directory** — people at the school
- **School Participant Profiles** — students and faculty registrations (linked via Programs)
