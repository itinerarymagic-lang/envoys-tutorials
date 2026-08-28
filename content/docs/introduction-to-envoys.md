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

## The New Reconciliation App

Everything lives in one place now, instead of split across tools. Login links are available in your ENVOYS HQ Profile.

## I&B Requests

Mostly relevant to other teams — it surfaces Itinerary & Budget request information across the system.

---

## Record Details: Keeping Things Organized

A few rules of thumb for how tables and records stay usable as the system grows:

- **Fields are limited per table** on purpose — tidy and organized, without losing functionality.
- **If a field can be edited, it's meant to be edited.** If it can't be, don't try — that's deliberate, not a bug.

### Linked Records

Linking records instead of retyping information keeps things organized, eliminates duplicate entries, and collects data that can be used for analysis later.

Filling out linked fields matters more here than in other systems you've used. They aren't just a record of the truth — they're *connected* to the rest of the system. Filling them in correctly saves work later and can trigger automations. For example: adding POD Members to a record can trigger automatic notifications.

### Source of Truth (SOT)

Some information needs to look different depending on who's viewing it — which means more than one field for what feels like "the same" data. For example, Operations may work from an HBH view, Enrollment Management from a separate SOT field, and another field tracks Registered Participants. These aren't duplicates — each serves a different audience.

### When a Field Needs Its Own Table

Sometimes a field would need an unpredictable number of entries — pricing is the clearest example. When that happens, the answer isn't to keep stretching one field; it's to turn that information into its own connected table. Go back to the same three questions: what thing, what information, how are they related.

---

## Buttons

Buttons on a record or interface can open another interface, run an automation, or open an external link.

---

## Action Item: Update Your Profiles

Please update your **ENVOYS HQ Profile** and **Field Staff Profile**. This also doubles as a quick attention check — everyone who does it gets a coffee, on MG & Allan.

---

## Itinerary & Budgets (I&B)

This process has been running since last season and already works well, so it's a useful preview of how the rest of these tutorials will eventually look. Not mandatory to review now, but worth it.

**The flow:** I&B Creation → Hubspot → I&B Sheet → Sent to PT → Approved → Migrating a Program.

Cross-over points like this one deserve extra attention to detail — most records are created here, and a mistake at this stage can mean significant rework.

**Operational stage notes:**

- The two field variations to remember: the **SOT** version vs. the **HBH** version cards.
- A reconciliation column is still missing and coming soon — keep it in mind for now.
- From here you can move elements around, change status, and rename records — or open into Record Details to see vendor info and listings.

**Example Tech Ticket, shown live:** a request to let schools leave comments directly on the HBH, and for our team to leave comments back to the school — a real example of how a ticket turns into a feature.

School HBH and Field Staff HBH views are still pending. A few solid options are already on the table; we just need to land on the best one.

**Payment Tracker** is a good example of using another team's interface to find an answer yourself, instead of waiting on someone who's OOO.

---

## Program Dashboard (EM)

An example of automation and system design working together: we identify the essential elements every dashboard needs, template them to cut down manual entry, and keep the template flexible enough for one-off additions.

- **Flights** is called out as an area with a lot of potential — we haven't yet looped in NB on this, so for now we're using her existing system. It'll be incorporated and optimized later.
- Some **new additions don't exist in the old App yet** (registration is one example) — expect some initial friction while the team adjusts.
- **Invoices look different by team.** Fields act as control elements — for example, the Invoice Payment Status field determines whether an invoice is even visible in the Finance interface.
- **QC Tracker** is an example of pulling elements out of individual teams' "Supreme" sheets and into the global system — no more manually updating a program in two places, which reduces mistakes and keeps things consistent.
- There are **two ways to visualize an interface**: the legacy Google Sheets-style layout, or a custom view built around the actual workflow. Both exist today, and more flexibility is coming as we move toward Softr and a fully custom front end (the Reconciliation App).

---

## S&R Interfaces

Same idea as above — Supreme sheets can be brought in, and both the legacy and new custom views are available. Also shown: the **Staff Profile Form**.

---

## Wrap-Up

1. **Write down every question** you have. A dedicated channel will open for session-related questions so we can prepare properly for next week.
2. **If a question isn't answered here:** think it through, figure out exactly what you're trying to achieve, organize it clearly, and submit a Tech Ticket.
