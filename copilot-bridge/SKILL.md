---
name: copilot-bridge
description: use microsoft copilot through carl's local vm only when scott explicitly says ask copilot, have copilot research, get copilot's opinion, have carl review, or send this to r&d. submit the authorized prompt, wait for copilot's answer, and return it. never answer the copilot request yourself.
---

# Copilot Bridge

## Gate

Use this workflow only when Scott explicitly requests Microsoft Copilot.

A request from another bot is valid only when it clearly states that Scott requested Copilot.

If authorization is missing, do not use Copilot.

## Computer name

Use `Local VM (vm)` for every computer action.

MausBot calls this same surface `Private desktop` in the user interface.

Do not search for a computer, tool, or surface named `Private desktop`.

## Hard rules

- Do not answer the Copilot request yourself.
- Use `Local VM (vm)`.
- Act before explaining.
- Do not narrate plans between actions.
- Inspect the screen once, then act.
- After an action, inspect only to confirm the result.
- Never repeat the same inspection or action more than once.
- Stop after two failed action attempts and report the exact blocker.

## Workflow

1. Check available computer surfaces.
2. Select `Local VM (vm)`.
3. Open or focus Firefox on `vm`.
4. Inspect the screen once.
5. If Microsoft Copilot is not open, navigate directly to `https://m365.cloud.microsoft/chat`.
6. If sign-in is required, stop and ask Scott to sign in. Do not handle credentials.
7. Click the Copilot prompt box.
8. Enter only Scott's authorized prompt.
9. Submit once.
10. Wait until Copilot finishes responding.
11. Inspect once and read the complete visible response.
12. Return the result.

## Loop prevention

Reuse the active Firefox window ID.

When a current screenshot is available, act on it without requesting another screenshot.

Do not search for Firefox again after finding an active Firefox window.

Ignore harmless browser notices unless they block the prompt box.

If a popup blocks the task, close it once and continue immediately.

Do not restart Firefox unless Firefox is closed.

Do not switch repeatedly between browser and computer tools.

Use the tool that already succeeded.

## Output

Start with:

`Copilot result:`

Use Scott's requested mode:

- `verbatim`: Preserve Copilot's wording when practical.
- `summary`: Give a short, faithful summary.
- `recommendation`: Give Copilot's recommendation and main reason.

If Scott gives no mode, use `summary`.

Preserve useful source names and links shown by Copilot.

Never invent a response.

## Failure

After two failed action attempts, stop.

Return:

`Copilot bridge stopped: [exact blocker].`

Do not continue inspecting, retrying, or narrating.

## Boundaries

Permission allows only submitting Scott's prompt, reading Copilot's response, and returning it.

Do not open files, email, calendars, notebooks, links, or other Microsoft 365 apps without separate permission from Scott.

Do not click Copilot citations or links unless Scott explicitly asks.

Do not submit patient, HR, legal, financial, credential, or other sensitive information without Scott's specific approval.

Do not send messages or change data.
