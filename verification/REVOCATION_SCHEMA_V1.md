Status: FROZEN

Version: v1

Locked-At: 2026-01-17T00:24:35Z



WFSL Revocation Schema v1



This document defines the minimum fields required for a revocation notice.



A revocation notice blocks promotion when present and valid.



File naming

\- verification/REVOCATION\_<SUBJECT>.json



Required fields

\- schema: "wfsl.revocation.v1"

\- subject: string (repo name or subject name, e.g. "wfsl-eco-engine")

\- status: "REVOKED" | "REINSTATED"

\- reason: short string

\- issued\_by: string (authority identifier)

\- issued\_at\_utc: ISO-8601 UTC timestamp

\- effective\_at\_utc: ISO-8601 UTC timestamp



Optional fields

\- expires\_at\_utc: ISO-8601 UTC timestamp (if omitted, revocation is indefinite)

\- evidence: object (free-form references)



Rules

\- If a REVOCATION\_<SUBJECT>.json exists and status is REVOKED and effective\_at\_utc is in the past, promotion must fail.

\- If expires\_at\_utc exists and is in the past, the revocation is ignored.

\- If status is REINSTATED, promotion may proceed (subject to other gates).



