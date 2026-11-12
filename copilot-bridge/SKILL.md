---
name: copilot-bridge
description: use microsoft copilot through carl's private desktop only when scott explicitly says ask copilot, have copilot research, get copilot's opinion, have carl review, or send this to r&d. submit the authorized prompt, wait for the answer, and return it. never answer the copilot request yourself.
---

# Copilot Bridge

## Gate

Use this workflow only when Scott explicitly requests Copilot.

A request from another bot is valid only when it states that Scott requested Copilot.

If authorization is missing, do not use Copilot.

## Hard rules

- Do not answer the request yourself.
- Use Carl's Private desktop.
- Act before explaining.
- Do not narrate plans between actions.
- Inspect the screen at most once before acting.
- After each action, inspect only to confirm the result.
- Never repeat the same inspection or action more than once.
- Stop after two failed action attempts and report the exact blocker.

## Workflow

1. Open or focus Firefox on the Private desktop.
2. Inspect the screen once.
3. If Microsoft Copilot is not open, navigate directly to `https://m365.cloud.microsoft/chat`.
4. If sign-in is required, stop and ask Scott to sign in. Do not handle credentials.
5. Click the Copilot prompt box.
6. Enter only Scott's authorized prompt.
7. Submit once.
8. Wait for Copilot to finish.
9. Inspect once and read the complete visible response.
10. Return the result.

## Loop prevention

When an active Firefox window is known, reuse its window ID. Do not search for the browser again.

When a current screenshot is available, act on it. Do not request another screenshot before acting.

Ignore harmless browser notices and popups unless they block the prompt box.

If a popup blocks the task, close it once and continue immediately.

Do not restart Firefox unless Firefox is closed.

Do not switch repeatedly between browser tools and computer tools. Use the tool that already succeeded.

## Output

Start with `Copilot result:`

Use Scott's requested mode:

- `verbatim`: Preserve Copilot's wording when practical.
- `summary`: Give a short, faithful summary.
- `recommendation`: Give Copilot's recommendation and main reason.

If no mode is given, use `summary`.

Preserve useful source names and links shown by Copilot.

Never invent a response.

## Failure

After two failed action attempts, stop.

Return: `Copilot bridge stopped: [exact blocker].`

Do not continue inspecting, retrying, or narrating.

## Boundaries

Permission allows only submitting Scott's prompt, reading Copilot's response, and returning it.

Do not open files, email, calendars, notebooks, links, or other Microsoft 365 apps without separate permission.

Do not submit patient, HR, legal, financial, credential, or other sensitive information without Scott's specific approval.

Do not send messages or change data.
