# Invoices

**Primary field:** Income Record ID

Income tracked via invoices issued to schools or parents for a Program. Each record is one invoice -- deposit, balance, flights, or an extra charge. Payment status on each invoice rolls up to the FIN | Income section of the linked Program.

## Fields

| Field | Type | Description |
|---|---|---|
| **Income Record ID** | formula | Auto-generated identifier combining the linked Program name and Invoice Number. Primary field. |
| **Program** | link -> Programs | The Program this invoice is associated with. |
| **School** | lookup | School name pulled from the linked Program. |
| **Date** | date | Date the invoice was issued. |
| **Invoice Number** | singleLineText | Invoice number as it appears on the issued document. Must be unique per program. |
| **Invoiced Amount** | currency | Total amount billed on this invoice in USD. Rolls up to FIN \| Total Invoiced on Programs. |
| **Invoice Uploaded** | multipleAttachments | The invoice document sent to the school or parent. |
| **Categories** | singleSelect | Type of charge on this invoice. Determines whether the amount rolls into FIN \| Additional Ground Invoiced or FIN \| Additional Flights Invoiced on the Program.<br>Options: Deposit - Balance - Full Amount - Extra - Flights - Flights Extra |
| **Proof Of Payment** | multipleAttachments | Bank confirmation or receipt showing the payment was received. |
| **Invoice Destination Email** | singleLineText | Email address the invoice was sent to. |
| **Invoice Sent** | checkbox | Check once the invoice has been sent to the recipient. |
| **Invoice Payment Status** | singleSelect | Current payment state of this invoice.<br>Options: Idle - Request For Finance - Not Sent - Sent & Pending - Complete |
| **Invoice Payment Status Last Updated** | lastModifiedTime | Last time the Invoice Payment Status field was changed. |
| **Payment Category** | singleSelect | Whether this invoice is billed to the school as a group or to an individual parent.<br>Options: School Invoice - Parent Invoice |
| **Notes** | singleLineText | Free-text notes on this invoice. |

## Related tables

- **Programs** -- the invoice rolls up into FIN | Total Invoiced, FIN | Total Paid, FIN | Additional Ground/Flights Invoiced
- **Schools** -- accessible via the Program lookup

## Notes

- **Categories drives the rollup split on Programs.** Any invoice with Categories = "Flights" or "Flights Extra" counts toward FIN | Additional Flights Invoiced; everything else goes to FIN | Additional Ground Invoiced.
- **Invoice Payment Status = Complete** is what triggers FIN | Total Paid to count this invoice. Don't mark Complete until funds are confirmed received.
