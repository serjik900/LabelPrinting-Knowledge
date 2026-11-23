# CORE recognition policy

The app shares exact supplier + part-number CORE rules through the `rules` object in recognition.json. Keys use the `core:` prefix followed by the normalized supplier, the JSON-escaped unit separator, and the exact part number. Values contain only supplier and part. No invoice or customer information belongs in these entries.

Built-in handling, already included in the Windows app:

- Recognize explicit CORE CHARGE / CHG / DEPOSIT evidence; ambiguous CORE KIT lines require review.
- Keep positive core obligations separate from merchandise and negative core credits/returns.
- Use explicitly supported unit quantities, never a charge amount as a label count.
- Require the actual associated part number; never guess it from a generic CORE row.
- Apply learned associations only to the same normalized supplier and exact part number.
- Keep print history local; applying a recognition rule does not print a label.

There are currently no approved custom supplier/part CORE associations in the published file. Approve them in the app and explicitly publish approved knowledge to make them available to other PCs. The app validates imported rules, and each PC reviews and applies incoming changes.
