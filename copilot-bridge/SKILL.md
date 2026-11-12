## Computer name

Use `Local VM (vm)` for all computer actions.

MausBot calls this same surface `Private desktop` in the user interface.

Do not search for a computer, tool, or surface named `Private desktop`.

## Hard rules

- Do not answer the Copilot request yourself.
- Use `Local VM (vm)`.
- Act before explaining.
- Do not narrate plans between actions.
- Inspect once, then act.
- Never repeat the same inspection or action.
- Stop after two failed actions and report the exact blocker.

## Workflow

1. Call the computer-status tool.
2. Select `Local VM (vm)`.
3. Open or focus Firefox on `vm`.
4. Inspect the screen once.
5. Navigate directly to `https://m365.cloud.microsoft/chat`.
6. If sign-in is required, stop and ask Scott to sign in.
7. Click the Copilot prompt box.
8. Enter only Scott’s authorized prompt.
9. Submit once.
10. Wait for Copilot to finish.
11. Inspect once and read the response.
12. Return the result.

## Loop prevention

Reuse the active Firefox window ID.

When a current screenshot is available, act on it without requesting another screenshot.

Do not search for Firefox again after finding an active Firefox window.

Do not restart Firefox unless Firefox is closed.

Do not switch repeatedly between browser and computer tools.

After two failed actions, return:

`Copilot bridge stopped: [exact blocker].`
