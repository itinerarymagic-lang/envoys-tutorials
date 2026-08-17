# ENVOYS Product Tickets — System Guide

Everything you need to know about reporting bugs and requesting features for our internal system.

---

## What this system is for

We rebuilt our entire working system, and we're still building it out. As you start using it, you will find things that are broken, things that are missing, and things that could work better.

The Ticket System is where all of that goes. Instead of sending a Slack message, an email, or mentioning it in a meeting where it gets forgotten, you submit a ticket. Every ticket is reviewed, prioritized, and tracked from submission to resolution.

**Why this matters:** requests scattered across chats, emails and channels get lost. Tickets don't. A ticket also captures the details needed to actually fix the problem — which is usually the difference between something getting solved this week versus next month.

---

## When to submit a ticket

Submit a ticket whenever:

- Something in the system is broken or behaving strangely
- You need functionality that doesn't exist yet
- Something works, but it's clunky and could be better
- A process or rule needs to change
- An automation (N8N), a portal (Softr), or a form (Jotform) isn't doing what it should
- Something seems wrong but you're not sure what — that counts too

**One issue per ticket.** If you have three unrelated problems, submit three tickets. Bundled tickets are harder to prioritize and one part inevitably gets forgotten.

**Don't worry about submitting too much.** A ticket for a small annoyance is welcome. That's what the priority system is for — small things get logged and handled in their turn, not ignored.

---

## How to submit a ticket

1. Open the ticket form (link provided by your team lead)
2. Fill out every field as accurately as you can
3. Attach a screenshot if you possibly can — it saves an enormous amount of back-and-forth
4. Submit

That's it. Your ticket goes into the review queue, gets prioritized, and you'll be able to follow its progress.

---

## Field-by-field guide

Below is every field on the form, what it means, and how to answer it well.

### Title

A single short sentence describing the issue or request. Maximum 100 characters.

Think of it as a headline: someone reading only the title should know roughly what the ticket is about.

- GOOD — "Participant emails not syncing from Jotform to OPS view"
- GOOD — "Need a filter by program on the Field Staff dashboard"
- BAD — "Broken"
- BAD — "Help"
- VERY BAD — "The thing in the system where you click and it shows the list but then it doesn't show the right one and I already tried..." (that belongs in the Description)

### Description

The full story. This is the most important field on the form, and the one that most determines how fast your ticket gets resolved. Remember, the more accurate and clear the information, the quicker the solution!

**If it's a bug, include:**

- What you were doing when it happened
- What you expected to happen
- What actually happened instead
- Steps to reproduce it — "click X, then Y, then the error appears"
- Any error message, word for word

**If it's a request, include:**

- What you need
- Why you need it — what problem does it solve, or what does it let you do?
- How you're handling it today without it

You can format this field with bold, bullet points, and lists. Use them for long descriptions. Also, you can record your screen using Loom or Komodo, explaining the issue and pin-pointing it, to later attach the video link here.

**Rule of thumb:** write it so someone who has never seen your screen could understand the problem.

### Screenshot

Optional, but genuinely the highest-value thing you can add. Attach screenshots, screen recordings, or any relevant file.

A screenshot showing an error message answers questions that would otherwise take three rounds of Slack messages. If you can include one, do.

### Type

What kind of work is this? Pick the closest match — the exact choice matters less than submitting the ticket at all.

| Type | Use it when |
|---|---|
| **Bug** | Something is broken or behaving incorrectly. It should do X, it does Y. |
| **Feature** | New functionality that doesn't currently exist and needs to be built. |
| **Enhancement** | Something that already works, but could work better. Not broken, just improvable. |
| **Change Request** | An existing requirement, behavior, or process needs to change — often because our real-world process changed. |
| **Fix** | Corrective work on an issue we already know about. |
| **Maintenance** | Routine upkeep to keep the system healthy — cleaning up data, updating lists, general housekeeping. |
| **Refactor** | Internal improvement to how something is built, with no visible change for users. Usually raised by the technical team. |
| **Performance** | Something works but is slow, inefficient, or won't scale. "This page takes 30 seconds to load." |
| **Security** | A security concern: someone can see data they shouldn't, permissions are wrong, access needs hardening. |
| **Integration** | Anything involving connections between systems — N8N automations, Softr portals, Jotform submissions, external services. |
| **Investigation** | Something seems off, but you can't tell what or why. Research is needed before anyone can act. |
| **Documentation** | Documentation, instructions, or guides need to be created or updated. |

