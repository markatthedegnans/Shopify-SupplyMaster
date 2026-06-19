---
title: "Variant Splitting (Legacy Feature)"
source: "https://help.comstack.com/en/articles/13933800-variant-splitting-legacy-feature"
author:
published: 2026-05-27
created: 2026-06-11
description: "Variant splitting is a legacy feature in SupplyMaster."
tags:
  - "clippings"
---
Variant splitting is a **legacy feature** in SupplyMaster. It was originally built when Shopify limited products to 100 variants each. Shopify has since raised that limit to **2,048 variants per product** for all stores, meaning virtually all supplier products now fit in a single Shopify product without splitting.

**If you are setting up a new supplier, you can skip this article entirely.** The default settings already use the 2,048-variant limit, and no splitting is needed.

This feature remains available only to support stores that originally imported products under the old 100-variant limit and already have split products in their Shopify store. Those stores need the setting to remain so their existing split products continue to sync correctly.

---

## Background: The Old 100-Variant Limit

Shopify previously limited each product to 100 variants (each unique size/color combination counts as one variant). A t-shirt with 20 colors and 8 sizes has 160 variants (20 × 8 = 160), which exceeded the old limit. SupplyMaster provided variant splitting to work around this by breaking large products into smaller ones.

Shopify has since increased the per-product limit to **2,048 variants** for all stores. At this limit, even the largest supplier products fit comfortably without splitting.

---

## Do I Need Variant Splitting?

| **Situation** | **Do You Need Splitting?** |
| --- | --- |
| New supplier setup | **No.** The default 2,048-variant limit handles all supplier products without splitting. |
| Existing store with split products from the old 100-variant limit | **Yes — keep your current settings.** Changing them could break the link between your existing split products and the supplier data. |

---

## How Variant Splitting Works

For stores still using the legacy 100-variant limit, the **Handle Variant Limit** setting determines what happens when a product exceeds the limit:

| **Strategy** | **What It Does** | **Example** |
| --- | --- | --- |
| Split by Color | Creates a separate Shopify product for each color. Each product contains all sizes in that color. | “Gildan T-Shirt - Red” (all sizes in Red), “Gildan T-Shirt - Blue” (all sizes in Blue) |
| Split by Size | Creates a separate Shopify product for each size. Each product contains all colors in that size. | “Gildan T-Shirt - Small” (all colors in Small), “Gildan T-Shirt - Large” (all colors in Large) |
| Limit to Max Variants | Imports only up to the maximum number of variants. Additional variants beyond the limit are not imported. | A product with 160 variants under the 100-variant limit would import only the first 100 variants. |

**Split by Color** is the most common choice. It keeps all sizes together on one product page, which is the way most customers shop for apparel.

---

## Configuring Variant Splitting (Legacy Stores Only)

1. Go to **Edit Supplier** > **Automatic Sync** tab.
2. Find the **Maximum Variants Per Product** setting and set it to **100 Variants (Legacy)**.
3. Set **Handle Variant Limit** to your preferred strategy (Split by Color, Split by Size, or Limit to Max Variants).

[![The Handle Variant Limit dropdown and Maximum Variants Per Product settings](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2430465410/639875e795c00ad06f386e7d5f57/variant-splitting-dropdown.png?expires=1781227800&signature=51b14dd336170f1dde01ab7562079c3efa5bb32872d2bd024ab330929cdc5035&req=diQkFs14mIVeWfMW1HO4zTLsM12bksPMDI0ZAzNuk6I9fB%2F91hnl%2B1Jq8lG2%0AfMvnpF6a2WQDoMVK1Yg%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2430465410/639875e795c00ad06f386e7d5f57/variant-splitting-dropdown.png?expires=1781227800&signature=51b14dd336170f1dde01ab7562079c3efa5bb32872d2bd024ab330929cdc5035&req=diQkFs14mIVeWfMW1HO4zTLsM12bksPMDI0ZAzNuk6I9fB%2F91hnl%2B1Jq8lG2%0AfMvnpF6a2WQDoMVK1Yg%3D%0A)

---

## Customizing Split Product Titles

When products are split by color or size, SupplyMaster generates a new title for each split product. You can customize this title using a Liquid template.

`{​{ title }​} - {​{ key }​}`

This produces titles like “Gildan T-Shirt - Red” or “Gildan T-Shirt - Small” depending on the split type.

You can change the format to suit your store. For example:

| **Template** | **Result** |
| --- | --- |
| `{​{ title }​} - {​{ key }​}` | Gildan T-Shirt - Red |
| `{​{ title }​} ({​{ key }​})` | Gildan T-Shirt (Red) |
| `{​{ title }​} \| {​{ key }​}` | Gildan T-Shirt \| Red |

`{​{ title }​}` is the original product title from the supplier, and `{​{ key }​}` is the split value (the color name or size name).

1. Go to **Edit Supplier** > **Automatic Sync** tab.
2. Set **Handle Variant Limit** to either **Split by Color** or **Split by Size**.
3. The **Title for Split Products** field appears. Enter your Liquid template.

[![The Title for Split Products template field with the default Liquid template](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2430465429/f3370cbb1b8d378125679afec9a7/title-template-field.png?expires=1781227800&signature=8156320c5ecc7d7b177e5ac100ea5b4e0f6de04b19671b3cb0d68a892637fcd9&req=diQkFs14mIVdUPMW1HO4zXNuzzDL5wZ%2BeAhszx9MRBGOfN11wAQ8NhRrPXa1%0AXrZQVz5pKu60wyLX07U%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2430465429/f3370cbb1b8d378125679afec9a7/title-template-field.png?expires=1781227800&signature=8156320c5ecc7d7b177e5ac100ea5b4e0f6de04b19671b3cb0d68a892637fcd9&req=diQkFs14mIVdUPMW1HO4zXNuzzDL5wZ%2BeAhszx9MRBGOfN11wAQ8NhRrPXa1%0AXrZQVz5pKu60wyLX07U%3D%0A)

---

## Shopify Store-Wide Variant Limit

Separate from per-product variant limits, Shopify also caps the rate of **new variant creation** on large stores: non-Plus stores with 50,000+ variants can add up to 1,000 new variants per day. SupplyMaster manages this automatically. See our **Shopify's Daily Variant Creation Limit** article for details.