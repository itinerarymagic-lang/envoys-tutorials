# School Participant Profiles

**Primary field:** Participant ID

> ⚠️ **This table holds sensitive PII and medical data** (passports, allergies, medications, mental health information, emergency contacts). Only surface the fields needed for a given task. Do not display medical fields in any interface unless explicitly required.

Student and faculty registration records submitted via Jotform or other built automations. One record per participant per program. Created automatically when a Jotform submission is received — do not create or edit records manually. The Programs link is set by the automation; do not change it.

## Fields

| Field | Type | Description |
|---|---|---|
| **Participant ID** | formula | Unique identifier: First + Middle + Last Name + Passport Number + Date of Birth (MMDDYY). Primary field. |
| **Programs (Link to Database)** | link → Programs | The Program this participant is registered for. Set by automation — do not edit unless automation fails. Contact system manager for batch linking. |
| **Participant Full Name** | formula | Concatenates First + Middle + Last Name. |
| **Start Date of Program (From Database)** | lookup | Program Start Date from the linked Program. Used to calculate passport expiration flags and participant age. |
| **School (From Database)** | lookup | School pulled from the linked Program. |
| **Submission Timestamp** | dateTime | When the Jotform form was submitted. |
| **Start Date of Program** | date | Program start date as entered by the participant on the registration form. Cross-check against the Database lookup. |
| **Program Name** | singleLineText | Program name as entered by the participant on the form. Needed to automatically link program. |
| **Participant First Name** | singleLineText | First name from the registration form. |
| **Participant Middle Name** | singleLineText | Middle name from the form. |
| **Participant Last Name** | singleLineText | Last name from the form. |
| **Date of Birth** | date | Participant's date of birth. Used to calculate age and classify as Student or Faculty. |
| **Participant Age During Program Start Date** | formula | Age at Program Start Date. Participants under 20 are classified as Students; 20+ as Faculty. |
| **Participant Type** | formula | Auto-classifies as Student (age < 20) or Faculty (age ≥ 20). |
| **Participant Type (Text)** | singleSelect | Manual override of participant type for the EM interface extension.<br>Options: Student · Faculty · Traveling Faculty (Adult) |
| **Gender** | singleLineText | Gender as entered on the form. Used for rooming lists. |
| **Preferred Name** | singleLineText | Preferred name if different from legal first name. |
| **Preferred Pronoun** | singleLineText | Preferred pronouns. |
| **Parent First Name** | singleLineText | Parent/guardian first name (students only). |
| **Parent Last Name** | singleLineText | Parent/guardian last name. |
| **Parent Full Name** | formula | Concatenates Parent First + Last Name. |
| **Parent Email** | email | Parent/guardian email. Primary contact for pre-program communication. |
| **Parent/Student Address** | multilineText | Home address — used for SWAG shipping if needed. |
| **Travelers Email** | email | The traveler's own email (distinct from parent email for faculty/adult participants). |
| **Passport Number** | multilineText | Passport document number. Used in the Participant ID formula. |
| **Passport Country** | singleLineText | Country of passport issuance. |
| **Passport Expiration Date** | date | Passport expiry date. |
| **Expiration Date Flags** | formula | Returns "Good To Go" if passport expires ≥ 180 days after program start; "Review Passport" if sooner. |
| **Passport Upload** | multipleAttachments | Scan or photo of the passport. |
| **Hiking Ability** | singleLineText | Self-reported hiking ability level. |
| **Swimming Ability** | singleLineText | Self-reported swimming ability level. |
| **Shirt Size** | singleSelect | T-shirt size for SWAG orders.<br>Options: XS · S · M · L · XL · XXL |
| **Food Allergies** | singleLineText | Whether participant has food allergies (Yes/No). |
| **Food Allergy Severity** | singleLineText | Severity level of food allergy. |
| **Food Allergy Reaction Type** | multilineText | Description of allergic reaction. |
| **Food Allergy Treatment** | multilineText | Treatment protocol for food allergy (e.g. EpiPen, antihistamine). |
| **Non-Food Allergies** | singleLineText | Whether participant has non-food allergies (Yes/No). |
| **Non-Food Allergy Severity** | singleLineText | Severity level. |
| **Non-Food Allergy Reaction Type** | multilineText | Description of reaction. |
| **Non-Food Allergy Treatment** | multilineText | Treatment protocol. |
| **Carries EpiPen** | singleLineText | Whether the participant carries an EpiPen (Yes/No). |
| **Dietary Restrictions** | singleLineText | Whether participant has dietary restrictions. |
| **Dietary Restriction Details** | multilineText | Details of dietary restrictions (e.g. vegetarian, halal, vegan). |
| **Current Medications** | singleLineText | Whether participant takes regular medications (Yes/No). |
| **Medications Detail** | richText | Full list of medications with dosage, frequency, and purpose. |
| **Medications Not Taken During Program** | singleLineText | Whether any medications will be intentionally suspended during the program. |
| **Medications Not Taken Explanation** | multilineText | Explanation of which medications will be suspended and why. |
| **Respiratory Issues** | singleLineText | Whether participant has respiratory conditions (asthma, etc.). |
| **Respiratory Details** | multilineText | Details of respiratory condition and management. |
| **Diabetes** | singleLineText | Whether participant has diabetes. |
| **Diabetes Details** | multilineText | Type, management method, supplies needed. |
| **Neurological Conditions** | singleLineText | Whether participant has neurological conditions. |
| **Neurological Details** | richText | Condition details and management notes. |
| **Chronic / Recurring Medical Conditions** | singleLineText | Other ongoing medical conditions not covered above. |
| **Chronic Condition Details** | multilineText | Details and management. |
| **Medical Devices** | singleLineText | Whether participant uses medical devices (e.g. hearing aids, insulin pump). |
| **Medical Device Details** | multilineText | Device type and requirements. |
| **Head Injury** | singleLineText | History of head injury or concussion. |
| **Head Injury Details** | multilineText | Details and current status. |
| **Mental Health Treatment** | singleLineText | Whether participant is currently receiving mental health treatment. |
| **Mental Health Details** | multilineText | Treatment type and any field considerations. |
| **Hospitalized / Crisis Center Admittance** | singleLineText | Whether participant has been hospitalized or admitted to a crisis center. |
| **Hospitalization Details** | multilineText | Circumstances and current status. |
| **Eating Disorders** | singleLineText | Whether participant has or has had an eating disorder. |
| **Eating Disorder Details** | multilineText | Details and current management. |
| **Additional Medical Information** | multilineText | Any other medical information the participant or parent wants to share. |
| **Emergency Contact Name** | singleLineText | Emergency contact full name. |
| **Emergency Contact Phone** | multilineText | Emergency contact phone number. |
| **Photo Release Permission** | singleLineText | Whether the participant/parent authorizes use of photos taken on program. |
| **Signature Assertion** | singleLineText | Participant/parent signature acknowledgment from the form. |
| **Registration Date** | formula | Date derived from the Submission Timestamp. |
| **Jotform Registration Link** | url | Link to the Jotform registration form used for this submission. |
| **Jotform Submission Form ID** | singleLineText | Jotform form ID. Used for debugging automation issues. |
| **Payment Status** | singleSelect | Whether the participant's program fee has been paid.<br>Options: Payment Pending · Partial Payment Made · Full Payment Made · Other |
| **Total Paid** | currency | Total amount paid by this participant to date. |
| **Deviations** | singleSelect | Whether the participant has a flight deviation (arriving or departing on different dates/routes than the group).<br>Options: Yes · No |
| **Notes on Deviations** | multilineText | Details on the deviation — alternate flight, dates, and any cost implications. |
| **Financial Aid Details** | multilineText | Financial aid arrangements for this participant. |
| **Financial Aid Payments** | multilineText | Payment schedule or notes for financial aid recipients. |
| **Created** | createdTime | Timestamp of record creation (same as Submission Timestamp for Jotform imports). |

## Related tables

- **Programs** — each registration links to one program
- **Schools** — accessible via the Program

## Notes

- Records are created automatically by the Jotform → Airtable automation. Do not create, edit, or delete records manually — changes may be overwritten on the next sync.
- The `Programs (Link to Database)` field is set by the automation. Changing it will break the participant count rollups on Programs.
- `Participant Type` classifies by age (under 20 = Student). `Participant Type (Text)` is a manual override singleSelect used by the EM interface extension — keep it in sync if you need to reclassify a traveling adult.
