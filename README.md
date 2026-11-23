# Shared recognition knowledge

This public folder contains 41 reviewed vendor instruction profiles and supports approved exact supplier/part CORE rules and reusable part descriptions. No custom CORE associations or reviewed part rows had been approved when the folder was initialized.

## How PCs share

Use Invoice Labels 2026.11.22.33 or newer. Every updated PC uses this same repository. New approved vendor/CORE rules, approved edits and reviewed part changes trigger publication while the app is running. There is no 30-minute publishing schedule. A brief debounce coalesces related saves; identical knowledge creates no extra GitHub commit. Offline changes remain in the local approved database and are retried after connection failures or at the next startup.

Other PCs load the public knowledge at startup, or from Settings > Data > Shared recognition knowledge - GitHub > Check GitHub. Downloading needs no GitHub account or token. The app continues working with local knowledge offline. A PC needs an authorized GitHub writer login to publish; the app can reuse an existing noninteractive Git credential-manager login, or a fine-grained publisher token saved securely on that PC. No writer token is included with the application or this repository. Legacy private auto-sync is paused while this public source is active; its saved connection remains available for manual use.

## Duplicates and choices

Identical entries are skipped. A different version of the same supplier/part/manufacturer or vendor/CORE rule never silently overwrites the other version. The app shows both versions and lets you choose Shared or This PC. Save choices on GitHub records the choice in recognition.json under decisions, together with both content fingerprints. Updated PCs reuse that choice for that exact conflict; a later edit with different fingerprints requires another choice. New nonconflicting approved knowledge can still be shared. Concurrent writes use GitHub's current file SHA and do not force-overwrite or immediately retry a stale write.

Incoming new entries and versions covered by an exact saved choice can be applied safely. Local edits, exclusions and locally forgotten rules remain protected. Publication is additive: removing a local entry does not silently delete knowledge from everyone else's PC.

## What is excluded

Invoice originals, invoice numbers, invoice quantities and prices, history, print attempts, sign-ins, printer settings, licenses and private keys are not in this dataset. Approved rule instructions can contain illustrative extraction examples. Never upload the private recognition transfer ZIP, SQLite databases or credentials here. Applying a rule does not print anything.

For reusable parts, review the invoice, save its supplier, select the reviewed rows and use Save reviewed parts to catalog. Approve vendor/CORE rules through their normal app workflows. The app shares approved knowledge only; unreviewed OCR rows are not published.

CORE-RULES.md describes the app's CORE policy. sync-policy.json documents the shared behavior. public_knowledge.py in the application source validates this schema. Readers need no publisher access; saving a shared decision requires write access to this repository.
