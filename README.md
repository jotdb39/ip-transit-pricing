# IP Transit Los Angeles Price: What a 1G or 10G Port Costs, Whether Flat-Rate or 95th Percentile Is Cheaper, and the Setup Fees That Change the First Year

IP transit Los Angeles price lists don't compare cleanly, but the range is narrow enough to plan against. Verified quotes in this piece run from **$199/mo** for a 1G commit billed at the 95th percentile on a 10G LR handoff, up to **$1,300/mo plus a $300 setup fee** for a dedicated 1G port with 1 Gbps of DDoS mitigation attached. Three variables explain the spread: the port you're handed, the way the commit is measured, and whether scrubbing is bundled with the port or sold separately.

What follows is the LA market as currently listed, the arithmetic on flat-rate versus 95th percentile, the four costs that never appear in the headline monthly, the tunnel option for readers who don't need a physical port at all, and where SixtyNet's Los Angeles lineup fits.

> **The short version.** If you need an LA edge with a BGP session and you're not pushing a gigabit, SixtyNet's Los Angeles China Unicom-Premium plan includes free BGP session setup on a 100M port with 3× burst and 95th-percentile billing at **$2,500/year** (list $3,000). If you need a dedicated 1G or 10G commit inside a carrier hotel, you're buying a port from a transit provider in that building and budgeting $199–$1,300/mo plus setup. 👉 [See SixtyNet's Los Angeles plans and current annual pricing](https://sixtynet.net/aff.php?aff=39)

## SixtyNet's Los Angeles lineup, and which plan is actually a routing product

SixtyNet sells cloud instances in Los Angeles, not metered transit ports, so its price list reads differently from a carrier's. One plan on that list is built for routing rather than for general hosting: Los Angeles China Unicom-Premium, which lists a China Unicom Premium AS9929 path, free BGP session setup, limited BGP technical support, a 100M basic network, 3× burst, and 95th-percentile billing, with quarterly and annual payment discounts.

| Plan | Network | Included | Price | Billing |
| --- | --- | --- | --- | --- |
| Los Angeles China Unicom-Premium | AS9929, 100M basic, 3× burst, 95th billing | Free BGP session setup, limited BGP support | **$2,500/yr** (list $3,000, 17% off) | Annual, quarterly discounts listed |
| LAX-STARTER | 2G premium network, 5TB traffic | 2 core, 2G RAM, 40G NVMe, DDoS protection | **$200/yr** (list $240) | Annual |
| LAX-MEDIUM | 10G premium network, 20TB traffic | 8 core, 8G RAM, 160G NVMe, DDoS protection | **$800/yr** (list $960) | Annual |
| LAX-LARGE | 10G premium network, 40TB traffic | 8 core, 16G RAM, 320G NVMe, DDoS protection | **$1,600/yr** (list $1,920) | Annual |
| Residential-STARTER | 2G premium network, 5TB traffic | 2 core, 2G RAM, 40G NVMe, residential IP | $25/mo or $260/yr | Monthly or annual |
| Residential-MICRO | 4G premium network, 10TB traffic | 4 core, 4G RAM, 80G NVMe, residential IP | $45/mo | Monthly |
| Residential-MEDIUM | 10G premium network, 20TB traffic | 8 core, 8G RAM, 160G NVMe, residential IP | $85/mo | Monthly |
| Residential-LARGE | 10G premium network, 40TB traffic | 16 core, 16G RAM, 320G NVMe, residential IP | $165/mo | Monthly |

The residential-IP plans are on the same price list but can't serve as a transit edge: ports 80 and 443 are closed on them for IP-risk reasons, and the address isn't yours to announce. They're in the table so you can see the whole lineup and what the money actually buys. The LAX plans carry DDoS protection and a datacenter IP, which makes them usable for hosting, but they still aren't a routed port with a commit you negotiate.

👉 [Check the Los Angeles China Unicom-Premium plan's current annual price](https://sixtynet.net/aff.php?aff=39)

## What the Los Angeles market charges for an actual transit port

Two very different products both get called "1G transit in LA," and the pricing reflects it.

| Offer | Commit and handoff | Monthly | Attached to it |
| --- | --- | --- | --- |
| Xenyth 1G 95%ile | 1G commit, 10G LR | $199 ($0.199/mbit) | Dual-stack, same-day LOA; list valid at all its NA/EU sites |
| Xenyth 4G 95%ile | 4G commit, 10G LR | $599 ($0.149/mbit) | Same terms |
| Xenyth 10G flat-rate | 10G flat, 10G LR | $999 ($0.099/mbit) | Same terms |
| Xenyth 10G 95%ile | 10G commit, 40G LR4 | $1,299 ($0.129/mbit) | Same terms |
| Xenyth 100G flat-rate | 100G flat, 100G LR4 | $7,499 ($0.075/mbit) | Same terms |
| CNSERVERS 1G | 1G port | $1,300 | +$300 setup, 1Gbps DDoS, Coresite LA1 or Equinix LA1 |
| CNSERVERS 10G | 10G port | $7,500 | +$300 setup, 10Gbps DDoS, same two sites |
| CNSERVERS 20G | 20G port | $14,000 | +$5,000 setup, mitigation upgradable to 1Tbps |

Read the commit column before the price column. The $199 line is a 1G commit measured at the 95th percentile on a 10G handoff; the $1,300 line is a full 1G port with scrubbing sized to the port speed. One bills a statistical sample of your traffic, the other bills the interface. Xenyth's own note says its list applies at any location it operates in North America or Europe, so there's no separate Los Angeles premium to hunt for there.

The per-Mbit number is the one to carry between quotes: **$0.199** at 1G, $0.149 at 4G, $0.099 at 10G flat, $0.089 at 40G, $0.075 at 100G. A 10G flat-rate port at $999 costs less than two 4G 95th-percentile commits at $599 each, which is $1,198 for 8G of commit. Volume discounts are real, and they're steeper than most buyers assume when they start at the 1G row.

## Flat-rate or 95th percentile: do the math on your own peak-to-average

At the same 10G commit, the metered option costs more, not less, in this price list. Flat-rate on a 10G port is $999. A 10G 95th-percentile commit needs a 40G LR4 handoff at $1,299, or a 100G LR4 handoff at $1,399. Per Mbit that's **$0.099 against $0.129 or $0.139**, a 30% to 40% premium for the privilege of being billed on a percentile.

That flips only when your 95th-percentile sample lands far enough below the commit to matter, and if that's your traffic profile you should be buying a smaller commit instead. A 4G commit at $0.149/mbit or a 1G commit at $0.199/mbit will beat a 10G commit you never fill.

Burst isn't free overflow either. Xenyth bills burst at **150% of the Mbit rate**, so the 1G tier's $0.199/mbit becomes $0.299/mbit on anything above commit. Spiky traffic (game backends, nightly backups, patch distribution) needs that multiplier in the model. Flat traffic (VPN egress, CDN fill, bulk replication) is better served by a flat-rate port at the highest commit you can justify.

## The four costs that sit outside the monthly line

**Setup fees.** CNSERVERS charges $300 on its 1G, 2G and 10G products and **$5,000** on the 20G product. Over twelve months the $300 adds $25/mo to the effective rate; over a three-month trial it adds $100/mo. Ask what the setup covers before you assume it's waivable.

**Burst.** Covered above, but it belongs in the budget: at 150% of the Mbit rate, one bad month of overflow can cost more than the commit itself.

**Contract term.** Colocation listings in the same buildings show how long commitments run in this market. Voxility's 10U listing at CoreSite LA1 requires a full calendar year, and terminating early still leaves you paying monthly until the last day of that year or a significant termination fee. Transit contracts vary, but get the term and the early-termination language in writing before signing.

**Hands on the rack.** The same Voxility listing prices on-site support outside the standard SLA at **$5,600/hour**. That's a colocation number, not a transit one, and it sets the order of magnitude for "someone walks over and reseats the optic."

## Do you actually need a port?

Two providers in this market sell Los Angeles reach without a cross-connect, and for a lot of readers one of them is the right answer.

Pathfabric puts a dedicated Los Angeles IPv4 /32 on a remote Linux VM or physical server over WireGuard, GRE or IPIP. Port limits start at **$0.99/mo** for 100 Mbps, $1.99 for 200 Mbps, $2.99 for 500 Mbps and $3.99 for 1,000 Mbps, with outbound from **$0.038/GiB** and inbound about 70% cheaper. The metered rate is where the arithmetic bites: a terabyte of outbound is roughly $35 at that rate, and pushing a sustained 100 Mbps for a full month moves about 30,000 GiB, which works out to roughly **$1,150** in outbound alone. Those are conversions of the listed per-GiB rate, not a quote. Metered pricing wins below a few hundred gigabytes a month and loses badly above a few megabits of sustained throughput.

ThoughtWave runs BGP tunnels from a Los Angeles POP: $39/mo for a 50 Mbps commit, $79 for 200 Mbps, $99 for 1 Gbps, each splittable across up to five WireGuard tunnels with 25 prefixes per tunnel and no setup fee. Managed tiers add **$200/mo** for a /24 announcement with IRR route objects, RPKI ROA signing and route monitoring, or **$350/mo** for peering with your own public ASN, AS-SET documentation and a monthly route report. KYC runs through Stripe Identity and an LOA is issued on request. At $99/mo for a 1 Gbps commit, a tunnel undercuts a $999 10G port by an order of magnitude, and it rides commodity internet with no latency guarantee and no port to show for it.

## What you need before anyone will route your /24

- **An ASN.** Your own, or a private AS if the provider offers one on its self-service tiers.
- **A prefix.** IPv4 /24 or larger, or an IPv6 block from your own registration. Providers accept standard minimum prefix sizes per ARIN policy.
- **An IRR route object and an RPKI ROA.** Many networks filter on both before accepting your announcement.
- **An LOA.** Xenyth advertises same-day LOAs; ThoughtWave issues them on request.
- **KYC.** ThoughtWave verifies identity through Stripe Identity before activation.
- **DDoS capacity matched to the port.** CNSERVERS bundles 1Gbps of mitigation on the 1G port and 10Gbps on the 10G port, so scrubbing headroom scales with what you buy.

Dual-stack comes standard on Xenyth's sessions: every transit session includes IPv4 and IPv6. If your quote doesn't mention IPv6, ask.

## Where SixtyNet fits, and who shouldn't buy it

The China Unicom-Premium plan is the one line on SixtyNet's Los Angeles list with routing built into it. AS9929 matters if a meaningful share of your traffic goes to China, which is the main reason to pick it over a generic LA instance. Free BGP session setup removes a line item that ThoughtWave charges $200–$350/mo to manage.

The limits are equally clear. A **100M basic network with 3× burst** means peaks around 300 Mbps and a 95th-percentile sample that will sit near the port speed if you run hot. Push more than 100 Mbps month after month and the burst economics work against you; a metered port from a transit provider in the building becomes the cheaper buy. The page also states **limited BGP technical support**, so plan on running your own session, filters and communities.

Facility matters for cross-connect cost. Third-party reviews describe SixtyNet's Los Angeles footprint as Coresite LA2. Coresite LA1, Equinix LA1 and One Wilshire are where most LA transit lands, and One Wilshire alone hosts 330+ networks with Any2 connecting 235+ participants. If your gear sits in LA1, a provider in LA1 saves you a cross-connect; if your gear sits anywhere else, a tunnel sidesteps the question.

One purchase detail worth confirming: a third-party review of SixtyNet reports a **3-day money-back window**, well short of the 30 days common elsewhere. Read the terms at checkout rather than assuming.

👉 [Compare SixtyNet's Los Angeles plans before you commit](https://sixtynet.net/aff.php?aff=39)

## Picking the right shape for your traffic

One Los Angeles egress IP for a server or an office, under a few hundred gigabytes a month: a /32 tunnel, and SixtyNet's residential and LAX plans are for hosting rather than routing.

Your own ASN announcing a /24, under a gigabit: a BGP tunnel, or SixtyNet's China Unicom-Premium plan if China-bound latency is the reason you're in LA at all.

Sustained 1G or more, or latency-sensitive traffic: a dedicated port in LA1, Equinix LA1 or One Wilshire. At 10G, flat-rate at $999 undercuts 95th-percentile billing on a bigger handoff by 30% to 40% in the current Xenyth list.

Before you sign anything, confirm three things: whether the provider is in your building, what the burst multiplier is, and how long the term runs. Then check the price against the per-Mbit column rather than the headline monthly.

👉 [Start with SixtyNet's Los Angeles pricing](https://sixtynet.net/aff.php?aff=39)
