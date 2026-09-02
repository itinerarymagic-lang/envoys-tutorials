# ENVOYS HQ

**Primary field:** Name

Internal ENVOYS team directory. Each record is one HQ team member. POD assignments on Programs link to this table (PT Lead, OPS Lead, EM Lead, S&R Lead, HQ Lead, HQ Blackouts Lead). I&B Request assignments also link here.

## Fields

| Field | Type | Description |
|---|---|---|
| **Name** | formula | Concatenates First + Middle + Last Name \| Team. Primary display identifier. |
| **First Name** | singleLineText | First name. |
| **Middle Name** | singleLineText | Middle name (optional). |
| **Last Name** | singleLineText | Last name. |
| **Team** | multipleSelects | Which functional team(s) this person belongs to.<br>Options: OPS · PT · S&R · EM · FINANCE |
| **Email** | email | Work email. Used in automations for notifications. |
| **Phone Country Code** | link → Countries | Country code for this person's phone number. |
| **Phone** | phoneNumber | Phone number (excluding country code). |
| **Slack ID** | singleLineText | Slack member ID. Used in Slack notification automations. |
| **SOFTR Permanent Login Link** | lookup | Permanent Softr login link pulled from the linked Field Staff Profile, if this HQ member also has a field staff record. |
| **Programs PT Pod** | link → Programs | Programs where this person is the PT Lead. |
| **Programs OPS Pod** | link → Programs | Programs where this person is the OPS Lead. |
| **Programs EM Pod** | link → Programs | Programs where this person is the EM Lead. |
| **Programs S&R Pod** | link → Programs | Programs where this person is the S&R Lead. |
| **Programs S&R Pod copy** | link → Programs | Programs where this person is the HQ Lead (Emergency Contacts). |
| **Programs** | link → Programs | Programs where this person is the HQ Blackouts Lead. Consolidated link field added alongside the POD-specific fields. |
| **I&B Requests Owner** | link → I&B Requests | I&B Requests where this person is the OPS Lead. |
| **I&B Requests PT Lead** | link → I&B Requests | I&B Requests where this person is the PT Lead. |
| **Vendor Payments** | link → Vendor Payments | Vendor payment requests submitted by this person. |
| **Schools** | link → Schools | Schools where this person is the Account Lead. |
| **Field Staff Profile Link** | link → Field Staff Profiles | If this HQ member also has a field staff record (e.g. they occasionally work in the field), link it here. Used to pull the Softr login link. |

## Related tables

- **Programs** — five POD link fields plus one consolidated link
- **I&B Requests** — OPS and PT lead assignments
- **Schools** — account lead per school
- **Vendor Payments** — requests raised by this person
- **Countries** — phone country code
- **Field Staff Profiles** — cross-reference for HQ members who also work as field staff

## Notes

- `Programs S&R Pod copy` is confusingly named — it actually backs the **POD | HQ Lead** field on Programs (Emergency Contacts), not a duplicate S&R field. The field name is a live misnomer.
- Each POD link field is directional: the link on Programs sets who the lead is; the lookup here shows all programs that person leads. They stay in sync automatically.
