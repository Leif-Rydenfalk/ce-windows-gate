# ce-windows-gate

Release gate for the ce Windows installer: each build runs once on a real Windows machine (GitHub `windows-latest`, which ships WebView2) before it goes to anyone. The job checks the sha256, installs silently and expects exit 0, starts `ce.exe`, checks that the join bar renders, and keeps screenshots only when the run fails, for 1 day. The link is never printed, and no screenshot ever shows a customer name or invite code (the gate runs a fresh, unjoined install).

Run it with `windows-build gate <installer.exe>`. The installer arrives through the `EXE_URL` secret, a short-lived private link, so this repo stores nothing but the workflow.
