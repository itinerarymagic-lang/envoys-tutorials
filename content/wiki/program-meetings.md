# Program Meetings

**Primary field:** Meeting Name

Scheduled meetings tied to a program. One record per meeting. The Meeting Type field drives the suggested date formula — each type has a fixed timing window relative to Program Start or End Date, calculated automatically and displayed as a suggestion in PROPOSED | Meeting Date. The actual scheduled time is always entered manually in SET | Meeting Date.

## Fields

| Field | Type | Description |
|---|---|---|
| **Meeting Name** | formula | Auto-generated: Meeting Type (or Optional Name if "Other") \| Program Name. Primary display identifier. |
| **Programs** | link → Programs | The Program this meeting belongs to. |
| **Program Start Date** | lookup | Program Start Date from the linked Program. Used in the PROPOSED date formula. |
| **Program End Date** | lookup | Program End Date from the linked Program. Used for Staff Debrief date calculation. |
| **Program Name** | lookup | Program Name from the linked Program. |
| **Meeting Type** | singleSelect | Type of meeting. Determines the suggested date offset and intended attendees. If other, use next field to name it. |
| **Optional Meeting Name** | singleLineText | Free-text name used when Meeting Type = "Other". Appears in the Meeting Name formula instead of the type. |
| **PROPOSED \| Meeting Date** | formula | Suggested meeting date based on Meeting Type and Program Start/End Date. Skips weekends and hardcoded holidays. This is a recommendation — ALWAYS confirm and enter the real date in SET \| Meeting Date. |
| **SET \| Meeting Date** | dateTime | The actual scheduled date and time. Source of truth. All times in Bogota time (Colombia / EDT). |
| **Link to Program Meeting Notes** | url | Link to the meeting notes document (Google Doc or equivalent). |
| **Meeting Participants** | singleLineText | Comma-separated email list of invitees. Paste here before creating calendar invites. |
| **Program Field Staff Assignments** | link → Program Field Staff Assignments | Staff assignments included in this meeting. |

## Meeting type timing reference

| Meeting Type | Suggested timing |
|---|---|
| PT/EM Program Handover | As soon as possible after handover |
| Program Kickoff | Immediately after PT handover |
| Introduction Meeting | ~45 days before Program Start |
| Staff Remote Preparation | ~20 days before Program Start |
| Team Traveling Meeting | ~30 days before Program Start |
| Program Handover Meeting | ~21 days before Program Start |
| Faculty Logistics Meeting | ~14 days before Program Start |
| Staff Debrief Meeting | 1 day after Program End |

## Related tables

- **Programs** — meetings belong to a program
- **Program Field Staff Assignments** — staff assignments can be associated with a meeting

## Notes

- PROPOSED | Meeting Date skips weekends and a hardcoded list of Colombian and US holidays through 2027. If the suggested date lands on a holiday it shifts forward to the next weekday.
- SET | Meeting Date is the only authoritative date — use it for calendar invites. Ignore PROPOSED after the real date is set.
- All times in SET | Meeting Date should be entered in Bogota time (America/Bogota / Colombia Standard Time).
