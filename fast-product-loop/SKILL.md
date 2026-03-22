---
name: lulox-fast-product-loop
description: "Use for lulox-style coding requests: fast implementation over discussion, mixed EN/ES collaboration, Next.js or web UI polish, mobile/desktop cleanup, and live log-driven debugging. Start local-first, but allow push/deploy inference later when the session clearly becomes a live mobile-preview iteration loop."
---

# Lulox Fast Product Loop

Use this skill when the user is driving the work like an operator:

- They want execution first and explanations second.
- They paste live logs, commands, screenshots, or deployment output.
- They care about visible product quality, especially web/mobile UI polish.
- They often want the task carried through implementation and verification.

## Operating assumptions

- Treat the first prompt as the product brief, even if it is informal.
- Treat short follow-ups as context updates to the same task unless the user is clearly pivoting to a new task.
- Prefer repo inspection and concrete progress over early clarification questions.
- At the start of a session, do not infer `commit`, `push`, or `deploy` from momentum or prior sessions.

## Intake checklist

Extract these items immediately:

- Target surface: web, mobile web, extension, desktop overlay, backend, deploy flow.
- Exact bad behavior or requested change.
- Desired end state in user-facing terms.
- Relevant repo/path if provided or discoverable.
- Shipping boundary: edit only, commit, push, deploy, or audit/report only.

If one of these is missing but discoverable from the workspace, inspect first and ask later.

## Release boundary

- Default to local edits plus verification only.
- Do not start by staging, committing, pushing, deploying, publishing, or amending unless the user explicitly asks.
- Once the session clearly shifts into live testing on phone/mobile against a hosted build, you may infer that `push` or `deploy` is part of the loop if it is necessary for the user to try the change live.
- Good signals for that mode: the user is testing on mobile, referencing a hosted URL or preview, giving fast visual feedback from the deployed app, or asking to "try it live".
- In that mode, prefer `push` or `deploy` only when it directly serves the live test loop. Do not infer `commit --amend`, release publishing, or unrelated git hygiene.
- If the request is ambiguous, prefer finishing the code change and reporting status over performing a release action.
- Separate `code fixed` from `released` in the final response.

## Preferred execution style

- Work in tight loops: inspect, change, verify, report.
- Keep commentary short and action-oriented.
- Anchor debugging to the first concrete failing signal, not downstream noise.
- When logs are pasted, identify the failing command and summarize the root cause before changing code.
- Preserve unrelated work and avoid cleanup that was not requested.

## Frontend priorities

When the task is UI-heavy, optimize for the patterns this user repeatedly asks for:

- Stronger contrast and cleaner hierarchy.
- Symmetry, alignment, and reduced visual clutter.
- Mobile/desktop parity where practical.
- Full-height or low-scroll layouts when the user calls out wasted space.
- Buttons, tabs, and controls sized intentionally instead of default spacing.

Do not settle for generic styling when the user asks to "make it nicer" or "look good".

## Debugging priorities

- Reproduce locally if possible.
- Use pasted logs and command output aggressively; the user often provides the real clue.
- If the fix involves infra or permissions, explain the tradeoff briefly and choose the safest workable path.
- If a deploy is blocked by environment setup, separate code status from environment status so the user knows what is actually fixed.

## Communication pattern

- Match the user's language. Mixed EN/ES is normal.
- Default to concise updates.
- Final response should lead with outcome, then blockers/verification, then only the most useful next step if one exists.

## Skill debug

- When you use this skill, append one short line at the end of the final response:
  `Skill debug: applied=yes; effect=<helped|neutral|hurt>; note=<very short reason>`
- Keep the note brief and concrete.
- This footer is for debugging the skill, not for repeating the whole summary.

## What this skill is trying to preserve

This user is strong at product direction, rapid iteration, and supplying runtime evidence. The main gain comes from turning that energy into fewer context resets and faster end-to-end execution.
