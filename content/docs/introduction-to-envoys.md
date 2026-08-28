# Introduction to Envoys | V.0

This is the first walkthrough of the Interfaces built inside the ENVOYS Airtable system — where the ideas from the last video (Database vs. Interfaces, and Table → Field → Record → Relationship) turn into things you'll actually click on and use every day.

---

## Quick Recap

Two ideas carry over from the previous session, and it's worth keeping both in mind below:

- **Backend vs. Frontend.** The backend is where the data actually lives (the tables). Interfaces are the frontend — how each person interacts with that data, built around what they specifically need.
- **The database mindset.** Every process breaks down into: what *thing* are we tracking, what *information* do we need about it, and how is it *related* to other things.

If something isn't covered here, that doesn't mean it doesn't exist — check the documentation and the Brain first. You might find your answer before you even have to ask it.

---

## What Are Interfaces?

The Tech Ticket system lets us build Interfaces: custom screens where we interact with the data we need, when we need it, and however we need it.

**Interfaces are dynamic.** They're built to change as our needs change — this isn't a fixed tour of a finished product. Version 1 was built on a lot of assumptions, some right and some wrong. Now that the ticket system exists, adjusting the system to what you actually need is much easier.

**Why this matters — stopping the silo effect.** Interfaces also give the whole team visibility into how other teams use the same data. That gets us:

- **Teamwork** — shared visibility across teams
- **Visibility** — see how other teams work, and where you might find something useful
- **Fallback control** — if someone is OOO, sick, or missing context, the information is still reachable

There's a good chance a question you have is already answered in another team's tab.

---

## Before Next Session

Two things to do before the test sessions:

1. Think back on last season — where did our old systems (App, Sheets, Jotform, Reconciliation, etc.) work *for* you, and where did they work *against* you? Take note of specific examples.
2. Restructure those notes into the new mindset: what thing, what information, how it's related.

Keep these in mind during testing next week. If something you need is missing, submit a Tech Ticket. Login details for the test sessions will be sent out beforehand.

---

## Record Details: Keeping Things Organized

A few rules of thumb for how tables and records stay usable as the system grows:

- **Fields are limited per table** on purpose — tidy and organized, without losing functionality.
- **If a field can be edited, it's meant to be edited.** If it can't be, don't try — that's deliberate, not a bug.

### Linked Records

Linking records instead of retyping information keeps things organized, eliminates duplicate entries, and collects data that can be used for analysis later.

Filling out linked fields matters more here than in other systems you've used. They aren't just a record of the truth — they're *connected* to the rest of the system. Filling them in correctly saves work later and can trigger automations. For example: adding POD Members to a record can trigger automatic notifications.

### Source of Truth (SOT)

Some information needs to look different depending on who's viewing it — which means more than one field for what feels like "the same" data. For example, Operations may work from an HBH view which needs difFerent values for participants, another field tracks actual Registered Participants that have filled out the Jotform, and EM records what is expected, the SOT. These aren't duplicates — each serves a different audience and purpose. 

### When a Field Needs Its Own Table

Sometimes a field would need an unpredictable number of entries — pricing is the clearest example. When that happens, the answer isn't to keep stretching one field; it's to turn that information into its own connected table. Go back to the same three questions: what thing, what information, how are they related.

---

## Buttons

Buttons on a record or interface can open another interface, run an automation, or open an external link.

---

## Action Item: Update Your Profiles

Please update your **ENVOYS HQ Profile** and **Field Staff Profile**. 


**Operational stage notes:**

- The two field variations to remember: the **SOT** version vs. the **HBH** version cards.
- A reconciliation column is still missing and coming soon — keep it in mind for now.
- From here you can move elements around, change status, and rename records — or open into Record Details to see vendor info and listings.

**Example Tech Ticket, shown live:** a request to let schools leave comments directly on the HBH, and for our team to leave comments back to the school — a real example of how a ticket turns into a feature.

School HBH and Field Staff HBH views are still pending. A few solid options are already on the table; we just need to land on the best one.

**Payment Tracker** is a good example of using another team's interface to find an answer yourself, instead of waiting on someone who's OOO.


## Wrap-Up

1. **Write down every question** you have. A dedicated channel will open for session-related questions so we can prepare properly for next week.
2. **If a question isn't answered here:** think it through, figure out exactly what you're trying to achieve, organize it clearly, and submit a Tech Ticket.
