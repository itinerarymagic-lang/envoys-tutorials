# How to Resubmit and Update an HBH from a New or Modified I&B

This guide explains how to fix a program whose HBH (Hour by Hour) was uploaded incorrectly, or that needs to be linked to a new I&B (Itinerary & Budget) sheet.

Use it when:

- The I&B version was changed after the program was migrated.
- The wrong I&B version was used during migration.

The process keeps the Program record (title, POD Leads, dates, SOT numbers, etc), deletes everything else tied to that program's HBH (Days, Blocks, Versions and Costs), and rebuilds it from new CSV files exported from the correct I&B.

---

## Before You Start

Do not click anything until you have checked that the following all show the same information:

- The I&B sheet
- The I&B record in Airtable
- The Program record

This includes the number of participants and the dates. If any of them differ, fix that first. The new HBH is built from this information.

You will also need two CSV files, both downloaded from the correct I&B sheet:

1. The HBH CSV, from the staging_hbh tab.
2. The Associated Costs CSV, from the staging_associated_costs tab.

Each file must be uploaded to its own matching section. Be careful not to upload the Associated Costs file in the HBH section, or the other way around.

---

## Step-by-Step

**1. Open the I&B to Program Migration interface.**
Open Airtable, go to the OPS section and click "I&B to Program Migration". This interface is used to migrate I&Bs to Programs, and it only shows I&Bs with the status Ready to Migrate.

**2. Open the HBH Resubmission interface.**
In the top left sidebar, next to the interface title, there is a redirect button (a rectangle with a diagonal arrow). Hover over it and it says "HBH Resubmission". Click it.

**3. Find the program and start the resubmission.**
A new tab opens with the HBH Resubmission interface. Search for the program you want to resubmit and click the blue button "Resubmit HBH - Step 0".

Before you confirm, double-check that you selected the right program. Step 0 deletes all data tied to that program's HBH and it cannot be undone.

**4. Check for the red HBH Resubmission check.**
Once the process runs correctly, the red HBH Resubmission check appears on the program. This tells you the program is ready to receive the new files.

**5. Upload the new CSV files.**
Upload the CSV files you exported from the correct I&B. Upload each file in its own section (HBH file in the HBH section, Associated Costs file in the Associated Costs section).

**6. Check the dates.**
Make sure the dates selected are exactly the same as in the updated I&B.

**7. Click through the blue buttons up to Step 4.**
Continue by clicking each blue button in order, all the way to Step 4. Wait for each step to finish before clicking the next one.

**8. Check the final result.**
Open the OPS HBH operational interface and confirm that the program shows the right itinerary and the right dates.

---

## What Each Step Does Behind the Scenes

| Step | What it does |
|---|---|
| Step 0 | Deletes all previous data except the Program record. |
| Step 2 | Uses the dates in the Program and I&B records to create the Days records for the HBH. |
| Step 3 | Creates the HBH line by line from the uploaded CSV. |
| Step 4 | Creates the Associated Costs line by line from the uploaded CSV. |

Because Step 2 builds the Days from the dates in the Program and I&B records, wrong dates there will produce a wrong HBH. This is why the Before You Start check matters.

---

## Quick Checklist

- The I&B sheet, I&B record and Program record match (dates and number of participants).
- You exported the CSV files from the correct, updated I&B.
- You selected the correct program before confirming Step 0.
- Each CSV was uploaded in its own section.
- The dates selected match the updated I&B.
- The OPS HBH operational interface shows the right itinerary and dates.
