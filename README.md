# firecrawl api: Plans, Credit Costs, and When ScraperAPI Is the Smarter Pick

The Firecrawl API turns any web page into clean Markdown or structured JSON with one call, which is exactly what AI agents and RAG pipelines need. It's free to start (1,000 credits a month, no card), and paid plans run from $19 to $749 a month. But before you pick it, there's a credit-cost layer most people miss: format add-ons, error-page billing, and a pricing page that shows annual prices by default. And if what you actually want is raw HTML from Amazon, Google, or LinkedIn at volume, a different tool with a very different billing model will cost you far less. This article walks through both, with real numbers.

> **Quick take:** If your job is LLM-ready Markdown, Firecrawl's free tier gets you 1,000 pages a month. If your job is scraping specific hard targets — Amazon, Google, LinkedIn, sites behind Cloudflare — ScraperAPI is built for that, and you can test it for free: a 7-day trial with 5,000 credits, no card required. [👉 Start the ScraperAPI trial with 5,000 free credits](https://www.scraperapi.com/signup?fp_ref=coupons)

## What the Firecrawl API actually does

Firecrawl is a web data API aimed at AI agents: it searches, scrapes, crawls, and interacts with live websites, then hands back LLM-ready Markdown or structured JSON. Under the hood it handles proxies, anti-bot walls, JavaScript rendering, and dynamic content, so you don't maintain a browser farm. The endpoint list covers the main things builders ask for:

- **Scrape** — one URL in, markdown, HTML, or structured JSON out
- **Crawl** — recursively pull an entire site, with a job ID returned for async runs
- **Search** — one call returns search results plus full page content, sorted into web, images, and news
- **Interact** — click buttons, fill forms, and navigate pages after scraping, driven by plain-English prompts or Playwright code
- **Map, Parse, Agent, Webhooks, Browser Sandbox** — URL discovery, local file conversion (PDF, DOCX, XLSX), autonomous data collection, async events, and hosted browser sessions

One genuinely unusual detail: you can call the scrape endpoint without an account or API key at all. Firecrawl caps keyless usage per IP address, so it works for a quick test, then you add a key for real rate limits. There are Python and Node SDKs, an MCP server for wiring it into any AI tool, and a CLI that installs with one command and attaches skills to detected coding agents. It's open source under AGPL-3.0, so self-hosting is possible — though the default stack skips screenshots and page actions, and Agent, browser interaction, and some formats stay cloud-only.

## Firecrawl API pricing: every plan on the official page

Firecrawl's current rate card took effect September 4, 2026, and all prices are in USD. Six tiers are on the pricing page:

| Plan | Monthly | Billed yearly | Credits/month | Concurrent browsers |
| --- | --- | --- | --- | --- |
| Free | $0 | $0 | 1,000 | 2 |
| Hobby | $19 | $16/mo | 5,000 | 5 |
| Standard | $99 | $83/mo | 100,000 | 25 |
| Growth | $399 | $333/mo | 500,000 | 50 |
| Scale | $749 | $599/mo | 1,000,000 | 100 |
| Enterprise | Custom | Custom | Custom | Custom |

A basic scrape, crawl, or map costs 1 credit per page, so the free tier works out to roughly 1,000 pages or 500 searches monthly. Every endpoint is available on every plan, including Free — what changes is volume, speed, and support level (Community support on Free, Priority on Growth and Scale, a shared Slack channel only from Growth up).

Here's the trap worth knowing before you look at the page: it defaults to the annual toggle, so you'll see $16, $83, and $333 first. Those are per-month prices billed yearly. Month to month, the same plans cost $19, $99, and $399. Annual saves 16.7% on most tiers and 20% on Scale. Neither number is hidden, but plenty of pricing roundups quote the annual figure as if it were the sticker price.

## The credit costs that don't show up in the headline price

This is where most Firecrawl pricing articles stop at "1 credit per page," and it's where your real bill gets decided. A few rules from Firecrawl's billing documentation matter a lot:

**LLM formats multiply your cost.** JSON extraction, question/query answers, highlights, audio and video transcription, and PII redaction each add 4 credits per page on top of the base 1. A crawl with JSON output enabled costs five times a plain one. Add-ons stack, too: JSON plus PII redaction is 9 credits per page.

