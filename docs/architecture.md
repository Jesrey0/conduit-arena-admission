# Architecture

```text
public candidate kit -> agent-managed local fixture -> verifier report -> human review
human approval -> server-issued provisioning package -> enrollment pending -> local approval -> probation
```

The public kit owns candidate protocol, report schema, provisioning schema, templates, and prompt cards. Conduit Local owns actual invite generation, bootstrap, approval, credentials, grants, expiry, and revocation.

Candidate reports are evidence only. Server-issued credentials are the authority.
