# Program Dashboard

**Primary field:** Program Document

School-facing documents and resources linked to a program — proposals, websites, rooming lists, contracts, travel policies, hotel information, flight documents, and more. One record per document per program. The Document Type field selects from a fixed list of recognized document types; if a type isn't listed, use “Other” and set a name in Optional Document Name.

## Fields

| Field | Type | Description |
|---|---|---|
| **Program Document** | formula | Auto-generated: Programs \| Document Type (or Optional Name if “Other”). Primary display identifier. |
| **Programs** | link → Programs | The Program this document belongs to. |
| **Document Type** | singleSelect | Type of document.<br>Options: Proposal · Program Website · Registration Dashboard · Registration Information · RAMPs · Pre-Departure Resources · Get Curious · Photo Album · Faculty Hour-by-Hour · Contract · Travel Policies · Code of Conduct · Participant Agreement · Rooming List · Hotel Information · Final Issued Tickets · Other |
| **Description** | formula | Auto-populated description of the document type. For “Other” types, shows the free-text name instead. |
| **Optional Document Name** | singleLineText | Free-text name used when Document Type = “Other”. Do not include the program name — it’s added automatically in the primary field. |
| **Optional Description** | singleLineText | Custom description for “Other” document types. Overrides the auto-description formula. |
| **Link to Document** | url | URL of the document (Google Drive, Canva, external link, etc.). |
| **Shared** | checkbox | Check once this document has been shared with the school or is live in the dashboard. |

## Related tables

- **Programs** — each document belongs to one program

## Notes

- This table is for **school-facing** resources for the creation of program dashboards.
- The Description formula auto-fills a standard explanation for each recognized Document Type. Only fill in Optional Description if you selected “Other” and want a custom description. If a new recurring type is needed, contact system Administrator to add.
- The Program Document primary field automatically prepends the program name — do not include it in Optional Document Name.
