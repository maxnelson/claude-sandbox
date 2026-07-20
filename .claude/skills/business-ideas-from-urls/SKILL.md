---
name: business-ideas-from-urls
description: Turn a list of article URLs (news, scientific journals, research publications, or saved browser tabs) into investor-ready business-idea proposals. For each URL, research the topic and the market around it, derive a lucrative business opportunity or monetization angle, and write a thorough primer plus a mini business plan and an investor pitch, all collected into a single dated Markdown file at a specified output location. Use this whenever the user supplies, pastes, or points to a list of URLs and wants business ideas, ways to make money, market opportunities, startup concepts, or investor-style write-ups generated from them. Trigger this even when the user doesn't say the word "skill" — a pasted batch of links plus any ask for business or monetization ideas is the signal.
---

# Business Ideas from URLs

Generate a set of investor-ready business proposals from a supplied list of URLs. Each URL becomes one proposal that doubles as a primer on the underlying topic and a pitch for a concrete way to make money from it.

## When to use this

Use this whenever a list of URLs is supplied — pasted inline, provided as a file, or accumulated as browser tabs — together with a request to generate business ideas, monetization angles, market opportunities, or investor write-ups. The list may be a handful of curated links or a large batch of the week's saved tabs.

## Input

The input is a list of URLs. Accept them in any of these forms:
- Pasted directly into the prompt (one per line, comma-separated, or as a bulleted list)
- Supplied as a path to a text or Markdown file containing URLs
- Referred to as "my open tabs" or "this week's tabs" — in that case, ask the user to paste the URLs unless a tab list has already been provided

By default, generate one proposal per URL. If the caller asks for a subset (for example, "the 5 with the most lucrative potential"), first skim every URL, rank them by business potential, keep the top N, and generate proposals only for those. Note in the output which URLs were considered but not selected.

## Output

Write a single Markdown file containing every proposal.

- **Filename:** `business-ideas-<YYYY-MM-DD>.md`, using the current date.
- **Location:** write it to the output directory specified by the caller. If none is specified, default to `./output/` and create the directory if it does not exist. Always state the full path of the file you wrote at the end of the run.
- **Format:** Markdown by default. If the caller explicitly asks for a polished or investor-facing document, additionally convert the Markdown to PDF.

Structure the file as:
1. A short header: date, number of sources processed, one-line summary of the batch.
2. A table of contents listing each proposal title.
3. One section per proposal, using the structure below.

### Structure of each proposal

For each selected URL, produce a section with these parts:

- **Business idea (title):** a short, memorable name for the opportunity.
- **Source:** the URL, the publication, and one line on what the article or paper actually says.
- **Primer — what's going on and why it matters:** a thorough, self-contained explanation of the topic in the source and its surrounding context. Assume the reader has not read the source. Cover the key facts, the "why now," and the background someone would need to evaluate the opportunity. This is the part that makes the document useful even to a reader unfamiliar with the news.
- **The opportunity:** the specific business or way to make money the topic suggests. Be concrete about what the product or service is and who pays for it.
- **Mini business plan** — cover each briefly but substantively:
  - Problem being solved
  - Product / solution
  - Target customer and rough market size
  - Revenue model (how it makes money)
  - Go-to-market (how you would get the first customers)
  - Competitive landscape and what is defensible
  - Key risks and unknowns
  - What it would take to start (rough scope, not a detailed budget)
- **Investor snapshot:** a tight, compelling pitch — the "why this, why now, why it could be big" in a few sentences that could stand alone in front of an investor.

## Process

Work through the list one URL at a time:

1. **Fetch and read the source.** Retrieve the page content. If a URL is unreachable, paywalled, or dead, note it in the output and move on rather than guessing at its contents.
2. **Research around it.** Do not rely only on the single article. Research the broader topic, the market, existing players, and adjacent developments needed to assess a real opportunity and to write an accurate primer.
3. **Find the most lucrative angle.** Identify the business idea or monetization path with the most genuine upside for this topic — not the most obvious one if a stronger one exists.
4. **Write the proposal** using the structure above.
5. After all URLs are processed, **assemble the file**, add the header and table of contents, write it to the output location, and report the full path.

## Quality bar

- The primer must be genuinely informative to someone who never read the source: thorough, accurate, grounded in the research, not padding.
- Business ideas must be concrete and plausible, with a clear answer to "who pays, and why." Avoid vague "build a platform for X" ideas with no revenue logic.
- Ground claims about markets, competitors, and facts in the research. Flag speculation as speculation, and do not invent statistics.
- Keep each proposal readable on its own; the file is meant to be skimmed by an investor or used as a topic primer.

## Notes and edge cases

- **Duplicates:** if the list contains multiple URLs about the same story, merge them into one proposal citing all sources.
- **Off-topic or low-potential links:** if a URL has no plausible business angle, say so briefly in its section rather than forcing a weak idea.
- **Large batches:** for a long list of weekly tabs, ranking and selecting the top N is usually more useful than a thin proposal for every link — offer this if the list is long and the caller has not specified.
- **Framing:** keep proposals to legitimate, legal business opportunities.
