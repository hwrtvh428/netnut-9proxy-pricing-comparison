# NetNut Review: Real Plan Pricing, the Compliance Questions, and a Cheaper Per-IP Alternative

Most NetNut reviews answer the wrong question. They list feature bullets, quote the "85M+ IPs" line from the homepage, and end with a verdict that says "reliable but expensive." That doesn't help anyone who is actually trying to decide whether to wire $99, $999, or $3,750 a month to a proxy vendor.

What people searching this term usually want to know is narrower: does the network work on my targets, what does it cost once the introductory "from $X/GB" disappears, and is this company safe to hand a prepayment to. The first two have clean answers. The third got considerably messier this year, and a lot of content written before the summer skips it entirely.

Short version: NetNut's residential network is real and its published benchmarks are competitive. Its entry price is high, its billing model assumes steady monthly volume, and its name now appears in a federal enforcement story that you should at least read before signing an annual contract. If your workload is better described in IP counts than in gigabytes, the per-IP model discussed further down is worth pricing before you commit to anything.

## What NetNut actually sells

NetNut is a proxy provider founded in 2018, headquartered in Israel, with a rotating residential network advertised at 85M+ IPs across roughly 195 countries, plus a mobile pool of about 5M IPs. Alongside rotating residential it sells static residential (ISP) proxies, datacenter proxies, a website unblocker, and two scraper APIs, one for SERP data and one for B2B contact data.

The architectural pitch is one-hop connectivity. Instead of routing your request through a consumer's device before it reaches the target site, NetNut claims traffic enters through ISP-level infrastructure operated by its network partner, DiViNetworks. In practice that's the difference between a residential proxy that feels like a datacenter proxy with a residential IP attached and one that doesn't add a second or two of latency per request.

One independent directory that benchmarks providers lists NetNut at 4.3 stars with a 99.2% success rate and an average response time around 880ms. Treat cross-provider benchmark numbers as directional, since success rates depend heavily on your target list, but those figures are not outlier claims.

## NetNut pricing: the tiers they publish

The rotating residential plans are charged by bandwidth with a monthly commitment. Here is the published structure, both monthly and billed annually:

| Plan | Data included | Monthly | Effective per GB | Annual (billed yearly) | Annual per GB |
| --- | --- | --- | --- | --- | --- |
| Starter | 28 GB | $99 | $3.53 | $84/mo | $3.00 |
| Advanced | 72 GB | $249 | $3.45 | $210/mo | $2.93 |
| Production | 150 GB | $499 | $3.32 | $423/mo | $2.82 |
| Semi-Pro | 350 GB | $999 | $2.85 | $850/mo | $2.43 |
| Professional | 800 GB | $1,999 | $2.49 | $1,696/mo | $2.12 |
| Master | 2 TB | $3,750 | $1.87 | $3,180/mo | $1.59 |

Every tier includes city and state targeting, API access, IP whitelisting, and a dedicated account manager. The gap between the cheapest and most expensive per-GB rate is roughly 2.2x, which tells you the pricing is really a volume commitment system wearing a plan-name costume.

Other product lines are quoted differently and are harder to compare cleanly. Aggregator listings put static residential entry pricing at around $3.82, mobile around $3.82, datacenter from about $0.45, the website unblocker from $4.80, SERP scraper API from $0.36, and B2B data scraper API from $1.50. One review of the service reported static residential running from $99/month for a 7 GB allocation up to $4,500/month at the 1 TB tier, which is a very different price shape from the rotating product. If you want static IPs, read that plan page yourself rather than trusting a summary table.

There is no self-serve free trial. NetNut's own documentation says you sign up, then contact sales through WhatsApp, Telegram, Skype, email, or live chat, explain your product type, target domains, use case, and required bandwidth, and get a trial account set up after review. A reviewer who tested this process described having to fill in a questionnaire before the chatbot would engage, and waiting 20 minutes without a human reply. That may be an artifact of giving flippant answers, but the funnel shape is clear: they qualify you before they let you test.

## The 2026 problem worth reading about

In July 2026, Google, the FBI and partners announced a joint disruption of a residential proxy network tracked as "NetNut," also recorded as "Popa." The reporting describes a network built on compromised consumer devices, enrolled largely through bandwidth-sharing apps that pay users for "unused internet," and used to relay password-spraying, account takeover attempts, ad fraud, and Mirai-variant DDoS traffic. The disruption involved disabling Google accounts used for command and control, sharing infrastructure indicators with platforms and law enforcement, and using Play Protect to disable apps carrying the affected code.

