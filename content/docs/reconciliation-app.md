# Reconciliation App (Recon Desk)

Recon Desk is the Envoys app for reconciling expenses. Every card payment, cash withdrawal and personal expense has to be matched to a program or to HQ, with a category, a description and a receipt. The same app is also where you upload program photos and open your staff hour by hour.

The video above walks through the HQ view. This page covers the whole app in writing, for HQ and for field staff.

---

## Who uses it

Your user type shows next to your name at the top of the home page.

| User type | What you can do |
| --- | --- |
| HQ | Reconcile program expenses and HQ office expenses |
| Field Staff | Reconcile the expenses of the programs you staff |
| Administrator | Everything HQ can do, plus a view of all reconciliations |

---

## Logging in

### If you are HQ

1. Open Airtable and go to **ENVOYS | GENERAL**.
2. Click **ENVOYS HQ Profiles**.
3. Click your own profile to open it.
4. At the bottom of your record, find the field **Magiclink Reconciliation App**.
5. Click the link. You are logged in straight away, with no password.

Your magic link is personal. Anyone who has it can open your account, so do not share it or paste it into a chat.

### If you are field staff

1. Look for an email inviting you to **Recon Desk**.
2. Click **Accept invitation**.
3. Set a new password.
4. Go back to the login page and sign in with the same email address the invitation was sent to.

If you see a message saying your profile could not be found, ask HQ to create your Field Staff profile with that same email, then log in again.

---

## The home page

| Area | What it shows |
| --- | --- |
| Welcome bar | Your name, your user type, and how many reconciliations are still pending out of your total |
| Tabs | **Reconciliations** and **Program Photos** |
| Buttons | **Register Field Cash**, **Register Personal Funds** and **Batch reconcile** |
| Search | Find a transaction by its description |
| Filters | Card / source, Period, Status and Type |
| Transaction list | Each transaction with its amount, how much is still pending, and its status |
| Left sidebar | **Recon Desk** (this page) and **Staff HBH** |

A transaction stays in your pending list until its full amount has been allocated.

---

## Reconciling a transaction

### 1. Open it

Click a transaction in the list. At the top you see the purchase date, the method of payment, the cardholder, and three numbers:

| Number | What it means |
| --- | --- |
| Amount | The total of the transaction |
| Allocated | How much you have already assigned through allocations |
| Pending | What is still left to assign |

### 2. Transfer it, if it is not yours

If the expense belongs to someone else, click **Transfer Expense**, select the person, and confirm. The whole expense moves to them and they become responsible for reconciling it. They receive an email telling them so.

### 3. Choose the reconciliation type

Under **What Reconciliation type is this expense?** pick one:

- **Program Related Expense** for anything spent on a program.
- **HQ Office Expense** for anything spent on running HQ.

The **Add allocation** button only appears after you choose a type.

### 4. Add an allocation

The **Allocations** section starts empty. Click **Add allocation** and fill in the form.

| Field | What to enter |
| --- | --- |
| Allocation Amount | The amount for this allocation. Click **Remaining Balance** to fill in everything that is still pending. |
| Program | The program the expense belongs to. Only shown for Program Related Expenses. |
| Allocation Category | The account from the chart of accounts that describes the expense |
| Observations | A short description of what the expense was for |
| Upload Receipt | The receipt for the expense. If you do not have one, switch on **I don't have a receipt**. |

Click **Allocation Completed** to save it. The button stays grey until the required fields are filled in and you have either uploaded a receipt or switched on **I don't have a receipt**.

### 5. Split the expense, if needed

One transaction can be divided across several programs or categories. Enter part of the amount in the first allocation, save it, then click **Add allocation** again for the next part. Keep going until **Pending** reaches zero.

### 6. Done

When the allocated amount equals the total, the transaction is fully reconciled and leaves your pending list.

---

## HQ Office Expenses

HQ Office Expenses follow the same steps. The only difference is that the allocation form has no **Program** field.

---

## Batch reconcile

Use this when several transactions share the same category, for example a group of software subscriptions.

1. Click **Batch reconcile**. Checkboxes appear next to each transaction.
2. Tick every transaction that belongs in the batch.
3. Click **Reconcile selected**.
4. Choose the reconciliation type.
5. Fill in the program, allocation category, observations and receipt once. These are shared by every transaction in the batch.
6. Check the amount next to each transaction. Each one keeps its own amount.
7. Click **Reconcile**. All the selected transactions are updated together.

To leave batch mode without changing anything, click **Cancel selection**.

---

## Register Personal Funds

Use this when you paid for a program expense with your own money.

1. Click **Register Personal Funds**.
2. Select the **Program**.
3. Select the **Local Currency** you paid in. Use the same currency stated in your contract.
4. Enter the **Amount** in that currency.
5. Set the **Date** the money was spent.
6. Click **Register Personal Funds**.

Register the total of the personal funds you used for that program. This creates a new transaction in your list, marked **Personal Funds**. Open it and add allocations, exactly as you would for a card payment, explaining what the money was used for.

---

## Register Field Cash

Use this for cash you withdraw to use during a program.

1. Click **Register Field Cash**.
2. Select the **Program**.
3. Enter **Field Cash in USD**: the amount in US dollars.
4. Select the **Local Currency**.
5. Enter **Field Cash in local currency**: the amount of cash you actually received.
6. Set the **Date** of the withdrawal.
7. Click **Register Field Cash**.

The form shows the **Exchange Rate** it will use. It is calculated from the cash you actually received, not from the market rate.

### Revolut withdrawals

For a withdrawal with your Revolut card, the USD amount is the one your Revolut app shows for that withdrawal.

Example: you withdraw 500,000 Colombian pesos and your Revolut app shows 120 dollars.

| Field | Value |
| --- | --- |
| Field Cash in USD | 120 |
| Local Currency | COP |
| Field Cash in COP | 500,000 |

The app works out a rate of 4,166.67 COP per USD for that withdrawal.

Registering field cash creates a new transaction in your list. Open it and allocate the total amount spent, using that exchange rate. If you have cash left over at the end of the program, follow the program's instructions for the remaining balance, or ask the HQ lead.

---

## Program Photos

1. On the home page, click the **Program Photos** tab.
2. Select the **Program**. You only see the programs you are assigned to.
3. Check the **Date**. It is set to today.
4. Drop your photos into the **Photos** box, or click it to choose files.
5. Click **Upload photos**.

---

## Staff HBH (hour by hour)

1. In the left sidebar, click **Staff HBH**.
2. Select a **Program**. You only see the programs you are assigned to.

The page shows the live version of the field staff hour by hour for that program:

- A summary with the start and end dates, ground days, and the number of students, faculty and field staff.
- Every block of the program, day by day, with its times, location, description, category, booking status, payment status and notes.

Use **Columns** to choose which columns to show, **Expand notes** to read the full notes, and **Export PDF** to save a copy.

---

## Common questions

**The Add allocation button is missing.** Choose the reconciliation type first.

**Allocation Completed is grey.** A required field is empty, or you have not uploaded a receipt or switched on **I don't have a receipt**.

**A transaction is still in my list after I added an allocation.** Its Pending amount is not zero yet. Add another allocation for the remaining balance.

**I received an email about an expense I did not make.** Someone transferred it to you. Open it and reconcile it, or transfer it on if it is not yours either.
