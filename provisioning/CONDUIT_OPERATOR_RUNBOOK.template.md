# Conduit Live-Probation Runbook

1. Inspect the authorization, envelope, and runbook. Download bootstrap only from the exact `bootstrap.url` in the envelope; no `.py` bootstrap is included in the upload package.
2. Verify envelope expiry, scope, server URL, bootstrap URL, and bootstrap SHA-256 before using the invite.
3. Request enrollment with the one-time invite. While pending, bootstrap may continue polling or stop and later resume the same request.
4. The resume capability is stored only at `/home/user/.conduit_enrollment.json` mode `0600`. Never reveal, upload, edit, or copy it into a Conduit workspace. Rerun the same bootstrap command after approval; do not reuse the invite.
5. Bootstrap removes resume state only after the approved credential is verified and atomically stored at `/home/user/.conduit_auth.json` mode `0600`.
6. Read client orientation and use the native SDK.
7. Verify workspace, grant, runtime health, Git status, and history.
8. Stop before mutation. Never create `.conduit_state.json` or lock files.
