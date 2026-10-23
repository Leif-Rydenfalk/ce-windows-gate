# ce-windows-gate

Release gate for the ce Windows installer: each build runs once on a real Windows machine (GitHub `windows-latest`, which ships WebView2) before it goes to anyone. The job checks the sha256, installs silently and expects exit 0, starts `ce.exe`, checks that the join bar renders, and keeps a screenshot as evidence for 3 days.

Run it with `windows-build gate <installer.exe>`. The installer arrives through the `EXE_URL` secret, a short-lived private link, so this repo stores nothing but the workflow.
