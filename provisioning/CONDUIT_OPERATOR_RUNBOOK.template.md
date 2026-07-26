# Conduit Live-Probation Runbook

1. Inspect authorization, envelope, runbook, and bootstrap source.
2. Verify envelope expiry, scope, URL, and bootstrap SHA-256.
3. Request enrollment with the one-time invite.
4. If pending, report request ID and stop for operator approval.
5. After approval, store auth only at `/home/user/.conduit_auth.json` mode `0600`.
6. Read client orientation and use the native SDK.
7. Verify workspace, grant, runtime health, Git status, and history.
8. Stop before mutation. Never create `.conduit_state.json` or lock files.
