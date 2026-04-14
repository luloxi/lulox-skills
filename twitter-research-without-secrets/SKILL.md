---
name: twitter-research-without-secrets
description: "Read, monitor, and research public X/Twitter content with a layered workflow that avoids exposing credentials in repos. Use when the goal is tweet reading, account monitoring, or research prep rather than account administration."
version: 1.0.0
author: Hermes Agent
license: MIT
metadata:
  hermes:
    tags: [x, twitter, social-media, research, monitoring, public-data]
---

# Twitter Research Without Secrets

This skill is for researching X/Twitter safely and reproducibly without putting credentials in the repository.

## What this skill covers

- read public tweets when possible
- monitor a shortlist of accounts
- collect candidate posts for commentary, reposts, or summaries
- keep operational setup separate from repo content

## Layered access model

Use these paths in order:

1. Public URL access
   - direct tweet URLs
   - public profiles
   - browser/web extraction if the content is accessible without auth

2. Browser-assisted reading
   - use browser tools if public pages render but plain extraction fails
   - inspect DOM or retry alternate public URLs before assuming login is required

3. Authenticated local workflow
   - if public reading fails, use a local CLI/browser-cookie workflow
   - credentials must live outside the repo
   - never commit cookies, tokens, or session exports

## Repo / setup expectations

To make this sustainable, keep these practices:

- store monitoring targets in markdown or config files without secrets
- keep tweet ideas, account notes, and posting heuristics in the repo
- keep cookies/tokens in env vars, local config, or a secret manager only
- document the operational dependency, not the secret itself
- assume public-read first and authenticated-read second
- separate research workflows from posting workflows

## Suggested repo artifacts

Good things to keep in the repo:

- a watchlist of accounts to monitor
- notes on tone, repost heuristics, and reply strategy
- templates for tweet suggestions and repost commentary
- small scripts that expect env vars but do not include them

Avoid putting in the repo:

- auth_token / ct0
- browser cookie exports
- bearer tokens
- screenshots containing secrets
- shell history with inline secrets

## Monitoring workflow

1. Check target accounts for new posts.
2. Keep only posts worth amplifying or reacting to.
3. Summarize why each post matters.
4. Draft 2-3 candidate tweets or quote-post comments.
5. Only move to authenticated posting when the user explicitly wants action.

## Good defaults

- prefer concise summaries
- preserve tweet URLs and account handles
- separate factual summary from proposed commentary
- when something fails, state whether the blocker is public access, login requirement, or bot protection