Separately, a security directory entry for netnut.com (a domain distinct from the provider's main netnut.io site) shows a page title reading "Seized by the Federal Bureau of Investigation," with nameservers under fbi.seized.gov and a WHOIS record updated in August 2026. Meanwhile, independent scraping-industry research describes the provider's IP sourcing as a border-router co-option model run through a partner company called DiviNetworks, with GRE tunnels and policy-based routing configured on partner ISP routers. That description matches NetNut's own marketing, which credits DiViNetworks as its global network partner. One case study from that research claims a single university's entire /16 address allocation was observed generating proxy exit traffic.

Here is what I can and cannot confirm. The enforcement reporting and the seizure notice are both publicly verifiable. I cannot confirm that the network named in the enforcement action is the same legal entity that sells plans on the provider's main site, and you should notice that NetNut's own positioning runs in the opposite direction: its sales pages argue that sourcing residential IPs business-to-business "alleviates issues with consents, personal data and other compliance hurdles." Both framings exist in public. They have not been reconciled by anyone I could find, and I'm not going to guess which one describes the inventory you'd be buying.

What that means practically depends on who you are. If you're buying for a company with procurement rules and a legal team, "who owns the IPs and how were they acquired" stops being a footnote and becomes the question, and you now need a written answer from the vendor rather than a blog post. If you're a solo developer or a small agency, the relevant risk is simpler: don't prepay twelve months of anything to a vendor whose name shows up in a botnet takedown headline until someone with authority says the two entities are unrelated. Buy monthly. The annual discount is not worth the counterparty risk you can't currently price.

## What customer reviews say

Third-party scores for NetNut are decent and slightly overstated in the way directory scores usually are. One tech-press review cites 4.7/5 on Trustpilot. Software Advice user reviews sit between 4.5 and 5.0 across individual categories, with recurring praise for geo-targeted testing, IP rotation reliability, and account management responsiveness. The complaints cluster in the same two places every time: price, which reviewers describe as higher than comparable options, and support response speed on live chat during peak hours. One Software Advice reviewer also flagged the service as less suited to sneaker botting and streaming, where rotation flexibility and location coverage matter more than raw throughput.

## Who NetNut is right for, and who it isn't

NetNut makes sense if you're running predictable, sizeable monthly volume, want city-level or state-level targeting as a standard feature, need a named account manager and integration support, and are doing ad verification, SERP monitoring, price aggregation, or brand protection where latency and uptime claims actually affect your pipeline. It also makes sense if you need written compliance documentation to get a purchase approved.

It's the wrong tool in a few other situations. If your traffic is spiky, bandwidth billing hurts twice, once when you overcommit and once when you undercommit and burn a tier you didn't use. If your main need is holding hundreds of logged-in sessions on stable endpoints for days, rotating residential is the wrong product category regardless of vendor. And if you want to test before paying, you'll be filling in a sales form rather than clicking a trial button.

## The alternative model: pay per IP instead of per GB

Here's the part that tends to change buying decisions. Two teams can spend the same money on proxies and one of them is using the wrong billing unit.

Per-GB billing assumes your usage grows with data volume. That's true for heavy page scraping. It's false for anyone running many long-lived sessions on a moderate amount of traffic: account management, multi-profile browser work, regional QA, anything where you care about how many clean endpoints you hold rather than how many gigabytes pass through them. In that scenario you're paying for a meter that doesn't describe your problem.

9Proxy is built around the opposite model. It sells residential access two ways: by IP, where you buy a fixed number of residential IPs with unlimited bandwidth and unused IPs that never expire; and by GB, where you pay only for traffic with unlimited endpoints and 180-day validity on the balance. Targeting on the GB side goes down to country, state, city, ZIP, and ISP. Protocols are HTTP, HTTPS, and SOCKS5, so the usual automation stacks drop in without adapters.

The advertised network is 20M+ residential IPs across 90+ countries. That is a materially smaller pool than NetNut's claimed 85M+, and you should weigh that honestly: on aggressively protected targets, pool size and exit-node freshness show up as success rate. One review site listing the published per-country counts has the deepest pools in the US (572,600), Canada (530,800), France (490,090), the UK (446,080), and Germany (385,590), with notably thinner coverage in parts of Asia. If your targets are US or Western European, that's fine. If you need a specific Southeast Asian city at scale, test first.

👉 [Check current 9Proxy per-IP and per-GB packages](https://bit.ly/9-Proxy)

## 9Proxy pricing in full

Residential by IPs. You buy a block of endpoints, bandwidth is unlimited, and IPs stay valid until used. Sessions on individual IPs run somewhere between a few hours and roughly 24 hours depending on the address.

| Package | Price per IP | Total | Purchase |
| --- | --- | --- | --- |
| 100 IPs | $0.24 | $24 | [Buy the 100 IP starter pack](https://bit.ly/9-Proxy) |
| 500 IPs | $0.144 | $72 | [Buy 500 residential IPs](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus | $0.084 | $126 | [Buy the 1,000 + 500 bonus bundle](https://bit.ly/9-Proxy) |
| 2,500 IPs | $0.084 | $210 | [Buy the 2,500 IP package](https://bit.ly/9-Proxy) |
| 5,000 IPs | $0.072 | $360 | [Buy the 5,000 IP package](https://bit.ly/9-Proxy) |
| 15,000 IPs | $0.048 | $720 | [Buy the 15,000 IP package](https://bit.ly/9-Proxy) |
| 25,000 IPs | $0.035 | $863 | [Buy the 25,000 IP package](https://bit.ly/9-Proxy) |
| 50,000 IPs | $0.029 | $1,438 | [Buy the 50,000 IP package](https://bit.ly/9-Proxy) |
| 100,000 IPs (Business) | $0.023 | $2,300 | [Buy the 100,000 IP business pack](https://bit.ly/9-Proxy) |
| 200,000 IPs (Business) | $0.021 | $4,140 | [Buy the 200,000 IP business pack](https://bit.ly/9-Proxy) |
| 500,000 IPs (Business) | $0.018 | $8,625 | [Buy the 500,000 IP business pack](https://bit.ly/9-Proxy) |

Residential by GB. You pay per gigabyte, generate as many proxy endpoints as you want, and pick rotating or sticky sessions.

| Package | Rate | Total | Validity | Purchase |
| --- | --- | --- | --- | --- |
| 5 GB | $3.00/GB | $15 | 180 days | [Buy 5 GB of residential traffic](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | $2.10/GB | $105 | 180 days | [Buy the 50 GB traffic pack](https://bit.ly/9-Proxy) |
| 100 GB | $1.50/GB | $150 | 180 days | [Buy the 100 GB traffic pack](https://bit.ly/9-Proxy) |
| 200 GB | $1.00/GB | $200 | 180 days | [Buy the 200 GB traffic pack](https://bit.ly/9-Proxy) |
| 1,000 GB | $0.80/GB | $800 | 180 days | [Buy the 1,000 GB traffic pack](https://bit.ly/9-Proxy) |
| 2,000 GB | $0.75/GB | $1,500 | 180 days | [Buy the 2,000 GB traffic pack](https://bit.ly/9-Proxy) |
| Enterprise GB | From ~$0.68/GB at the 10,000 GB tier | Custom | No expiry | [Request Enterprise GB pricing](https://bit.ly/9-Proxy) |

Bundle packages. IPs plus traffic in one purchase, for workloads that need both stable endpoints and flexible rotation.

| Bundle | Contents | Price | Purchase |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | [Buy the Starter bundle](https://bit.ly/9-Proxy) |
| Popular | 1,500 IPs + 50 GB | $180 | [Buy the Popular bundle](https://bit.ly/9-Proxy) |
| Pro | 5,000 IPs + 500 GB | $720 | [Buy the Pro bundle](https://bit.ly/9-Proxy) |

Two things to note about these numbers. The IP-based and bundle pricing reflects a pricing update that took effect on June 1, 2026, which raised those tiers while leaving GB-based pricing untouched. Older reviews still quote the previous rates, so if you see a table showing 100 IPs at $20, you're looking at stale data. There is no monthly subscription attached to any of these packages; you buy a balance and spend it. Unused IPs don't expire, and GB balance is valid for 180 days.

## The cost math, on a workload you might actually have

Take a pipeline that pushes roughly 200 GB a month through rotating residential IPs.

At NetNut, the smallest published tier that covers 200 GB is Semi-Pro at 350 GB for $999 a month. You'd be paying for 150 GB you don't use. Billed annually it's $850 a month, or $10,200 for the year.

At 9Proxy, the 200 GB pack is $200, with 180 days of validity, so the same $200 covers roughly six months at that rate if your usage is steady.

That is a real gap, roughly five times on list price. But it isn't a free lunch, and the honest reading is this: NetNut's pool is advertised at more than four times the size, its benchmarks are publicly documented, it has account management and enterprise procurement paperwork, and its IP sourcing story is at least designed to survive a compliance review, even if the 2026 enforcement story complicates that. 9Proxy is cheaper per unit and its per-IP model solves a problem bandwidth billing can't. Cheaper and better are different claims, and which one you need depends on how hard your targets are.

## What to watch out for with 9Proxy before you buy

It's residential only. There's no datacenter line and no separate ISP/static product, so if part of your stack needs long-lived stable IPs of a different class, you're running a second vendor alongside it.

There's no free trial. The smallest entry point is $15 for 5 GB or $24 for 100 IPs, which is cheap enough to function as a test, but you are paying to find out.

The dead-IP replacement window is short. If a proxy fails within the first 60 seconds of activation, you get credit back automatically, and that's a better policy than most providers offer. Beyond that window, a dead IP is a manual support conversation, so an IP that dies at hour two is money you spent. With unlimited-bandwidth per-IP billing, that's the tradeoff you're accepting: no traffic meter, but you're buying addresses rather than guaranteed working addresses.

Availability has been inconsistent. Multiple review outlets documented a service blackout that began around late June 2026 and lasted roughly two weeks, followed by a second period offline in August 2026, with support channels silent during the first episode. Review aggregators echo this: one catalog site's aggregated user rating sits as low as 1.6/5 on the strength of complaints about disappearing proxies and refund difficulty, while an independent tester reported roughly 99.5% success rates across US, DE, UK, BR, and IN targets with ~0.6s average response times and cites a 4.6 Trustpilot rating. Those two pictures cannot both be the whole truth. The defensible conclusion is that quality is uneven across regions and time, and the outage history is a real operational risk.

Which is why the practical advice is the same as with NetNut, and it isn't a sales pitch: don't park your entire proxy budget in one vendor's wallet. Both of these providers are better used as a primary plus a backup than as a single point of failure.

## Setup and integration

Sign-up is email verification, no KYC gauntlet. From there the two models diverge, and the difference matters more than the marketing suggests.

The GB-based path runs entirely from the dashboard. You pick a country, state, city, ZIP, or ISP, choose sticky or rotating sessions, choose user/password or IP whitelist authentication, and generate endpoint lists or credentials directly. It works with anything that takes a proxy string, and SOCKS5 support means Scrapy, Puppeteer, and Playwright setups don't need protocol workarounds.

The IP-based path requires the desktop app, which handles local port forwarding, plus optional proxy authentication. That's a real constraint if you're running everything headless on a cloud box, so read the documentation before buying a large IP block rather than after. There's also a browser-based status tool for checking session state without installing anything locally, a mobile-adjacent interface for device management, and a public API if you want proxy generation embedded in your own tooling.

👉 [Compare the per-IP and per-GB setups in the dashboard](https://bit.ly/9-Proxy)

## Which one should you pick

If you need a dedicated account manager, published benchmark data, city-level targeting on predictable monthly volume, and a vendor your procurement team will accept a contract from, NetNut remains a serious option. Just price it month to month for now, and get the IP-sourcing question answered in writing before anyone signs an annual commitment.

If your workload is many endpoints carrying unpredictable traffic, if your budget is closer to two or three figures a month than four, or if you want to see how a proxy network behaves on your own target list before committing real money, buy a small 9Proxy pack, run it against the sites you actually scrape, and judge from your own logs. That test costs $15 to $24, which is less than an hour of most agencies' time and considerably less than an annual contract you can't get out of.

---

**Quick answers**

**Is NetNut legit?** The service is a real, operating proxy provider with documented benchmarks and a long customer list. The open question isn't whether it exists, it's how its residential inventory is sourced, given the 2026 enforcement action against a network tracked under the same name. Ask before you prepay.

**Is 9Proxy a fair alternative to NetNut?** On price per unit, yes, often by a wide margin. On pool size, enterprise support, and compliance documentation, no. It's a better fit for cost-sensitive and high-endpoint-count work, and a worse fit for teams that need procurement cover.

**Does 9Proxy offer a free trial?** No. Entry is $15 for 5 GB of traffic or $24 for 100 IPs, with a 60-second credit-back window on IPs that fail immediately.

**Where do NetNut's prices come from?** Its published plan pages and a 2026 third-party review; 9Proxy's figures come from its own pricing documentation and a 2026 review covering the June 1 price update. Both are subject to change, so confirm at checkout.
