---
name: business-ideas-from-urls
description: Turn a list of article URLs (news, scientific journals, research publications, or saved browser tabs) into a brief of low-capital, bootstrappable money-making ideas — each realistically startable for under $2,000 and nights-and-weekends effort. For each URL, research the topic and derive a high-return-on-little-investment angle, then write a punchy slug line, an at-a-glance metadata snapshot, and concrete first steps. Use this whenever the user supplies, pastes, or points to a list of URLs and wants business ideas, side hustles, ways to make money, or monetization angles generated from them. Trigger even when the user doesn't say "skill" — a batch of links plus any ask for money-making ideas is the signal.
---

# Business Ideas from URLs

Turn a supplied list of URLs into a tight, high-end-brief-style set of **low-capital business ideas** — the kind of scannable brief a top business-development firm would produce. Each URL becomes one idea that could be started for **≤ $2,000 and several weeks of nights-and-weekends work**, with a clear path to profitability before any more time or money is committed.

## The core constraint (applies to EVERY idea)

Every idea must be realistically startable with:
- **≤ $2,000** total initial cash, and
- **nights-and-weekends effort** over a few weeks to launch (more time or money is fine *after* it shows profit or has an obvious path to it).

Optimize for **high return on little investment.** Favor scrappy, accessible, fast-to-cash ideas over ambitious capital-heavy ventures. An idea can be a micro-service, a flip or arbitrage play, a content or small-product play, a simple investment, or even a collection/redemption play (buy-and-resell, collect-and-redeem, a productized weekend service, etc.). If the most natural idea from an article is capital-heavy, find the **low-capital wedge** into that space instead — don't propose the capital-heavy version.

## Input

A list of URLs — pasted inline (one per line, comma-separated, or bulleted), supplied as a file path, or referred to as "my tabs" (if no list is actually present, ask the user to paste it).

By default, generate one idea per URL. If the list is long, or the caller asks for a subset (e.g., "the best 5"), rank the URLs by return-on-effort under the ≤ $2,000 constraint, keep the top N, and list which were considered but not selected with a one-line reason each.

### Research budget (per idea) — keep resource use bounded

For each selected URL: fetch the source **once**, and run **at most 2 supporting web searches** for market/context and feasibility. Do not exceed this. If a fact isn't findable within that budget, note the uncertainty rather than digging further.

(Discovery of *which* URLs to use is the caller's job — when this skill is driven by the weekly routine, the routine handles article-gathering under its own search limits. This skill only researches the URLs it's handed.)

## Output

Write a single Markdown file — a scannable brief, not an essay.

- **Filename:** `business-ideas-<YYYY-MM-DD>.md` (current date).
- **Location:** the output directory the caller specifies; default `./output/` (create it if missing). Always state the full path when done.
- **Format:** Markdown by default; also produce a PDF if the caller asks for a polished version.

Structure the file as:
1. Header: date, number of sources processed, one-line summary of the batch.
2. Table of contents (idea titles).
3. One entry per idea, in the format below.

### Entry format (per idea)

Keep prose tight. No long, meandering sections — this is a brief.

```
### N. <Idea Title>
> **<Slug line — one punchy, high-impact sentence that sells the idea>**

**Source:** <url> — <publication>. <one line on what the article says>

<Primer: 2–4 crisp sentences — what's happening and why it opens a low-capital money-making angle right now.>

**Snapshot**
- 💵 **Initial investment:** <≤ $2,000 figure or range>
- ⏱️ **Time to first revenue:** <estimate>
- 🗓️ **Ongoing effort:** <nights/weekends estimate>
- 📈 **Return potential:** <qualitative or rough numbers>
- 🔁 **Model:** <recurring / one-off / arbitrage / flip / content / investment>
- 🧰 **Need to start:** <key tools, skills, or assets>
- ⚖️ **Watch-outs:** <permits, legal, or the main risk>
- <add idea-specific metadata as useful>

**First steps**
1. <concrete, do-this-now step>
2. <next step>
3. <continue until the reader could reach first revenue — usually 3–6 steps>
```

**Metadata rules:** aim for **4–8 items**. Always include **initial investment** and a **time** metric. Each item is an icon (emoji) + a short bold label + a concrete value. Items can be anything relevant, even unique to the idea — e.g. 📦 units to buy, 🎯 target margin, 🌐 online vs local, ⚡ speed to cash, 📊 scalability, 🔧 skill level. **Omit any metric you can't honestly quantify** rather than padding with vague values.

**First steps replace the old business-plan sections.** Do not include separate "target customer / revenue model / go-to-market / competitive landscape" write-ups — anything obvious from the idea needs no explanation. Put the useful substance into concrete, do-this-now steps that get someone to first revenue.

## Process

1. **Fetch the source** once. If it's unreachable, paywalled, or dead, note that in the entry and move on.
2. **Research within budget** — up to 2 supporting searches to check the market and pressure-test feasibility under the ≤ $2,000 constraint.
3. **Find the low-capital, high-return angle** — the scrappiest viable way to make money from the topic.
4. **Write the entry** — slug line, primer, snapshot metadata, first steps.
5. **Assemble the file**, add header + table of contents, write it to the output location, and report the full path.

## Quality bar

- Every idea must pass the ≤ $2,000 + nights-and-weekends test. If it can't, reframe to the low-capital wedge or drop it.
- Slug lines should be sharp and specific, not generic hype.
- First steps must be concrete and doable this week — not abstract advice.
- Ground facts in the source and research; don't invent statistics, and flag speculation as speculation.
- Prefer clarity and brevity over volume — the brief should be skimmable.

## Notes and edge cases

- **Duplicates:** merge multiple URLs about one story into a single idea citing all sources.
- **No viable low-capital angle:** if an article genuinely offers none, say so briefly rather than forcing a weak idea.
- **Large batches:** rank by return-on-effort and select the top N; list the rest with one-line reasons.
- **Framing:** legitimate, legal ideas only.
