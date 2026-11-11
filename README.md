# From Manual Trackers to Decision Inputs: Operational Reporting in a Jeddah Construction Office

**Question:** how does an office that runs several construction projects at once turn scattered trackers into numbers a CEO can act on?
**Short answer:** consolidate the inputs, automate the repetitive checks, and refuse to present any figure that hasn't been tested against its source.

This is a written case study of my day job, plus a public pipeline showing the same habits on open data. It contains no employer data.

## The moment that changed how I report

I work in the CEO's office of a Jeddah construction contractor, where I maintain the Power BI and Excel reporting the CEO uses to follow budget, schedule and resources across 5–6 concurrent projects.

One review stuck with me. A project showed a cost variance, and the question that followed was about equipment sitting idle on site. The answer was in the business already. It was just spread across separate trackers kept by different people, in different formats, updated on different days. Pulling it together by hand took time the decision didn't have.

The lesson was simple. A variance is only useful if the inputs behind it are current, consistent and in one place. Otherwise the meeting becomes a debate about whose spreadsheet is right.

## The automation

The most repetitive part of that problem was HR data. Timesheets, leave and end-of-service records were tracked separately and checked by hand every cycle. I rebuilt the process in Excel and Power Query: one refreshable model that pulls the trackers in, standardises them, runs validation checks and produces a single self-serve view.

It saves **20–25 hours a month** of manual tracking. More importantly, staffing and leave figures now reach the resource-allocation conversation clean and on time, instead of arriving late or with caveats. The anonymised workflow, controls and an illustrative schema are in [`/hr-automation`](hr-automation/README.md).

## The reliability habit

The automation made me stricter about one rule: **no result is presented until it has been tested against its source.** At work that means row counts and totals reconciled back to the original trackers before anything goes into a report.

I apply the same rule in public. [`/sama-spending-pulse`](sama-spending-pulse/README.md) links to my pipeline on 307 weeks of Saudi Central Bank point-of-sale data (May 2020 to March 2026). It has 23 automated checks, including sector totals summing to the national total and recomputed week-on-week changes matching SAMA's published figures.

## Intended use: an Allahabad briefing

I was born in Allahabad (Prayagraj). My planned next step, not yet delivered, is to adapt this reporting approach into a short briefing for a small business there that is considering Gulf trade. It would carry three items:

1. **PortWatch disruption flag:** a simple signal from IMF PortWatch vessel-transit data (built on my [Red Sea Shock Control Tower](https://github.com/amirator/red-sea-shock-control-tower)) showing whether the Bab el-Mandeb route is currently disrupted.
2. **Payment-cycle window:** a note on when cash goes out and comes in, so shipment timing doesn't collide with a tight month.
3. **Capacity-check note:** a short check on whether the business has the people and stock to take on an order before committing.

## Limitations

- The workplace sections are a first-person account. No company data, names or figures beyond those stated are published, so they can't be independently reproduced here.
- The 20–25 hours a month has no formal baseline published here.
- The Allahabad briefing is a plan, with no client or result yet.

Licensed under MIT. See [LICENSE](LICENSE).
