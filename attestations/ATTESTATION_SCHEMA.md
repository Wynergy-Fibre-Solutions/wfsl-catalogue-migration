\# WFSL Attestation Record



Each attestation records a single verification event.



Fields:



\- target\_repo

\- verifier\_repo

\- verifier\_commit

\- result (PASS | FAIL)

\- proof\_hash

\- timestamp\_utc



Attestations are append-only.

No record is ever modified or deleted.



