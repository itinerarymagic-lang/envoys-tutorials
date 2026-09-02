# Program Versions

**Primary field:** Id

Registers participant counts (students / faculty / staff) for each stage of a program — Budget, Quote, or Execution. Every program has three version records, created automatically. HBH Blocks and Associated Costs both link to one version, so all costs are always tied to the right headcount snapshot rather than the live SOT numbers.

> **Version naming in this table:** Budget · Quote · Execution — these are the live option names in Airtable. The Programs table rollup prefixes use different language (Budget | / Operations Budget | / Closing |) but they refer to the same three versions respectively.

## Fields

| Field | Type | Description |
|---|---|---|
| **Id** | formula | Auto-generated label combining the Version name and Program name. Primary display identifier. |
| **Programs** | link → Programs | Link to Program record this version belongs to. |
| **Version** | singleSelect | Which stage of the program's lifecycle this snapshot represents.<br>Options: Budget · Quote · Execution |
| **Students** | number | # of Students for Calculations |
| **Faculty** | number | # of Faculty for Calculations |
| **Staff** | number | # of Staff for Calculations |
| **Total No. of Participants** | formula | # of Participants for Calculations |
| **HBH Blocks** | link → HBH Blocks | The itinerary rows costed against this version. Each HBH Block links to exactly one version; changing this link moves the block's costs to a different stage. |
| **Pre-Ops Costs** | link → Associated Costs | The Associated Cost rows costed against this version. |

## Related tables

- **Programs** — the hub; each program has three version records
- **HBH Blocks** — itinerary rows belong to one version each
- **Associated Costs** — pre-ops cost rows belong to one version each

## Notes

- **Do not manually create or delete version records.** They are created automatically by the "Executed version created?" and "Associated costs executed version created?" automation flags on Programs.
- The participant counts here (Students / Faculty / Staff) are the inputs for cost formula calculations in HBH Blocks and Associated Costs. They are set when the version is created and updated if headcounts change before that stage is locked.
- **Budget version** is seeded from the I&B sheet at proposal stage. **Quote version** is updated throughout OPS as bookings firm up. **Execution version** is locked after the program runs.
