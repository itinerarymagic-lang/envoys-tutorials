# Field Staff Profiles

**Primary field:** Staff ID

Directory and compliance record for all Envoys field staff — certifications, availability, payment preferences, personal emergency contacts, and expertise. One record per staff member. Program Field Staff Assignments link here when staff are assigned to a program.

## Fields

| Field | Type | Description |
|---|---|---|
| **Staff ID** | formula | Concatenates First + Middle + Last Name. Primary display identifier. |
| **Full Name** | formula | Same as Staff ID — mirrors the name for display in linked fields. |
| **First Name** | singleLineText | First name. |
| **Middle Name** | singleLineText | Middle name (optional). |
| **Last Name** | singleLineText | Last name. |
| **Phone Country Code** | link → Countries | Country code for this staff member's WhatsApp number. |
| **Whatsapp Number** | phoneNumber | WhatsApp contact number (excluding country code). Primary communication channel on program. |
| **Email** | singleLineText | Email address. Used for contract delivery and pre-program communications. |
| **Date of Birth** | date | Date of birth. Used for background check and compliance purposes. |
| **Sex (match travel document)** | singleSelect | Sex as it appears on the travel document. Required for flight bookings.<br>Options: Female · Male · Other/Unspecified/Undetermined |
| **Staff Type** | singleSelect | Role category for this staff member.<br>Options: Field Staff - Localist · Field Staff - Globalist · HQ · Program Adult Assistance |
| **Staff Tier** | singleSelect | Internal seniority/experience tier used in compensation and assignment decisions.<br>Options: Category 1 · Category 2 · Category 3 · Category 4 · Category 5 · Category 6 · Not Available · Blocked · Other |
| **Country Coordinator Status** | singleSelect | Whether this staff member is designated as a Country Coordinator.<br>Options: Prospect · CC Designated · No |
| **CC Destinations** | link → Destinations | Destinations where this staff member serves as Country Coordinator. |
| **Shirt Size** | singleSelect | Shirt size for SWAG orders.<br>Options: XS · S · M · L · XL |
| **CV** | multipleAttachments | Staff member's curriculum vitae. |
| **Link to Staff Folder** | url | Link to this staff member's folder in Google Drive (FPF or equivalent). |
| **Highest Medical Training** | singleSelect | Highest level of medical certification held.<br>Options: None · WFR · WFA · CPR & First Aid · Other |
| **Medical Certification Expiration Date** | date | When the medical certification expires. |
| **Medical Certification Status** | formula | Returns "Valid", "Expired", "Missing Document", or a warning if expiring within 183 days. |
| **Background Check** | multipleAttachments | Background check document. |
| **Background Check Expiration Date** | date | When the background check expires. |
| **Background Check Status** | formula | Returns "Valid", "Expired", "Missing Document", or expiry warning. |
| **Life Guard Certification?** | singleSelect | Whether this staff member holds a lifeguard certification.<br>Options: Yes · No |
| **Lifeguard Certificate** | multipleAttachments | Lifeguard certificate document. |
| **Lifeguard Expiration Date** | date | Certificate expiry date. |
| **Lifeguard Status** | formula | Returns "Valid", "Expired", "Missing Document", or expiry warning. |
| **Passport** | multipleAttachments | Passport scan. |
| **Passport Number** | singleLineText | Passport document number. |
| **Passport Expiration Date** | date | Passport expiry date. |
| **Passport Status** | formula | Returns "Valid", "Expired", "Missing Document", or expiry warning. |
| **Driver License** | multipleAttachments | Driver's license scan. |
| **Driver License Expiration Date** | date | License expiry date. |
| **Driver License Status** | formula | Returns "Valid", "Expired", "Missing Document", or expiry warning. |
| **Payment Currency** | link → Currencies | The currency this staff member prefers to be paid in. |
| **Current Daily Rate** | currency | Default daily rate in the staff member's preferred payment currency. Used as a starting point for salary negotiation. |
| **Rate USD** | currency | Current daily rate expressed in USD. Maintained in parallel for cross-currency comparison. |
| **Destinations Expertise** | link → Destinations | Specific destinations where this staff member has direct experience. |
| **Languages** | multipleSelects | Languages this staff member speaks. Used for assignment matching in multilingual destinations. |
| **Theme Preference** | multilineText | Educational themes or program types this staff member is most interested in. |
| **Mailing Address** | richText | Full mailing address. Used for SWAG shipping and contract delivery. |
| **City** | singleLineText | City of residence. |
| **State of Residence** | singleLineText | State or province of residence. |
| **Country of Residence** | link → Countries | Country where the staff member currently lives. |
| **Region of Residence** | singleLineText | Region pulled from the linked Country of Residence. |
| **Personal Description** | multilineText | Bio or profile summary used in school-facing materials. |
| **Field Staff Photo** | multipleAttachments | Profile photo. Used in school-facing staff profiles and SWAG. |
| **Able to drive?** | singleSelect | Whether the staff member can drive a vehicle on program.<br>Options: Yes · No |
| **Swimming Ability** | singleSelect | Swimming competency level.<br>Options: Advanced · Intermediate · Basic · None · Other |
| **Staff Availability Observation** | multilineText | Notes on general availability patterns — semester schedules, known blackouts, commitments. |
| **Availability Weeks** | date | Next availability start date (approximate). |
| **Dietary/Medical Requirements** | richText | Staff member's own dietary needs or medical requirements relevant for field deployment. |
| **PEC Name** | singleLineText | Personal Emergency Contact full name. |
| **PEC Country Code** | link → Countries | Country dialing code for the emergency contact's phone. |
| **PEC Phone** | phoneNumber | Emergency contact phone number. |
| **Assigned Programs** | link → Program Field Staff Assignments | All program assignments for this staff member. |
| **I&B Requests** | link → I&B Requests | I&B Requests where this staff member is the I&B Builder. |
| **Statements** | link → Statements | Expense statement records for this staff member. |
| **Payment Detail Notes** | richText | Notes on payment preferences, bank details, or any special instructions for paying this staff member. |
| **Associated Expenses** | link → Transactions | Transaction records linked to this staff member's expense reports. |
| **Pending Associated Expenses** | count | Count of linked transaction records. |
| **Total Associated Expenses** | count | Total count of all linked transaction records (pending and completed). |
| **SOFTR Permanent Login Link** | url | Permanent magic-link URL for this staff member's Softr portal access. System-managed — do not edit. |
| **HQ Profile Link** | link → ENVOYS HQ | If this field staff member also has an HQ record, link it here. |
| **Invitation Sent** | singleSelect | Whether the Softr portal invitation has been sent.<br>Options: No · Invitation Sent · Yes |
| **Training Accepted** | checkbox | Checked once the staff member has completed onboarding/training. |
| **Training Date** | date | Date training was completed. |
| **Active on Platform** | checkbox | Whether this staff member currently has active Softr access. |
| **Able to be RC?** | singleSelect | Whether this staff member is qualified to serve as a Resource Coordinator on program.<br>Options: Yes · No |
| **Able to be EM?** | singleSelect | Whether this staff member is qualified to serve as an Experience Manager.<br>Options: Yes · No |
| **Able to be Globalist?** | singleSelect | Whether this staff member can be deployed internationally (Globalist role).<br>Options: Yes · No |
| **Able to be Localist?** | singleSelect | Whether this staff member can serve as a Localist (local country expert) on program.<br>Options: Yes · No |

## Related tables

- **Program Field Staff Assignments** — the junction table where staff are assigned to programs with role and salary details
- **Currencies** — payment currency preference
- **Countries** — expertise, residence, emergency contact, phone code
- **Destinations** — destination expertise
- **I&B Requests** — I&B builder assignments
- **Statements**, **Transactions** — expense reconciliation
- **ENVOYS HQ** — cross-reference for dual HQ/field staff members

## Notes

- All four certification status formulas follow the same logic: Missing → Expired → Warning (within 183 days) → Valid. Run a compliance check before assigning staff to a program.
- `SOFTR Permanent Login Link` is system-managed. Do not edit it manually — it is generated by an automation when the record is created.
- The following fields from an earlier version of the schema no longer exist in the live table: Age Preference, Residency Observations, PEC Relationship, PEC Email, Negotiation Notes, Programs (consolidated link).
