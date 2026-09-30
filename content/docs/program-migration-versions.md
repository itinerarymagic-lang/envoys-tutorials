# From I&B to Program: Migration & Versions

What happens when an approved Itinerary & Budget moves into Airtable, what each of the 4 migration steps does, and why every Program has more than one version of its HBH.

---

## The short version

- **Before approval,** the I&B Google Sheet is the source of truth.
- **When the proposal is approved,** we migrate it into Airtable in 4 steps. From that moment, the **Program** in Airtable is the source of truth.
- **Every Program keeps its costs in Versions:** **Budget** (what we sold), **Quote** (what we're actually planning, and where you work) and **Execution** (what we really spent, created at Closing).
- **Comparing the versions category by category** tells us if a program is using the money we planned for it.

[![The life of a program: I&B Sheet, Migration, Program, Closing](content/img/migration/01-big-picture.svg)](content/img/migration/01-big-picture.svg)

---

## Stage 1: The I&B Sheet is the source of truth

When PT asks for an itinerary, an **I&B Request** record is created in Airtable, together with its **I&B Google Sheet**. At this stage, the Sheet is the source of truth.

The Sheet runs on formulas, so it reacts to changes:

- Change the number of students → every per-student price recalculates.
- Change the dates → the days move.
- Change a unit price → the totals follow.

Think of it as a draft written in pencil. You can erase and redraw as much as you need while the school decides.

---

## Migration: when the pencil becomes pen

When the proposal is approved, the I&B is migrated into Airtable. This is the exact moment the I&B **stops** being the source of truth and the **Program** takes over.

After migration, changes you make in the Sheet do **not** reach Airtable. From here on, the itinerary lives in the Program.

> **Only migrate when the I&B is ready.** The Budget Version is a photo of the I&B at the moment of migration. Migrate a half-finished I&B and you freeze a half-finished budget, and every financial comparison after that will be wrong.

---

## What are Versions?

A **Version** is one set of the program's costs, kept for a specific purpose.

| Version | Think of it as | It answers | Who works on it |
|---|---|---|---|
| **Budget** | The photo | What did we plan to spend when we sold the program? | Nobody. It stays frozen. |
| **Quote** | The live plan | What do we expect to spend now, with real bookings and real vendor prices? | **OPS. This is where you work.** |
| **Execution** | The receipt | What did we actually spend? | Created at Closing, from reconciled expenses. |

### The Version record is tiny

In the **Program Versions** table, each record only holds:

- Which version it is: **Budget**, **Quote** or **Execution**
- The Program it belongs to
- Number of **Students**
- Number of **Faculty**
- Number of **Staff**

Every HBH Block and every Associated Cost is linked to **exactly one** version. That's how each version can have its own participant numbers. You can change the Quote version's numbers without touching the Budget (see *Two sets of participant numbers* below).

[![How the tables connect: Program, Versions, HBH Blocks, Associated Costs, HBH Days](content/img/migration/03-how-tables-connect.svg)](content/img/migration/03-how-tables-connect.svg)

### Why the versions are not exact copies

In the old Envoys App, the versions had to be identical. That made it easy to compare them line by line, but it also meant **you couldn't change the itinerary.**

Real programs change all the time. The school asks for 3 new activities. A hotel on Day 2 falls through and you move the group to another town. If the versions had to match line for line, you couldn't make any of those changes.

So the rules are:

1. The **Quote** HBH is free to change as the program evolves.
2. We compare versions **by category** (Accommodations, Activities, Transportation, Meals...), not line by line.

**Example.** Right after migration, Budget and Quote are identical. Then the school asks for a chocolate workshop on Day 2, and the Day 2 hotel changes from Monteverde to La Fortuna. Everyone here is 20 students + 2 faculty + 2 staff = 24 people.

<div class="table-scroll">

| Day | HBH Block | Category | Budget | Quote |
|---|---|---|---|---|
| 1 | Private bus to Monteverde | Transportation | $350 | $350 |
| 1 | Hotel Monteverde | Accommodations | $1,440 | $1,440 |
| 2 | Zipline canopy tour | Activities | $900 | $900 |
| 2 | Hotel Monteverde | Accommodations | $1,440 | *(removed)* |
| 2 | Eco-lodge La Fortuna | Accommodations | *(not there)* | $1,680 |
| 2 | Chocolate workshop | Activities | *(not there)* | $600 |

</div>

Line by line, this doesn't work: the chocolate workshop has nothing to compare against, and the two hotels are different lines. **By category**, it's clear:

<div class="table-scroll">

| Category | Budget | Quote | Difference |
|---|---|---|---|
| Accommodations | $2,880 | $3,120 | +$240 |
| Activities | $900 | $1,500 | +$600 |
| Transportation | $350 | $350 | $0 |
| **Total** | **$4,130** | **$4,970** | **+$840** |

</div>

We can change anything in the itinerary and still see exactly where the money moved.

---

## The 4 migration steps

The migration buttons are on the **I&B record** in **OPS | I&B Request List**.

**Before you click anything:**

- The I&B is final. Remember: Step 3 freezes it.
- **HBH Blocks CSV** is uploaded: one file, exported from the `staging_hbh` tab of the I&B Sheet.
- **Associated Costs CSV** is uploaded: one file, exported from the `staging_associated_costs` tab.

**Click the steps in order, one at a time.** Each step builds on the one before it, so let each step finish before you click the next. When a step is done, its **Step X Complete?** box is ticked, so anyone can see how far the migration got.

[![The 4 migration steps and what each one creates](content/img/migration/02-four-steps.svg)](content/img/migration/02-four-steps.svg)

### Step 1: Create the Program and its Versions

- Creates the **Program** record. A Program needs many fields an I&B never did: pods, confirmed flights, booking statuses, payment statuses and more.
- Creates the **Budget** and **Quote** **Version** records, each with its own number of students, faculty and staff.
- It does **not** add any HBH yet. The versions exist, but they're empty, like a binder with labeled tabs and no pages.

### Step 2: Create the HBH Days

- Uses the Program's dates to create one **HBH Days** record per day: its day number and its date.
- Example: a 5-day program starting Mon Feb 22 gets *Day 1 : Mon Feb 22*, *Day 2 : Tue Feb 23*... through *Day 5 : Fri Feb 26*.
- The days are the shelves the HBH Blocks will sit on in Step 3.

### Step 3: Build the HBH, twice

This is where the itinerary actually arrives in Airtable.

- **First: the Budget HBH.** Copies the I&B itinerary into HBH Blocks linked to the **Budget** version. This is the frozen copy of the I&B. It still follows the same math as the Sheet: if the Budget version's participant numbers change, its totals recalculate.
- **Second: the Quote HBH.** Makes an exact duplicate, linked to the **Quote** version.

Right after Step 3, Budget and Quote are identical. As bookings, school requests and payments happen, the Quote HBH changes and the Budget doesn't. Keeping them separate is what lets us measure how we're doing.

### Step 4: Import the Associated Costs, twice

Some costs aren't part of the day-by-day HBH, like preparation days, essentials and staffing. Step 4 imports them into **Associated Costs**: one set linked to the **Budget** version and one set linked to the **Quote** version.

### After Step 4, the Program has:

| | Budget version | Quote version |
|---|---|---|
| Participant numbers | ✔ | ✔ |
| HBH Blocks (sitting on the HBH Days) | ✔ frozen copy of the I&B | ✔ live copy you work on |
| Associated Costs | ✔ | ✔ |

---

## Budget vs Quote: what you can touch

| | Budget | Quote |
|---|---|---|
| Edit, add or remove HBH Blocks | **No** | **Yes** |
| Change participant numbers | Only to match the Quote when comparing (see below) | **Yes**, to forecast |
| Changes show on the HBH sent to the school and staff | No | **Yes** |
| Source of truth for the itinerary | No | **Yes** |

**Once a program is migrated, every HBH change happens in the Quote version.** The Budget is the photo of what we sold. We keep it untouched so we can measure how the real program compares to the plan.

---

## Two sets of participant numbers

A Program has two kinds of participant numbers, and they are **not** linked on purpose.

| | SOT numbers | Version numbers |
|---|---|---|
| Where they live | On the Program | On each Program Version record |
| What they mean | How many people we officially expect | How many people this version is priced for |
| Do HBH costs use them? | No | **Yes**. Every HBH total is calculated from its version's numbers. |

**Why keep them separate?** So OPS can play with the numbers without breaking anyone else's work.

**Example.** The SOT says 20 students. For reservations you want to hold space for the maximum the school could bring, which is 24 students. Set the **Quote** version's Students to 24 and every per-student and per-person line in the Quote HBH recalculates instantly. The SOT stays at 20, so other teams' numbers don't move.

If the two were linked, you'd have two bad options: change the official numbers and mess up other teams' work, or do the math by hand, which is exactly what happened in the old App.

### Comparing fairly: match the numbers first

Before you compare Budget and Quote, set the **Budget** version's participant numbers to match the **Quote** version.

Otherwise the difference you see is "more kids," not "things cost more." The zipline is $45 per student. The Budget (20 students) shows $900 and the Quote (24 students) shows $1,080. That looks like $180 over budget, but the price didn't change, only the group size did. Set the Budget to 24 students and it shows $1,080 too. Now the only differences left are real ones.

---

## How an HBH cost is calculated

Every HBH Block has a **Cost Basis** that tells Airtable **who to count**. Airtable multiplies the **Unit Cost USD** by that count, using the numbers on the block's version. It's the same logic the I&B Sheet used.

| Cost Basis | Formula | Example (Quote: 24 students, 2 faculty, 2 staff) |
|---|---|---|
| **Per Group** | Unit Cost × 1 | Private bus: $350 × 1 = **$350** |
| **Per Person** | Unit Cost × everyone | Hotel: $60 × 28 = **$1,680** |
| **Per Student** | Unit Cost × students | Zipline: $45 × 24 = **$1,080** |
| **Per Adult** | Unit Cost × (faculty + staff) | Park entry, adult rate: $30 × 4 = **$120** |

[![Cost Basis: who gets counted](content/img/migration/04-cost-basis.svg)](content/img/migration/04-cost-basis.svg)

So when you change the Quote from 20 to 24 students:

- Per Student and Per Person lines **go up**.
- Per Group lines **stay the same**.
- Per Adult lines **stay the same**, because the number of adults didn't change.

Nothing is broken. That's the system working.

---

## The money fields on an HBH Block

| Field | Who fills it | What it is |
|---|---|---|
| **Cost Basis** | Comes from the I&B | Who to count: Per Group, Per Person, Per Student or Per Adult |
| **Unit Cost USD** | Comes from the I&B | The price of one unit |
| **Total Forecast Cost USD** | Automatic | Unit Cost × the count from the Cost Basis. Our **prediction**. |
| **Quoted Total Cost USD** | **You** | What we will actually pay, or already paid, the vendor |
| **Local Amount** | **You** | The vendor's price in local currency |
| **Local Amount to USD** | Automatic | Local Amount ÷ the exchange rate in Airtable |

[![From forecast to quoted cost](content/img/migration/05-money-fields.svg)](content/img/migration/05-money-fields.svg)

### Total Forecast Cost USD: the prediction

This works like the I&B Sheet: it predicts the cost from the Unit Cost, the Cost Basis and the Quote version's participant numbers. Change the numbers and the forecast updates by itself. That's what lets OPS test different group sizes and get an accurate forecast.

### Quoted Total Cost USD: the real price

At first it equals the Total Forecast Cost USD. Once you contact vendors, their price is usually different: discounts, taxes, budget errors and so on. This field holds **exactly what you expect to pay, or have already paid,** for that good or service.

**Example.** The zipline forecast is $1,080 (24 students × $45). The vendor gives a 10% group discount. Type **$972** into Quoted Total Cost USD. The forecast stays at $1,080. Now we can see the difference between what we predicted and what we actually got.

### Local Amount → Local Amount to USD: no outside calculator needed

Local vendors often quote in local currency, but all our math is in USD. Don't convert it yourself:

1. Type the vendor's price into **Local Amount**. Example: the hotel quotes **₡892,500** (Costa Rican colones, tax included).
2. **Local Amount to USD** converts it with the exchange rate stored in Airtable. At 510 colones per dollar: 892,500 ÷ 510 = **$1,750**.
3. **Copy that number into Quoted Total Cost USD yourself.** It does not fill in on its own.

---

## Closing: the Execution version

When a Program is back from the field and ready to close, it's migrated to **Closing**. This creates the **Execution** version.

We don't retype every cost. The real amounts come from the **reconciled expenses linked to the Program**.

Now each category can be compared across all three versions:

- **Budget:** the money set aside for the program when it was sold
- **Quote:** what we expected to spend, used for cash flow and financial planning
- **Execution:** what we actually spent

<div class="table-scroll">

| Category | Budget | Quote | Execution | What it tells us |
|---|---|---|---|---|
| Accommodations | $3,000 | $3,300 | $3,250 | We knew about a $300 increase ahead of time and ended up $250 over budget. |
| Activities | $1,800 | $2,400 | $2,400 | The school added activities. We planned for it and it matched. |
| Transportation | $700 | $700 | $820 | On plan until the field. Something unexpected came up on the ground. |

</div>

*(Example numbers.)*

---

## Quick questions

**I changed the number of students on the Quote version and a lot of costs changed. Did I break something?**
No. Per Student and Per Person lines follow the version's numbers. Per Group lines, and Per Adult lines when the adult count hasn't changed, stay the same.

**The school changed the itinerary. Where do I make the change?**
In the **Quote** version's HBH. Never in the Budget, and not in the I&B Sheet, because the Sheet stopped being the source of truth at migration.

**I see a mistake in the Budget version. Should I fix it?**
No. Leave the Budget as it is and make changes in the Quote. The Budget records what we sold, and the gap between Budget and Quote is exactly what we want to measure.

**I typed the Local Amount but Quoted Total Cost USD is still the old number.**
That's expected. Copy the value from **Local Amount to USD** into **Quoted Total Cost USD** yourself.

**Can I click Step 3 before Step 2?**
No. Step 3 places the HBH Blocks on the days Step 2 creates, inside the versions Step 1 creates. Always go 1 → 2 → 3 → 4.

---

## Cheat sheet

- **I&B Sheet** = source of truth **until migration**.
- **Program / Quote version** = source of truth **after migration**.
- **Budget** = frozen photo of what we sold. Don't edit its HBH.
- **Quote** = where OPS works. Change the HBH, participant numbers and quoted prices here.
- **Execution** = what we really spent, created at Closing from reconciled expenses.
- **Total Forecast Cost USD** = automatic prediction. **Quoted Total Cost USD** = real price, typed by you.
- **Compare by category**, with participant numbers matched between versions.
