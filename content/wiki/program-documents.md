# Program Documents

**Primary field:** Program Document

Connecting table of internal operating documents linked to a program -- Hotel Information Documents, Rooming Lists, RAMPs, flight estimates and proposals, TLTs, and ticket issue documents. One record per document per program. Enables us to have a non-restrictive number of associated documents to a program.

## Fields

| Field | Type | Description |
|---|---|---|
| **Program Document** | formula | Auto-generated: Document Type \| Program Name. Primary display identifier. |
| **Programs** | link -> Programs | The Program this document belongs to. |
| **Document Type** | singleSelect | Type of internal document.<br>Options: Hotel Document Information - Rooming List - Field RAMP - Destination RAMP - Medical RAMP - Flight Estimate - Flight Proposal - TLT - Flight Ticket Issued Document - Other |
| **Link to Document** | url | URL of the document in Google Drive, FPF, or external storage. |
| **Last Modified** | lastModifiedTime | Last time the Link to Document changed. Tracks when the document was last updated. |
| **Shared with School** | checkbox | Check once this internal document has been shared externally (e.g. Hotel Document sent to school, RAMP shared with risk team). |

## Related tables

- **Programs** -- each document belongs to one program

## Notes

- This table is for **internal operational documents** (RAMPs, Hotel Information Documents, TLTs, flight docs). School-facing resources go in **Program Dashboard**.
