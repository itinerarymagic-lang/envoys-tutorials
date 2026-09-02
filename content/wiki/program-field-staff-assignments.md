# Program Field Staff Assignments

**Primary field:** Program Staffing ID

Junction table mapping field staff to programs, with role, salary, flight logistics, contract status, and cash reconciliation. One record per staff-program pairing. The salary formula chain runs here: daily rate → bonuses → total → first/second payment split.

## Fields

| Field | Type | Description |
|---|---|---|
| **Program Staffing ID** | formula | Role Type + Staff Name. Primary display identifier. |
| **Full Assignment ID** | formula | Program Name \| Role Type + Staff Name. Full identifier including program context. |
| **Program** | link → Programs | The Program this assignment belongs to. |
| **Program Name** | lookup | Program Name from the linked Program. |
| **Destination (from Program)** | lookup | Destination pulled from the linked Program. |
| **Country of Program** | lookup | Country pulled from the linked Program's Destination. |
| **Program Start Date** | lookup | Program Start Date from the linked Program. Used in the payment date formula. |
| **Program End Date** | lookup | Program End Date from the linked Program. Used in the second payment date formula. |
| **Preparation Days** | lookup | Preparation Days from the linked Program. Used in the total salary formula. |
| **Number of Ground Days** | lookup | Number of Ground Days from the linked Program. |
| **Selected Field Staff** | link → Field Staff Profiles | The field staff member assigned to this program. |
| **Staff's Accepted Currencies** | lookup | Payment currency from the linked Field Staff Profile. Reference for negotiation. |
| **Staff's Current Daily Rate** | lookup | Default daily rate from the linked Field Staff Profile. Starting point for negotiation. |
| **Staff's Current Daily Rate USD** | lookup | Rate USD from the linked Field Staff Profile. |
| **Currency for Program Negotiated Staff Salary** | link → Currencies | The currency agreed for this specific assignment's salary. May differ from the staff member's default preference. |
| **Program Negotiated Daily Staff Salary** | currency | The daily rate negotiated for this assignment, in the salary currency. |
| **Program Negotiated Daily Salary with Applied Bonuses** | formula | Negotiated Daily Salary × 1.1 if Solo Program or Program Director bonuses apply; otherwise equals the base rate. |
| **Solo Program** | checkbox | Check if this staff member is the sole staff on the program. Triggers +10% bonus. |
| **Program Director** | checkbox | Check if this staff member is the Program Director. Triggers +10% bonus. |
| **Training Completion** | checkbox | Check once the staff member has completed pre-program training. When checked, the Training Day rate is added to the Second Payment. |
| **Negotiated Total Salary** | formula | Total salary: (Daily Rate with Bonuses × Ground Days) + (Daily Rate with Bonuses × 1 prep day bonus) + (Daily Rate with Bonuses / 2 × Preparation Days). |
| **Negotiated Total Salary USD** | formula | Total salary converted to USD using the exchange rate from the linked Currency. |
| **Exchange Rate** | lookup | Exchange rate to USD from the linked Currency. |
| **First Payment Amount** | formula | Half of the Negotiated Total Salary (50% paid before program starts). |
| **Second Payment Amount** | formula | Remaining half, plus Training Day rate if Training Completion is checked, plus Personal Funds advanced, minus Confirmed Leftover Cash. |
| **Program Role Type** | singleSelect | Whether the staff member is a Globalist or Localist.<br>Options: Globalist · Localist |
| **Staff Flight Cost** | currency | Cost of the staff member's flights to/from the destination. Rolls up to S&R \| Staff Flights Total Budget on Programs. |
| **Departure Flight Location** | singleLineText | Airport code for the staff member's departure airport (e.g. JFK, BOG). |
| **Return Flight Location** | singleLineText | Airport code for the staff member's return airport. |
| **Staff Flight Arrival at Destination** | dateTime | Date and time the staff member arrives at the program destination. |
| **Staff Flight Departure from Destination** | dateTime | Date and time the staff member departs the program destination. |
| **Staff First Full Preparation Day** | date | First full preparation day for this staff member. Used to anchor FINOPS Cash Deadline on Programs. |
| **Flight Ticket Purchased** | checkbox | Check once the staff member's flight has been purchased. |
| **Flight Email Sent** | checkbox | Check once the flight confirmation email has been sent to the staff member. |
| **Preparation Days Email Sent** | checkbox | Check once the email notifying the staff member of their preparation days has been sent. |
| **Flight Document** | multipleAttachments | Flight itinerary or ticket document. |
| **Program Participants** | singleLineText | Internal connector field. Do not edit. |
| **Current Payment Date Due** | formula | Next payment deadline: 10 working days before Program Start if First Payment not yet sent; 10 working days after Program End if it has been sent. |
| **First Payment Requested** | checkbox | S&R check once the first payment details are confirmed to requested to Finance. |
| **First Payment Sent** | checkbox | Finance check once the first payment has been confirmed sent to the staff member. |
| **Second Payment Ready** | checkbox | Check once all conditions [end of program, Leftover Cash, Personal Expenses, Salary Deductions] for the second payment are met and it is ready to send. |
| **Second Payment Sent** | checkbox | Check once the second payment has been confirmed sent. |
| **Second Payment Sent Timestamp** | lastModifiedTime | Automatically records when Second Payment Sent was checked. |
| **Staff Assignment Status** | singleSelect | Pipeline stage for this assignment.<br>Options: 1. Idea for Staff · 2. Reach Out to Staff · 3. Verbal Confirmation · 4. Program Terms Sent · 5. Ready for Contract · 6. Contract Sent · 7. Contract Signed |
| **Contract Status** | singleSelect | Staff Assignment Status.<br>Options: Pending · Program Terms Created · Program Terms Sent · Contract Created · Contract Sent |
| **Contract URL** | url | Link to the signed or pending contract document. |
| **Program Terms** | url | Link to the program terms document sent to the staff member. |
| **Program Meetings** | link → Program Meetings | Program meetings this staff member is included in. |
| **Selected for Cash Instructions** | checkbox | Check once this staff member has been selected to receive field cash for the program. |
| **Cash Instructions** | richText | Instructions for how the staff member should manage and account for field cash. |
| **Confirmed Leftover Cash** | currency | Amount of unspent field cash the staff member is returning after the program. Deducted from the Second Payment. |
| **Confirmed Personal Funds** | currency | Amount of personal funds the staff member spent on program expenses. Added to the Second Payment. |
| **Salary Deduction** | currency | Any salary deduction applied. |
| **Staff Salary Notes** | richText | Notes on salary negotiations, deductions, or special arrangements for this assignment. |

## Related tables

- **Programs** — the program this assignment belongs to
- **Field Staff Profiles** — the staff member assigned
- **Currencies** — the negotiated salary currency
- **Program Meetings** — meetings this staff member attends

## Notes

- **Salary formula chain:** Negotiated Daily Salary → + Bonuses → Negotiated Total → ÷ 2 → First/Second Payment. The Second Payment also accounts for Training Day, Personal Funds, and Leftover Cash.
- **Current Payment Date Due** is a rolling formula — it switches from pre-program to post-program deadline automatically once First Payment Sent is checked.
- **Solo** and **Program Director** bonuses are +10% each but do not stack — the formula applies × 1.1 if *either* box is checked, not × 1.21 for both. Verify the formula if both apply.
