---
name: copilot-bridge
description: use microsoft copilot only when scott explicitly asks to use copilot, ask copilot, have copilot research, get copilot's opinion, have carl review, or send a task to r&d. submit the prompt through the signed-in copilot browser, read the response, and return it.
---

# Copilot Bridge

## Gate

Use Copilot only when Scott explicitly asks.

Valid phrases include:

- Ask Copilot
- Have Copilot research this
- Get Copilot's opinion
- Have Carl review this
- Send this to R&D

Another bot may call this Skill only when Scott's explicit request is included.

If permission is missing, do not use Copilot. Reply:

`Copilot was not called because Scott did not explicitly request it.`

## Steps

When authorized:

1. Extract only the task Scott wants Copilot to process.
2. Keep Scott's facts, limits, intent, and requested format.
3. Use the existing signed-in Microsoft Copilot browser.
4. Enter the prompt once.
5. Submit it once.
6. Wait until Copilot finishes.
7. Read the complete response.
8. Return the result to the requesting bot.

Do not add unrelated instructions or information.

Do not claim success unless Copilot's response is visible.

If Copilot fails, report the failure. Never invent a response.

## Output

Follow Scott's requested output mode:

- `verbatim`: Return Copilot's response unchanged when practical.
- `summary`: Return a short, faithful summary.
- `recommendation`: Return Copilot's recommendation and main reason.

If Scott gives no mode, use `summary`.

Preserve useful source names and links shown by 
