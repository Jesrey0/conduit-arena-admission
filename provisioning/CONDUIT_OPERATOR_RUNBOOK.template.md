# Conduit Enrollment Runbook

1. Inspect the envelope and authorization. Timestamps are ISO-8601 absolute instants; `Z` means UTC. Compare timezone-aware instants, never calendar dates.
2. Download bootstrap only from exact `bootstrap.url`; verify its SHA-256 before using the invite.
3. `authorization.accessClass` authorizes one request with exactly the declared grant; it does not mean access is already issued.
4. Request enrollment. While pending, bootstrap stores its request-resume capability only at `/home/user/.conduit_enrollment.json` mode `0600`. It may keep polling or safely rerun the same command after approval. Never reveal, upload, or edit that file.
5. Bootstrap stores verified auth only at `/home/user/.conduit_auth.json` mode `0600`.
6. Use the native SDK, verify workspace/grant/runtime/Git state, and remain inside declared privileges.
7. Never create `.conduit_state.json` or lock files.
