# Shared recognition knowledge

This public folder contains 41 reviewed vendor instruction profiles and supports approved exact supplier/part CORE rules and reusable part descriptions. No custom CORE associations or reviewed part rows had been approved when the folder was initialized.

## How PCs share

Use Invoice Labels 2026.11.22.35 or newer. Every updated PC uses this same repository. New approved vendor/CORE rules, approved edits and reviewed part changes trigger publication while the app is running. There is no 30-minute publishing schedule. A brief debounce coalesces related saves; identical knowledge creates no extra GitHub commit. Offline changes remain in the local approved database and are retried after connection failures or at the next startup.

Other PCs receive public knowledge automatically while open, using lightweight ETag checks about every 30 seconds while idle. The automatic defaults apply to fresh installations and updates; no rules switch or GitHub login is required. Startup and manual Check GitHub remain available. Recognition, previews and printing defer safe application until idle. Unchanged responses contain no rule body; errors back off. The server cache updates immediately after relay saves, with a five-minute lazy backstop for outside GitHub edits. Downloading needs no GitHub account or token. The app continues working with local knowledge offline. Each PC registers automatically with the HTTPS rule relay at parts.ittr.pro. No GitHub account or token setup is needed on PCs. The relay holds a repository-scoped deploy key on the server; PCs receive their own revocable credential protected by Windows. Automatic registration is open to app users, with per-address/device limits and schema validation; it is not proof of an operator identity. No GitHub writer key is included with the application or this repository. Legacy private auto-sync is paused while this public source is active; its saved connection remains available for manual use.

## Duplicates and choices

Identical entries are skipped. A different version of the same supplier/part/manufacturer or vendor/CORE rule never silently overwrites the other version. The app shows both versions and lets you choose Shared or This PC. Save choices on GitHub records the choice in recognition.json under decisions, together with both content fingerprints. Updated PCs reuse that choice for that exact conflict; a later edit with different fingerprints requires another choice. New nonconflicting approved knowledge can still be shared. The relay serializes edits and uses non-force Git pushes. A concurrent external change is rejected and fetched again before merging; existing versions and decisions are never force-overwritten.

Incoming new entries and versions covered by an exact saved choice can be applied safely. Local edits, exclusions and locally forgotten rules remain protected. Publication is additive: removing a local entry does not silently delete knowledge from everyone else's PC.

## What is excluded

Invoice originals, invoice numbers, invoice quantities and prices, history, print attempts, sign-ins, printer settings, licenses and private keys are not in this dataset. Approved rule instructions can contain illustrative extraction examples. Never upload the private recognition transfer ZIP, SQLite databases or credentials here. Applying a rule does not print anything.

For reusable parts, review the invoice, save its supplier, select the reviewed rows and use Save reviewed parts to catalog. Approve vendor/CORE rules through their normal app workflows. The app shares approved knowledge only; unreviewed OCR rows are not published.

CORE-RULES.md describes the app's CORE policy. sync-policy.json documents the shared behavior. public_knowledge.py in the application source validates this schema. Readers need no publisher access; updated PCs save shared decisions through the same automatically registered relay.
