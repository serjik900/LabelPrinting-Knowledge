# Shared recognition knowledge

Public reviewed part descriptions and approved vendor/CORE rules for Invoice Labels.

In the updated Windows app, open Settings > Data > Shared recognition knowledge - GitHub, or the button in Transfer recognition data. Choose Check GitHub, compare incoming entries and apply selected reviewed parts or rules. Downloading needs no account or token; local recognition works offline. Matching entries are never silently applied.

This is not an invoice backup. Invoice originals, invoice numbers, prices, quantities, history, print attempts, sign-ins, printer settings and private keys are excluded. The repository starts empty when no reusable entries have been explicitly approved. Existing built-in recognition remains available in the app.

To add reusable parts, review the invoice, save its supplier, check the intended part rows and use Save reviewed parts to catalog. Approve vendor/CORE rules through the app's normal rule workflow. Then choose Publish approved knowledge. Other PCs can check GitHub and review the additions.

Publishing requires a GitHub identity with Contents write access to this repository. Optionally save a fine-grained publisher token securely in the app and explicitly choose Publish approved knowledge. Readers need no token. Never put tokens or the private recognition transfer ZIP in this repository. Concurrent writes use the current GitHub file SHA; failures do not trigger automatic overwrites.

The schema is validated by public_knowledge.py in the application source. recognition.json is intended for app consumption. PCs need an app version that includes Public recognition knowledge.
