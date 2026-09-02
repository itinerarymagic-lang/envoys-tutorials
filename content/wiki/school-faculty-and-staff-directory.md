# School Faculty & Staff Directory

**Primary field:** Full Name

Contact directory for faculty and staff at partner schools. Each record is one person. Contacts can be linked directly to Programs as primary contacts and to the School's directory. Also used on Countries for phone country code tracking.

## Fields

| Field | Type | Description |
|---|---|---|
| **Full Name** | formula | Concatenates First Name + Middle Name + Last Name + Position Title (dash-separated). Primary display identifier. |
| **First Name** | singleLineText | Contact's first name. |
| **Middle Name** | singleLineText | Middle name (optional). |
| **Last Name** | singleLineText | Contact's last name. |
| **Preferred Name** | singleLineText | Name the contact prefers to be addressed by, if different from first name. |
| **Preferred Pronoun** | singleLineText | Contact's preferred pronouns (e.g. she/her, he/him, they/them). |
| **Email** | email | Primary email address. |
| **Phone** | phoneNumber | Phone number (use with School Directory Country Code Phone for dialing). |
| **Address** | multilineText | Mailing address (optional — used when shipping SWAG or documents). |
| **Position Title** | singleLineText | Job title at the school (e.g. "Director of Experiential Learning", "Dean of Students"). |
| **Contact's School** | link → Schools | The school this contact belongs to. |
| **Notes** | multilineText | Short working notes on this contact — communication preferences, relationship history, context. |
| **Primary contact for Programs** | link → Programs | Programs where this person is the designated school-side primary contact. |
| **School Directory Country Code Phone** | link → Countries | Country code for this contact's phone number. Select the country to auto-populate the dialing prefix. |
| **Notes Section** | richText | Extended notes — use for longer relationship context, preferences, or history that doesn't fit the short Notes field. |

## Related tables

- **Schools** — each contact belongs to one school
- **Programs** — contacts can be designated as primary for specific programs
- **Countries** — used for phone country code

## Notes

- This table is for school-side contacts only. ENVOYS internal team members go in **ENVOYS HQ**. Field staff go in **Field Staff Profiles**.
- The Full Name formula includes Position Title after a dash — if a contact has no title, the formula omits the dash automatically.
