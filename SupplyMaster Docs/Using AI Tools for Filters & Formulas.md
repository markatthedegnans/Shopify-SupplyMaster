---
title: "Using AI Tools for Filters & Formulas"
source: "https://help.comstack.com/en/articles/13935178-using-ai-tools-for-filters-formulas"
author:
published: 2026-03-09
created: 2026-06-11
description: "SupplyMaster includes two AI-powered tools that let you describe what you want in plain English and receive ready-to-use filters or Liqui..."
tags:
  - "clippings"
---
SupplyMaster includes two AI-powered tools that let you describe what you want in plain English and receive ready-to-use filters or Liquid formulas. Both tools are experimental and work best as a starting point that you can review and refine.

---

## AI Filter Generator

The AI Filter Generator creates product and variant filters based on a natural-language description. Instead of manually adding filter rows and choosing conditions, you describe the products you want and the AI builds the filter configuration for you.

1. Open your supplier and go to **View Products**.
2. Click **Edit Filters** to open the filter panel.
3. Click the purple magic-wand icon at the top of the filter panel.

1. The **Generate Filters with AI Assist** modal opens. Your current filters are shown on the left; the AI Assist prompt is on the right.
2. Type a description of what you want to filter. For example:
	- “Only Gildan and Bella+Canvas t-shirts”
	- “Exclude sizes 3XL through 5XL”
	- “Nike and Adidas products in black or navy”
3. Click **Generate** (or press Enter). The AI reads your supplier’s available field values and builds matching filters.
4. Review the generated filters on the left side of the modal. You can manually adjust any filter before applying.
5. Click **Apply** to save the filters, or **Discard** to close without changes.
6. If the result isn’t what you expected, click **Undo** to revert to your previous filters and try a different prompt.

[![The Generate Filters with AI Assist modal showing filter controls and AI prompt](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143324026/1cd98dd332470d1170ceec8b2264/ai-filter-generator-modal.png?expires=1781228700&signature=d187038788bc9beaa6a22530bb9717fc6220b676958782eb1603f30ddeba7619&req=diEjFcp8mYFdX%2FMW1HO4zUBLxpi7sKcyXwez6O7y8ze1SsfkqFZk55wvidw6%0AdbACbhlaP2Cwu74sGPw%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143324026/1cd98dd332470d1170ceec8b2264/ai-filter-generator-modal.png?expires=1781228700&signature=d187038788bc9beaa6a22530bb9717fc6220b676958782eb1603f30ddeba7619&req=diEjFcp8mYFdX%2FMW1HO4zUBLxpi7sKcyXwez6O7y8ze1SsfkqFZk55wvidw6%0AdbACbhlaP2Cwu74sGPw%3D%0A)

- Be specific about brand names, colors, sizes, or categories.
- Mention whether you want to *include* or *exclude* items.
- Use natural terms — the AI maps them to the correct filter fields and conditions automatically.
- You can refine iteratively: generate once, review, then type an additional prompt to adjust.

Filter history is saved automatically, so you can always restore a previous filter set from **More Actions** → **Filter History**.

---

## AI Liquid Modifier

The AI Liquid Modifier generates Liquid template code for field mapping modifiers. Instead of writing Liquid syntax yourself, you describe the transformation you need and the AI produces the code.

1. Open your supplier and go to the **Match Fields** section.
2. On any field row, click **Modify** to add a modifier (or click on an existing modifier to edit it).
3. Click the purple magic-wand icon next to the modifier text field.

[![A field mapping row showing the Modify prefix and AI magic-wand icon](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143324045/b7766869e30877a570bb786b96ad/modifier-field-with-ai-icon.png?expires=1781228700&signature=3683c4e54774f53d5047db7ef0ff5b46ae066714450e7b9ffd7d47893d5da177&req=diEjFcp8mYFbXPMW1HO4zczreIMgXmdDcG996Nbey8u%2F01rfdBGrcDEz34iI%0ANjaX3SC34Hunf%2B7ZWDk%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143324045/b7766869e30877a570bb786b96ad/modifier-field-with-ai-icon.png?expires=1781228700&signature=3683c4e54774f53d5047db7ef0ff5b46ae066714450e7b9ffd7d47893d5da177&req=diEjFcp8mYFbXPMW1HO4zczreIMgXmdDcG996Nbey8u%2F01rfdBGrcDEz34iI%0ANjaX3SC34Hunf%2B7ZWDk%3D%0A)

1. The **Edit Modifier** modal opens with two panels: **Liquid Template** on the left and **AI Assist** on the right.
2. In the AI Assist prompt, describe the transformation you need. For example:
	- “Add the brand name after the title”
	- “Mark up the price by 40% and round to 2 decimal places”
	- “If the weight is zero, default to 0.35”
	- “Prefix each category name with sub\_cat\_”
3. Click **Generate** (or press Enter). The AI writes Liquid code using the available source fields for that mapping.
4. The generated code appears in the Liquid Template editor on the left. A **Source Fields Preview** shows sample values from your supplier, and a **Shopify Preview** shows what the output looks like with real data.
5. Review the code, make any manual adjustments, and click **Apply** when satisfied.
6. Click **Undo** to revert to the previous modifier if the generated code isn’t right.

A green checkmark confirms valid Liquid syntax. If the syntax is invalid, a red indicator and error message appear so you can fix it before applying.

[![The Edit Modifier modal with Liquid Template editor and AI Assist panel](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143324073/bf6d42eb33c950d2186e1beec604/ai-modifier-modal.png?expires=1781228700&signature=163bcce2b19def7d33b2a569eb504e89eb7af0780239984ad4f54d9f398ea274&req=diEjFcp8mYFYWvMW1HO4zaLLGHjZY2GgYmFNmUF9ks4Qgl%2Bwp57bZGC5rIH2%0A7o8B%2BB%2BhGjCfqSc2Qsw%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143324073/bf6d42eb33c950d2186e1beec604/ai-modifier-modal.png?expires=1781228700&signature=163bcce2b19def7d33b2a569eb504e89eb7af0780239984ad4f54d9f398ea274&req=diEjFcp8mYFYWvMW1HO4zaLLGHjZY2GgYmFNmUF9ks4Qgl%2Bwp57bZGC5rIH2%0A7o8B%2BB%2BhGjCfqSc2Qsw%3D%0A)

- Reference field names as they appear in your source dropdown (e.g., “brandName”, “variant.piecePrice”).
- Describe the end result you want rather than the Liquid code itself.
- For math operations, mention the operator and any rounding preferences.
- For conditional logic, describe the condition and both outcomes (e.g., “if the color is blank, use the style name instead”).