**Not sure which to pick?** Choose **Investigation** and explain the situation in the Description. Being unsure is never a reason to skip submitting.

### Module

Which part of the system is this about? This tells us where the problem lives and helps us spot patterns — if one area generates a lot of tickets, that area needs attention.

**Team areas:**

| Module | Covers |
|---|---|
| **PT** | Program Team workflows and views |
| **EM** | Enrollment Management workflows and views |
| **OPS** | Operations workflows and views |
| **FINANCE** | Finance workflows, payments, statements |
| **S&R** | Sales & Recruitment workflows and views |
| **Field Staff** | Anything related to field staff management |
| **Schools** | School records, school-facing processes |
| **Participants** | Participant records and participant-facing processes |

**Tools and platforms:**

| Module | Covers |
|---|---|
| **N8N** | Automations — things that are supposed to run automatically |
| **SOFTR** | The Softr portal and anything users see there |
| **JOTFORM** | Jotform forms and the data they collect |
| **OTHER** | Doesn't fit any of the above |

If you pick **OTHER**, please say why in the Description. This list grows over time — if something is consistently missing, tell us and we'll add it.

### Requester

Select your own name from the list.

This is how we follow up with questions and notify you when your ticket moves forward. Tickets submitted without a requester are much slower to resolve, because there's nobody to ask when something is unclear.

### Scope

**Who is affected by this?** Answer for the situation as it actually is — not how bad it feels.

| Option | Means |
|---|---|
| **1 person** | Just you. Nobody else is hitting this. |
| **Group** | One team or role is affected. Select which one in the Teams/Group field. |
| **Single Program** | Everyone working on one specific program. |
| **Multiple Programs** | Several programs are affected. |
| **System-wide** | Everyone using the system, across all teams and programs. |

**How to decide:** ask yourself who else would notice if this were fixed. If you're the only person who uses that view, it's 1 person — even if it's very annoying for you. If every OPS person hits it daily, it's a Group.

### Teams/Group

**Only answer this if you selected "Group" in Scope.** Which team is affected?

Options: PT · Field Staff · S&R · EM · OPS · FINANCE · Participants · Schools

If Scope is anything other than Group, leave this blank.

### Blockage

**How much does this stop you from working?** This is about your ability to complete the task — not how irritating the problem is.

| Option | Means |
|---|---|
| **UI Design / Minor annoyance** | It looks wrong, is confusing, or is mildly inconvenient — but you can complete your work normally. |
| **Partial block (Workaround exists)** | It slows you down or forces you to do something manually, but there is a way to get the job done. |
| **Complete block (No workaround)** | You cannot complete the task at all. There is no way around it. |

**The key question:** *can you still finish your work?*

- Yes, easily → UI Design / Minor annoyance
- Yes, but it's painful or manual → Partial block
- No → Complete block

Please be honest here. "Complete block" means work has genuinely stopped. If you can still get it done by exporting to a spreadsheet, that's a Partial block — a real problem worth reporting, but not a stoppage.

### Time Sensitivity

**When is this genuinely needed by?** Base this on a real, external deadline — a program start date, a payment deadline, a school commitment — not on preference or how frustrated you are.

| Option | Means |
|---|---|
| **No strict deadline** | It should be fixed, but nothing breaks if it takes a while. |
| **Needed in the upcoming season** | Required before the next season begins. |
| **Within 1 to 2 weeks** | There's a real deadline in the next couple of weeks. |
| **Within 72 hours** | A real deadline in the next three days. |
| **Today** | Something time-critical is happening today and this blocks it. |

