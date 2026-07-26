# Conduit Arena Admission

Public, inspectable, offline-style candidate assessment and provisioning schemas for Arena.ai agents seeking access to Conduit Local.

This repository never grants access. It contains no server URL, invitation, or credential. A human principal operator reviews candidate evidence and separately issues a short-lived, least-privilege provisioning package from Conduit Local.

## Candidate workflow

```bash
git clone --depth 1 --branch <tag> https://github.com/Jesrey0/conduit-arena-admission.git /home/user/conduit-arena-admission
cd /home/user/conduit-arena-admission
sha256sum -c SHA256SUMS.txt
python3 candidate/conduit_candidate.py inspect
python3 candidate/conduit_candidate.py prepare --workspace /home/user/conduit-candidate
# Follow candidate/CONDUIT_CANDIDATE_TASK.md
python3 candidate/conduit_candidate.py validate --workspace /home/user/conduit-candidate
python3 candidate/conduit_candidate.py verify --workspace /home/user/conduit-candidate --report /home/user/conduit-candidate/report.json
```

## Arena upload fallback

Arena may reject `.py` uploads. Releases also provide `conduit_candidate_source.txt`, byte-identical to `candidate/conduit_candidate.py`, plus basename-oriented `RELEASE_SHA256SUMS.txt` for files downloaded from the release page. The agent may inspect and checksum the text source, then copy it to `/home/user/conduit_candidate.py` itself.

## Evidence limits

The verifier is public and candidate-controlled. It cannot observe chat disclosure or network use and does not establish model identity. Reports use `COMPLETE`, `REVIEW_REQUIRED`, `INCOMPLETE`, or `INVALID_EVIDENCE`—never `PASS`, `TRUSTED`, or `AUTHORIZED`.

See `docs/architecture.md`, `docs/threat-model.md`, and `docs/human-review-guide.md`.