**Error pages still cost you.** The billing rule is explicit: what gets charged is whether Firecrawl returned a document, not whether the target site returned a success code. A 403 or 404 page comes back to you and costs 1 credit. A scrape that returns no result at all is not charged, and completely failed requests (site unresponsive, all rendering attempts dead) are free.

**Credits don't roll over.** Unused Hobby, Standard, and Growth credits vanish at the end of each billing period. Only Scale carries them over, and only for one month.

**Pay-as-you-go has no ceiling by default.** When credits run out, top-ups arrive in $5 increments automatically. If you leave the monthly spend limit blank, there is no cap. Set one the day you enable it.

**The Agent endpoint is hard to budget.** Your first 5 runs a day are free; after that, billing follows the tokens the agent actually uses, so similar tasks can cost different amounts.

One more thing the terms of service cover: Firecrawl doesn't issue refunds. You can cancel anytime and charges stop at the end of the billing period, but what you've already paid stays paid.

## ScraperAPI: the full plan lineup and what each tier actually buys

ScraperAPI takes the opposite approach to the same problem. Instead of converting pages for LLMs, it's a scraping API focused on getting you raw HTML from sites that fight back — rotating residential and mobile IPs, CAPTCHA and anti-bot handling, JS rendering, and automatic retries. All plans share the same feature set, including unlimited bandwidth, a 99.9% uptime guarantee, and priority support with a dedicated team.

Signing up gets you a 7-day trial with 5,000 API credits, no credit card needed. There's also a permanent free plan with 1,000 credits at up to 5 concurrent connections if you need more testing time. The paid lineup:

