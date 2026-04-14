---
name: internet-research-toolbox
description: "Free-first toolbox for exploring the internet: search, extract, browse, inspect pages, and scrape public content with native Hermes tools only. Use when the user wants current information, tweet/news monitoring, web page reading, or lightweight scraping without paid APIs."
version: 1.1.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [web, research, scraping, browser, free, public-data]
---

# Internet Research Toolbox

Use the free/native tools first, in this order:

1. web_search — find candidate sources and current facts
2. web_extract — pull readable markdown from URLs, PDFs, and articles
3. browser_navigate / browser_snapshot — interact with dynamic pages and logins
4. browser_console — inspect DOM, page state, JS errors, and extract structured data
5. browser_get_images / browser_vision / vision_analyze — handle image-based content
6. search_files / read_file / write_file / patch / terminal — local processing, caching, and scripting

## What this skill is for

- current news, docs, product pages, repos, public profiles
- reading public web content quickly
- dynamic sites that need browser interaction
- extracting text from pages or PDFs
- lightweight scraping of public data with tooling instead of paid APIs

## Repo / setup expectations

To get the most out of this workflow, keep these attitudes and repo conventions:

- prefer public/free sources before paid APIs
- keep reusable prompts and extraction notes in markdown
- cite sources and preserve URLs
- treat browser access and scraping as separate fallbacks, not the default
- avoid hardcoding secrets into repo files
- when a source needs credentials, store them outside the repo in env vars or a secret store
- keep small helper scripts under scripts/ if a source needs repeated extraction

## Recommended workflow

1. Search broadly with web_search.
2. Extract the best URLs with web_extract.
3. If the page is dynamic or blocked, use browser_navigate + browser_snapshot.
4. If the page renders poorly, inspect via browser_console or browser_vision.
5. If data must be transformed or deduplicated, use terminal or execute_code.
6. Summarize clearly with source URLs and caveats.

## Dynamic-site debugging checklist

- Check browser_snapshot before assuming access failed.
- Use browser_console to inspect errors and DOM state.
- If a page shows login or anti-bot blocks, try a public URL variant or a different extraction route.
- If content is visible in the browser but not in extract, use browser_console to read it directly.

## Good defaults

- Keep responses concise.
- Cite the specific URLs or pages used.
- Distinguish confirmed facts from estimates or heuristics.
- When asked for rankings or top-N lists, explain the data source and time window.
