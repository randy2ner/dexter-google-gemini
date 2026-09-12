# Synthetic Activity Scan Evidence

Approved scope: fictional Email and Teams items from `2026-09-08T00:00:00Z` through `2026-09-12T17:00:00Z`.

| Item | Source | Timestamp | Content summary | Expected interpretation |
| --- | --- | --- | --- | --- |
| E-1 | Email `fixture-email-passwordless` | 2026-09-10T19:15:00Z | Alex confirms pilot prerequisites and next cohort. | Qualifying continuation of Passwordless readiness. |
| E-2 | Email `fixture-email-passwordless` | 2026-09-11T14:00:00Z | Automated room-booking notice. | Excluded; must not advance `lastActivityAt`. |
| E-3 | Teams `fixture-chat-passwordless` | 2026-09-12T15:30:00Z | Sam records that customer testing found one enrollment dependency. | Same Passwordless readiness Activity; update factual account and `lastActivityAt`. |
| E-4 | Email `fixture-email-breakglass` | 2026-09-12T16:00:00Z | Alex requests a separate customer decision about emergency access ownership. | New Activity under Passwordless pilot; one source can yield distinct work. |
| E-5 | Teams `fixture-chat-internal` | 2026-09-12T16:10:00Z | General certification study reminder with no customer connection. | Excluded. |
| E-6 | Teams `fixture-chat-conditional-access` | unknown | Host returns only the first page and no continuation token. | Coverage gap; Conditional Access recency remains uncertain. |

No entry is a raw transcript. All people, organizations, references, and events are fictional.