**Ask yourself:** *what actually happens if this isn't fixed by then?* If the honest answer is "nothing specific, I'd just prefer it sooner," it's not a 72-hour ticket.

Accurate answers here are what make the queue trustworthy for everyone.

### Frequency

**How often does this happen?**

| Option | Means |
|---|---|
| **Once** | It happened one time. It might have been a fluke. |
| **Intermittent / Occasionally** | It happens sometimes but not always, or you can't predict when. |
| **Consistently / Every time** | It happens every single time you do that action. |

This is genuinely useful diagnostic information. A problem that happens *every time* is usually much easier to find and fix than one that happens *sometimes* — and knowing which one it is changes how it gets investigated.

If it's intermittent, mention in the Description anything you've noticed about when it does and doesn't happen.

---

## What happens after you submit

### 1. Your ticket enters the queue

It lands in the review queue with the status **Submitted**. Nothing is required from you at this point.

### 2. It gets reviewed and prioritized

Your ticket is reviewed and assigned a priority level (P0 through P4 — explained below). Priority is calculated from the answers you gave about scope, blockage, timing, and frequency.

This is why accurate answers matter: the priority order is only as good as the information going into it. Answering honestly means genuinely urgent things surface at the top, and your own urgent tickets get taken seriously when it counts.

### 3. It gets worked on

Tickets are worked in priority order. High-priority tickets are addressed before lower-priority ones, regardless of who submitted them or when.

### 4. It gets resolved

When your ticket is solved, it's marked **Solved** with a note explaining what was done. If it can't be done, or is being deferred, you'll get a reason — tickets don't disappear silently.

---

## Priority levels

Every ticket gets one of five priority levels. Here's what each one means in practice.

| Priority | Meaning | What to expect |
|---|---|---|
| **P0 — Emergency** | Critical. Work has stopped for a large part of the organization, or something time-critical is completely blocked today. | Dropped everything, addressed immediately. |
| **P1 — Urgent** | Serious. An entire program or a hard near-term deadline is completely blocked. | Addressed as the next priority after any P0s. |
| **P2 — High** | Important. Significant impact on how people work, or a meaningful deadline is approaching. | Scheduled in the near term. |
| **P3 — Normal** | Standard. A real problem or a worthwhile improvement, without heavy impact or urgency. | Worked in the regular queue. |
| **P4 — Low** | Minor. Small annoyances, cosmetic issues, nice-to-haves. | Handled when higher-priority work allows. |

**A P4 is not a "no."** It means "logged, understood, and queued." Small tickets do get done — they're just done after the things stopping people from working.

---

## Ticket statuses

You can follow your ticket through these statuses:

| Status | Means |
|---|---|
| **Submitted** | Received, waiting for review. |
| **Accepted** | Reviewed, confirmed as valid, and queued for work. |
| **In-Progress** | Actively being worked on right now. |
| **Solved** | Done. Check the resolution note for what was changed. |
| **Postponed** | Valid and accepted, but deliberately deferred — usually because it depends on other work being finished first. It stays in the queue. |
| **Declined** | Not going to be done. A reason is always given — commonly a duplicate of an existing ticket, already solved elsewhere, or something better handled outside the system. |

---

## How to write a ticket that gets solved fast

**Be specific.** "The list is wrong" could mean twenty things. "The participant list in the OPS view shows participants from last season instead of the current one" can be acted on immediately.

**Include a screenshot or video explanation.** Genuinely the single highest-impact thing you can do.

**Give steps to reproduce.** Walk through it click by click — "open the OPS view, filter by program, click the participant name, the error appears." If someone can reproduce it, they can fix it.

**Say what you expected.** Sometimes the system is doing exactly what it was built to do, and the real issue is that it was built on a wrong assumption. Stating what you expected surfaces that immediately.

**Answer the four scoring questions honestly.** Over-stating urgency doesn't get your ticket done faster in the long run — it makes the whole queue less trustworthy, including for your genuinely urgent tickets.

**One issue per ticket.** Always.
