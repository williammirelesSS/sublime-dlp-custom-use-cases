# Sublime DLP Custom Use Cases

Ten example outbound DLP rules for the [Sublime Security](https://sublime.security) platform, packaged as a custom feed.
Every rule has `type: dlp`, a stable UUID and the `DLP-Custom-Use-Cases` tag.

| Group | Rule |
|---|---|
| Misdirected | Recipient display name matches an internal employee |
| Misdirected | Recipient domain typo |
| Misdirected | Attachment names a different client |
| Leavers and personal email | Attachment sent to personal email |
| Leavers and personal email | Personal email recipient matches sender name |
| Leavers and personal email | Departure language with archive sent to freemail |
| Leavers and personal email | Upcoming leaver sends attachment externally |
| Leavers and personal email | Bulk data export sent to personal email |
| Sensitive content | Microsoft Purview sensitivity label sent externally |
| Sensitive content | Source code sent externally |

## Lists the rules expect

- `$org_upcoming_leavers`: string list of leaver email addresses (rule 10).
- `$org_client_names`: string list of short client names that also appear in each client's email domain, for example `northwind` (rule 12).

Create both lists before adding the feed, or those rules fail validation.

## Add as a feed

In Sublime, add a custom feed with:

- Git URL: `https://github.com/williammirelesSS/sublime-dlp-custom-use-cases.git`
- Branch: `main`
- DLP rule file filter: `rules/*.yml`

These are examples. Test them against your own mail flow before enabling actions.
