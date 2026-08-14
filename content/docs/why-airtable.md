# Airtable & Database Basics

  ## 1. The Problem with Spreadsheets

  **Great for:** Quick lists, calculations, financial models, and one-off analysis.

    **The breaking point:** As information and teams grow, spreadsheets become harder to control. Technically, a spreadsheet can do what Databases do, but depend on extremely complex formulas and break very easily.

      **Common pain points:**

      - Updating the same information in multiple places.
      - Accidentally deleting or overwriting formulas.
      - Multiple people editing the same file creates confusion.
      - Different versions of the "same" spreadsheet.
      - Difficult to connect information across different sheets.

      **The key issue:** A spreadsheet mostly sees **cells and tables**. It doesn't inherently understand what the information *means* or how different pieces of information relate to each other.

      ---

      ## 2. What Is a Database?

      **Spreadsheet = A flat whiteboard**
      You can write almost anything anywhere. It's flexible, but the whiteboard doesn't really understand what you've written.

      **Database = A smart filing cabinet**
      A database is an organized system for storing information so that it can be easily found, connected, updated, and used and connected by other systems.

        For example: **Programs** → **School** → **Tasks** → **Field Staff**

          The database understands that a particular task belongs to a particular school, which belongs to a particular program.

            ### The magic of relationships

            Instead of copying "PACE Academy" into 20 different places, we can create **one client record** and connect everything to it. If the client's name changes, we update it once.

              **One source of truth → many connected uses.**

              ---

              ## 3. Spreadsheet vs. Database

              | | Excel / Google Sheets | Database |
              |---|---|---|
              | **Structure** | Flexible | Structured |
              | **Data rules** | Easy to enter anything | Fields have defined types and rules |
              | **Connections** | Usually formulas/lookups | Built-in relationships |
              | **Duplication** | Often common | Designed to minimize duplication |
              | **Best for** | Calculations, analysis, charts | Systems, workflows, connected information |
                | **Collaboration** | Can become difficult at scale | Designed around shared, structured data |

                  **Important:** Databases aren't simply "better spreadsheets." They solve a different problem.

                    ---

                    ## 4. The Trade-Off of Traditional Databases

                    Databases are powerful, but traditionally they haven't been very approachable. SaaS and AI have lowered the entry barrier. However, we're not there....yet.

                      They often:

- Require technical knowledge or coding, such as SQL. (Developers)
  - Present information in technical interfaces. (Backend)
  - Require IT or developers to build applications around them. (Front End)
  - Take more planning and structure than a simple spreadsheet.

  So we've historically had a choice:

  **Easy to use → Spreadsheet**
  **Powerful and structured → Database**

  ---

  ## 5. Enter Airtable: The Best of Both Worlds

  **Airtable combines the familiarity of a spreadsheet with the structure of a database.**

  ### Familiar interface

  It uses the familiar:

  - Rows
  - Columns
  - Tables
  - Filters
  - Sorting

  So if you know Excel or Google Sheets, much of Airtable will feel familiar.

  ### Database brain

  Underneath the spreadsheet-like interface, Airtable understands:

  - What type of information you're storing.
  - Which records are related.
  - What rules the data should follow.
  - How information can be connected and reused.

  ### Click-to-link

  Instead of complicated formulas or VLOOKUPs, you can connect records directly.

    **Program → School → Task**

    The relationship is built into the data.

    ---

    ## 6. One Database, Multiple Views

      One of Airtable's biggest advantages is that **different people can look at the same information in different ways.**

      For example:

**Finance** → Grid view, like Excel
  **HQ Staff** → Calendar view
  **Operations** → Kanban board

  These aren't separate copies of the information. **Everyone is looking at the same underlying data.**

  This means we can give each team the view that makes the most sense for them without creating multiple versions of the truth.

  ---

  ## 7. The Airtable Mental Model

  There are five concepts to understand:

  ### Base
  The overall database/system.

  ### Table
  A category of "things". **Programs, Schools, Staff Assignments, Program Land Price per Student**

    ### Record
    One individual thing. **One Program, one School, one Staff Assignment**

      ### Field
      A piece of information about that thing. **Name, status, start/end date, # of participants, POD Members**

        ### Relationship
        A connection between things. **A Field Staff Assignment belongs to a Program. A Program belongs to a School.**

        ---

        ## 8. Why We're Using Airtable

        The goal isn't to make everyone a database expert. The goal is to create a system that is:

        - **Centralized** — information lives in one place.
        - **Connected** — related information is linked.
        - **Consistent** — data follows defined rules.
        - **Flexible** — everyone can eventually create the views they need.
        - **Automated** — repetitive work can be handled automatically through the use of different internal and external tools.
        - **Accessible** — people can use the system without knowing how to code.

        ### The mindset shift

        Instead of asking:

        > **"How can my spreadsheet look pretty and organized?"**

        Start asking:

> **"What "things" are we tracking?"**

  Then:

> **"What information do we need about each thing?"**

  And finally:

> **"How are those things related?"**

  That's the database mindset.

  ---

  ## The One-Minute Summary

  **Excel / Google Sheets:**
    > A flexible tool for working with tables, calculations, and analysis.

    **Database:**
      > A structured system for storing, organizing, and connecting information.

        **Airtable:**
          > A database that gives us the familiar experience of a spreadsheet, while adding relationships, structure, multiple views, and automation.

            **The goal:**
              > **One source of truth, connected information, and a system that can grow with the company.**