| Plan | Monthly | Billed annually | API credits | Concurrent threads | Get started |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | $0 | 1,000 | 5 | [Start free](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Hobby | $49 | $44.10/mo | 100,000 | 20 | [Start Hobby](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Startup | $149 | $134.10/mo | 1,000,000 | 50 | [Start Startup](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Business | $299 | $269.10/mo | 3,000,000 | 100 | [Start Business](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Scaling | $475 | $427.50/mo | 5,000,000 | 200 | [Start Scaling](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Professional | $975 | $877.50/mo | 10,500,000 | 300 | [Start Professional](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50/mo | 21,500,000 | 500 | [Start Advanced](https://www.scraperapi.com/signup?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [Contact ScraperAPI](https://www.scraperapi.com/?fp_ref=coupons) |

Annual billing takes a flat 10% off every tier. The two tiers that look cheapest on paper carry real restrictions: Hobby and Startup limit geotargeting to US and EU regions only, and their analytics dashboard only keeps the last 30 days of data. From Business up you get country-level targeting and unlimited dashboard history. If either of those matters to your project, the $100 jump to Business buys more than credits.

When credits run out, behavior depends on the tier. By default scraping pauses until renewal. Hobby through Professional can opt into auto-upgrade, which moves you to the next plan automatically. Scaling and above can use pay-as-you-go at a fixed per-credit rate, capped at a monthly limit you set. Exceeding your concurrent thread limit returns a 429 and the request is turned away — no queue, no extra charge.

## Firecrawl or ScraperAPI? The billing models decide it

Both services bill in credits, but the credits mean completely different things. Put them side by side:

|  | Firecrawl | ScraperAPI |
| --- | --- | --- |
| Core output | Markdown, structured JSON, screenshots | Raw HTML, JSON auto-parsing |
| Built for | AI agents, RAG pipelines, LLM extraction | High-volume scraping of protected sites |
| Entry paid plan | $19/mo (5,000 credits) | $49/mo (100,000 credits) |
| Free option | 1,000 credits/mo, no card | 7-day trial (5,000 credits) + 1,000-credit free plan |
| Search cost | 2 credits per 10 results | 25 credits per Google/Bing request |
| Amazon page | 1 credit (per standard page) | 5 credits |
| LinkedIn | Third-party data pricing (varies) | 30 credits |
| Anti-bot bypass | Included | +10 credits/request on Cloudflare, Datadome, PerimeterX |
| Open source / self-host | Yes (AGPL-3.0) | No |

The pattern is clear once you map real workloads onto it. Say you need 10,000 standard web pages. Firecrawl Standard at $99 burns 10,000 credits — a tenth of your monthly allotment. ScraperAPI Hobby at $49 uses the same 10,000 credits and still has 90,000 left. On plain pages, ScraperAPI is dramatically cheaper per unit.

Flip the workload. You need search results for an agent: 10,000 Firecrawl search results cost about 2,000 credits and come back with full page content attached. The same 10,000 queries through ScraperAPI cost 250,000 credits — two and a half Hobby plans' worth. And if the "raw HTML" you want is actually structured data for an LLM, Firecrawl's Markdown output saves you the parsing work entirely.

ScraperAPI's multipliers are its version of Firecrawl's format add-ons: easy to glance past, expensive to ignore. Google at 25 credits a request means the 100,000-credit Hobby allowance is really 4,000 Google searches if that's all you do. The good news is you don't have to guess — the dashboard includes a Domain Cost Estimator that prices any URL before you scrape it, and you can set a max_cost parameter to keep any single request within a budget you define. `render=true` adds 10 credits per request, `ultra_premium=true` adds 30, and stacking premium flags with JS rendering can push a single request to 75 credits. Check the estimator before you commit a plan to a target list.

## Which plan fits which situation

For **AI agents and RAG pipelines**, Firecrawl is the obvious tool: purpose-built Markdown output, search with content included, Interact for dynamic pages, and a free tier that runs real workloads. Standard at $99/month (or $83 annual) is the tier most builder teams land on — 100,000 credits covers 100,000 plain pages or roughly 50,000 search results a month.

For **structured extraction from a handful of hard targets**, ScraperAPI wins on cost. Its premium-domain pricing (Amazon 5x, Google 25x, LinkedIn 30x) exists precisely because those sites are what it's tuned to handle. If your target list is mostly standard pages with some Amazon mixed in, Hobby at $49 is the practical entry point. [👉 See all ScraperAPI plans and current prices](https://www.scraperapi.com/pricing?fp_ref=coupons)

For **e-commerce price monitoring**, run the numbers both ways before choosing. Firecrawl charges 1 credit per Amazon page; ScraperAPI charges 5. A 50,000-page monthly Amazon crawl is 50,000 Firecrawl credits (Standard tier, $99) versus 250,000 ScraperAPI credits (Startup tier, $149). Volume and target mix decide the winner — this is exactly the kind of case where the "obvious" AI-era pick isn't the cheap one.

## FAQ

**Does the Firecrawl API have a free tier?**
Yes — 1,000 credits per month, refreshed monthly, no credit card required. You can even call the scrape endpoint without registering, within per-IP daily limits. ScraperAPI's equivalent is a 7-day trial with 5,000 credits plus a standing free plan of 1,000 credits at 5 concurrent connections.

**What happens when I run out of Firecrawl credits?**
Pay-as-you-go tops you up in $5 increments, available on paid plans only, with a monthly cap you can (and should) set. ScraperAPI offers the same idea from the Scaling tier up, plus opt-in auto-upgrade on Hobby through Professional.

**Do unused credits carry over?**
On Firecrawl, no — except Scale, which carries credits for one month. ScraperAPI's credits reset each period as well, but annual subscribers can renew early for a fresh batch.

**Can I scrape Google with the Firecrawl API?**
You can search the web through the Search endpoint at 2 credits per 10 results. ScraperAPI prices Google and Bing at 25 credits per request because it's routing them through its own extraction logic. For pure search volume, Firecrawl's pricing is hard to beat; for Google's actual result pages as HTML, ScraperAPI is the specialist.

## The decision, in one pass

Need LLM-ready Markdown, agent-friendly search, or site interaction with a plain-English prompt? Go Firecrawl, start on the free tier, and remember the annual toggle before comparing prices. Need raw HTML from Amazon, Google, LinkedIn, or aggressively protected sites, at the lowest cost per request? ScraperAPI's multiplier model is cheaper precisely for those targets — and the 7-day trial with 5,000 credits lets you confirm it against your real target list before spending anything. [👉 Try ScraperAPI free before you commit](https://www.scraperapi.com/signup?fp_ref=coupons)

One last check before you pay for either: estimate your actual monthly page count and list the domains involved. A standard-page workload and a Google-heavy workload can differ by a factor of 25 in real cost on the same nominal credit allowance, and that single calculation will pick your plan faster than any feature list.
