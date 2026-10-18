# vultr database pricing: every managed database plan from $14.96 to $1,440 a month, and where AWS RDS, Cloud SQL and Azure SQL actually win

Vultr's managed databases start at **$14.96 per month** — a 1 vCPU / 1 GB High Performance node billed at $0.0205 per hour — and run up to $1,440 per month for a 16 vCPU / 64 GB Optimized Cloud Compute node. That's the entire range: 12 plans across two node families, running PostgreSQL, MySQL, or Redis, with automated backups included and hourly billing throughout.

Which of those 12 plans you actually need is a separate question, and so is whether Vultr is the cheapest option at your size. The honest answer: Vultr undercuts AWS RDS, Azure SQL Database, and Google Cloud SQL on most comparable tiers, sometimes by more than 80%, but it loses on at least two specific sizes that matter to plenty of people. Both sides of that are below, with numbers.

> **Short on time?** For a small production app, the HP 1 vCPU / 2 GB plan at **$30/month** is the sensible default — 1 GB of RAM gets tight fast once MySQL or PostgreSQL has real queries to cache. Weekend project? The $14.96 entry plan already includes automated backups and patching. 👉 [Check current Vultr managed database plans](https://bit.ly/VulTR)

## The full Vultr managed database price list

Vultr's managed database pricing is simple once you know the two families: HP (High Performance) covers the small and mid sizes, OCC (Optimized Cloud Compute) covers 4 GB of RAM and up. All 12 published plans are in the table below. Prices are on-demand rates for the ewr (New Jersey) region, and the monthly column is the hourly rate times a typical ~730-hour month.

| Plan | vCPU | RAM | Hourly | Monthly |  |
| --- | --- | --- | --- | --- | --- |
| HP 1 vCPU / 1 GB | 1 | 1 GB | $0.0205 | $14.96 | [ Get started](https://bit.ly/VulTR) |
| HP 1 vCPU / 2 GB | 1 | 2 GB | $0.0411 | $30.00 | [ Get started](https://bit.ly/VulTR) |
| HP 2 vCPU / 4 GB | 2 | 4 GB | $0.0822 | $60.01 | [ Get started](https://bit.ly/VulTR) |
| HP 4 vCPU / 8 GB | 4 | 8 GB | $0.1644 | $120.01 | [ Get started](https://bit.ly/VulTR) |
| HP 6 vCPU / 16 GB | 6 | 16 GB | $0.3288 | $240.02 | [ Get started](https://bit.ly/VulTR) |
| HP 8 vCPU / 32 GB | 8 | 32 GB | $0.6575 | $479.97 | [ Get started](https://bit.ly/VulTR) |
| HP 12 vCPU / 48 GB | 12 | 48 GB | $1.0521 | $768.03 | [ Get started](https://bit.ly/VulTR) |
| OCC 1 vCPU / 4 GB | 1 | 4 GB | $0.1233 | $90.01 | [ Get started](https://bit.ly/VulTR) |
| OCC 2 vCPU / 8 GB | 2 | 8 GB | $0.2466 | $180.02 | [ Get started](https://bit.ly/VulTR) |
| OCC 4 vCPU / 16 GB | 4 | 16 GB | $0.4932 | $360.04 | [ Get started](https://bit.ly/VulTR) |
| OCC 8 vCPU / 32 GB | 8 | 32 GB | $0.9863 | $720.00 | [ Get started](https://bit.ly/VulTR) |
| OCC 16 vCPU / 64 GB | 16 | 64 GB | $1.9726 | $1,440.00 | [ Get started](https://bit.ly/VulTR) |

Three things worth pulling out of that table:

- The published table prices nodes, not engines. PostgreSQL, MySQL, and Redis run on the same node sizes at the same rates.
- Automated backups come included. On Vultr's regular compute instances, backups add an extra 20% of the server price, so this is a genuine cost difference between the two product lines.
- The OCC family has no small plans. Its cheapest node, 1 vCPU / 4 GB at $90.01, costs six times the entry price. If a "$90 database" quote scared you off, you were looking at the wrong family.

## HP vs OCC: the difference most price tables skip

HP is the mainstream family and the cheaper one at every overlapping size; OCC exists mainly for the sizes HP doesn't offer. That single sentence resolves most of the confusion in Vultr's lineup, but the details are worth knowing.

HP runs from 1 vCPU / 1 GB up to 12 vCPU / 48 GB, priced $14.96 to $768.03 per month. OCC starts at 4 GB of RAM and stretches to 16 vCPU / 64 GB — and that top size only exists as OCC. If your database needs more than 48 GB of RAM, the OCC family is the only way to get there.

The two families overlap at 8 vCPU / 32 GB, and the gap there shows the positioning clearly: HP costs $479.97 per month, OCC costs $720.00. Same vCPU count, same RAM, roughly 50% more for the OCC badge. The published pricing data doesn't spell out what that extra money buys in hardware terms.

Practical rule: if your workload fits under 48 GB of RAM, HP covers it for less. OCC earns its place when you need the bigger sizes or the 16-core top end.

## How Vultr bills managed databases

Hourly, on-demand, with no commitment. The $14.96 entry plan is simply $0.0205 multiplied by 730 hours. Run a cluster for half a month and you pay roughly half the monthly figure. Vultr's published billing model lets you start and stop at any time — though "stopping" a database really means deleting it, which the fine print section below covers.

Every figure in this article is the ewr (New Jersey) on-demand rate from the published lineup. Other regions can price differently, so treat the number shown on the deployment screen as the final word for your location.

On long-term commitments: 1–3 year committed-use options show up in third-party pricing write-ups for Vultr databases, but no published discount percentages exist in the current data. Budget around the on-demand numbers and treat any commitment discount as a bonus rather than a plan.

Want to sanity-check these figures against the live lineup? 👉 [Open Vultr's managed database plans](https://bit.ly/VulTR)

## Vultr vs AWS RDS, Azure SQL, and Google Cloud SQL

On most comparable tiers Vultr is cheaper — dramatically so at the high end — but it loses on at least two sizes. The table below uses CloudPriceCheck's September 2026 on-demand comparison, which matched Vultr plans against rivals at similar sizes in default regions (USD, monthly):

| Comparable tier | Vultr Managed DB | AWS RDS | Azure SQL Database | Google Cloud SQL |
| --- | --- | --- | --- | --- |
| 1 vCPU / 1 GB | $14.96 (HP) | — | — | $25.55 (f1-micro class) |
| 2 vCPU / 8 GB | $180.02 (OCC) | $215.35 (db.m6idn.large) | — | — |
| 4 vCPU / 16 GB | $360.04 (OCC) | $654.81 (db.m6id.xlarge) | — | — |
| 8 vCPU / 32 GB | $479.97 (HP) | $275.94 (db.m5.2xlarge) | — | — |
| 12 vCPU / 48 GB | $768.03 (HP) | — | $5,334.84 (12 vCore) | — |
| 16 vCPU / 64 GB | $1,440.00 (OCC) | $8,376.90 (db.m5.4xlarge) | $1,560.21 (16 vCore) | — |
| 1 vCPU / 4 GB | $90.01 (OCC) | — | $36.50 (1 vCore) | — |

A dash means the comparison didn't include that pairing.

The 16 vCPU / 64 GB row is the eye-opener: AWS's db.m5.4xlarge lands at $8,376.90 per month against Vultr's $1,440 — an 82.8% gap in the compiled data. Azure's 12 vCore tier at $5,334.84 versus Vultr's $768.03 is similarly lopsided, and even the close matchups go to Vultr (7.7% cheaper than Azure at the top size).

Now the rows where Vultr loses, because price-list articles tend to quietly skip these:

- **8 vCPU / 32 GB:** AWS's db.m5.2xlarge at $275.94 undercuts Vultr's HP 8c32g at $479.97 by 42.5%. If that's your target size, RDS deserves a quote before you commit.
- **The 4 GB class:** Azure's 1 vCore plan at $36.50 beats Vultr's OCC 1c4g at $90.01. Vultr's cheapest 4 GB node is actually the HP 2 vCPU / 4 GB at $60.01, which narrows the gap but doesn't close it.

One caveat on the Cloud SQL numbers: the compiled pairings matched Vultr's 8 vCPU / 32 GB ($479.97) against a 16 vCPU / 60 GB Cloud SQL instance ($817.60), and Vultr's 16 vCPU / 64 GB against a 32 vCPU / 208 GB Cloud SQL node. The GCP sides of those pairings are bigger machines, so read those gaps with suspicion. Rival prices also bundle different tooling and support scopes, and everything depends on region. Treat the table as a starting filter, then price your exact size before deciding.

## Managed database or self-hosted on Vultr?

Self-hosting on Vultr starts around $7.20 per month all-in; managed starts at $14.96. The roughly $7.76 difference is what automated patching, failover, and backups cost you.

The math, from published prices: the cheapest viable self-host route is a High Frequency compute instance — 1 vCPU, 1 GB RAM, 32 GB NVMe — at $6 per month. Backups on Vultr compute add 20% of the instance price, so $7.20 all-in. You install MySQL or PostgreSQL yourself, apply updates yourself, and if the server dies at 3 a.m., recovery is your problem. Snapshots, if you use them, add $0.05/GB per month.

The managed HP 1 vCPU / 1 GB node at $14.96 includes automated backups, patching, and failover out of the box, with read replicas available if reads become the bottleneck.

Honest take: for a hobby project or a dev environment, self-host and pocket the difference. For anything with real users, that $7.76 buys you out of being the on-call DBA — roughly one coffee a week to never patch a production database at midnight again.

If that trade sounds right, 👉 [start a managed database from $14.96 a month](https://bit.ly/VulTR)

## The fine print before you deploy

Billing quirks and account friction are the two things that catch new Vultr users, so here they are up front.

- **An idle database still bills.** Vultr charges running resources whether or not you use them, and CheckThat's April 2026 billing analysis documents that stopped compute instances keep charging until they're destroyed entirely. Apply the same discipline to databases: when a project ends, export a backup and delete the cluster.
- **Compute-side extras add up.** If your app server also lives on Vultr: backups add 20% of the server price, extra reserved IPv4 addresses cost $3/month, snapshot storage runs $0.05/GB/month, and bandwidth overages bill at $0.01/GB.
- **New accounts can hit verification friction.** The same roundup documents users being asked for government ID and card photos after payment, with resolution taking days. Don't schedule a launch ten minutes after signing up.
- **The platform's reputation is polarized.** Trustpilot sits at 1.8/5 across 541 reviews (68% one-star), while G2's more technical audience rates Vultr 4.3/5. The low scores cluster around the billing surprises and verification delays above; hands-on users who like the DIY model rate it far higher.

None of this changes the database prices themselves. It changes your total, which is the number that actually matters.

## Vultr managed database pricing FAQ

**Is there a free Vultr managed database?**
No. The published lineup has 12 paid plans and starts at $14.96/month. Free options exist elsewhere on Vultr's platform, but a managed database isn't one of them in the current lineup.

**Which database engines does Vultr support?**
PostgreSQL, MySQL, and Redis, per Vultr's published managed database data. The engine choice doesn't change the node price.

**Do prices change by region?**
They can. Every figure in this article is the ewr (New Jersey) on-demand rate; confirm the price shown at deployment time for your region.

**Are backups included?**
Yes — automated backups come with managed databases. On Vultr's compute instances, by contrast, backups add 20% to the bill.

**Can I get a discount for a long-term commitment?**
Committed-use options appear in third-party pricing summaries, but no public discount percentages for managed databases could be confirmed. Budget around on-demand rates.

## Which Vultr managed database plan should you actually get?

- **Weekend project or learning:** HP 1 vCPU / 1 GB at $14.96/month.
- **Small production app (most readers):** HP 1 vCPU / 2 GB at $30/month. RAM is the first wall MySQL and PostgreSQL hit.
- **Growing app:** HP 2 vCPU / 4 GB at $60.01 or HP 4 vCPU / 8 GB at $120.01, plus a read replica if reads become the bottleneck.
- **8 vCPU / 32 GB on a tight budget:** run the numbers against RDS first — that's the one size where the compiled data shows AWS cheaper ($275.94 vs $479.97).
- **More than 48 GB of RAM:** the OCC family is your only option, from $90.01 up to $1,440/month for 16 vCPU / 64 GB.

Two checks before you click: pick the region closest to your users and confirm the price on the deploy screen, since the figures here are New Jersey rates. And ask yourself whether you need managed at all — a $6 self-hosted instance remains a perfectly good answer for throwaway projects.

Everything else points the same way: 👉 [pick your region and deploy a Vultr managed database](https://bit.ly/VulTR)
