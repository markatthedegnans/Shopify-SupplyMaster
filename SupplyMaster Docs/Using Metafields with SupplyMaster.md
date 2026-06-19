---
title: "Using Metafields with SupplyMaster"
source: "https://help.comstack.com/en/articles/13934519-using-metafields-with-supplymaster"
author:
published: 2026-03-09
created: 2026-06-11
description: "Metafields let you store additional supplier data on your Shopify products and variants beyond the standard fields like title, price, and..."
tags:
  - "clippings"
---
Metafields let you store additional supplier data on your Shopify products and variants beyond the standard fields like title, price, and SKU. SupplyMaster can map supplier fields to both **product metafields** and **variant metafields**, and automatically creates metafield definitions in Shopify when needed. This article covers how metafield mapping works, key constraints, and practical setup examples.

---

## Product Metafields vs. Variant Metafields

Shopify has two types of metafields:

- **Product metafields** — attached to the product as a whole. Use for data that is the same across all variants (e.g., product specs, category names).
- **Variant metafields** — attached to individual variants. Use for data that differs per variant (e.g., country of origin, per-variant images, per-variant cost).

**Important:** Variant-level source fields (any field prefixed with **variant.**) can only be mapped to **variant metafields**. They cannot be mapped to product metafields, because each variant may have a different value — for example, different sizes may have different prices or come from different countries. If you need variant data at the product level, consider using a Shopify automation app to copy a specific variant's metafield to the product after import.

---

## Setting Up a Metafield Mapping

1. Navigate to **Edit Supplier** > **Product Settings** > **Match Fields**.
2. Click **Add Field** to create a new mapping row.
3. Select the supplier **source field** you want to import (e.g., **specs**, **categories**, **variant.countryOfOrigin**).
4. For the **destination**, select:
	- **Metafield** — for product-level metafields (product-level source fields only).
	- **variant.metafields** — for variant-level metafields (works with both product and variant source fields).
5. Enter the metafield **namespace and key** in the text field that appears. The format is `namespace.key` — for example, `custom.specs`, `custom.country_of_origin`, or `custom.side_image`.
6. Optionally click **Modify** to add a Liquid template that transforms the value before writing it.
7. Click **Save Supplier**.

The namespace and key must match the pattern `word.word` (letters, numbers, and underscores only). The `custom` namespace is the most common choice and is recommended for most use cases.

---

## Automatic Metafield Definitions

When SupplyMaster writes a metafield value to Shopify for the first time, Shopify automatically creates a metafield definition if one doesn't already exist. This means you don't need to manually create definitions in Shopify before mapping — SupplyMaster handles it.

Shopify supports up to 250 metafield definitions per resource type (product and variant each have their own limit). If you reach this limit, you'll need to delete unused definitions in **Shopify Admin** > **Settings** > **Custom data** before adding new mappings.

---

## Common Metafield Setups

S&S Activewear and other suppliers provide category names that you can store as metafields for use in collections or storefront display:

1. Add a mapping: source **categories** (or **categoryNames**) → destination **Metafield**.
2. Enter the namespace and key: `custom.categories`
3. Optionally use a Liquid modifier to add prefixes: `{% for category in categories_names %}sub_cat_{​{ category }​},{% endfor %}`

Category numbers can be mapped similarly using a different key (e.g., `custom.category_numbers`).

Import product specs (available on S&S Activewear and other suppliers) to a metafield for display on product pages:

1. Add a mapping: source **specs** → destination **Metafield**.
2. Enter the namespace and key: `custom.specs`

The specs data is imported as a text value. To display it as a formatted table on your product page, you'll need to add a Custom Liquid section to your Shopify theme. See our **Displaying Supplier Data on Your Shopify Theme** article for step-by-step theme setup instructions.

S&S Activewear provides relative paths for side, back, and on-model images. Store them as variant metafields with the full URL:

1. Add a mapping: source **variant.colorSideImage** → destination **variant.metafields**.
2. Enter the key: `custom.side_image`
3. Click **Modify** and enter: `https://www.ssactivewear.com/{​{ variant.colorSideImage }​}`

Repeat for other image fields as needed:

- **variant.colorBackImage** → `custom.back_image`
- **variant.colorOnModelFrontImage** → `custom.on_model_front`
- **variant.colorOnModelSideImage** → `custom.on_model_side`

These image URLs can then be displayed on your product page using a Custom Liquid section in your theme. See our **Displaying Supplier Data on Your Shopify Theme** article for the Liquid code and CSS needed.

---

Country of Origin is not a metafield — it maps to Shopify's built-in **variant.inventoryItem.countryCodeOfOrigin** field. It's included here because the setup uses the same Match Fields workflow and a Liquid modifier.

1. Add a mapping: source **variant.countryOfOrigin** → destination **variant.inventoryItem.countryCodeOfOrigin**.
2. Click **Modify** and enter: `{​{ variant.countryOfOrigin | slice: 0, 2 }​}`
3. This trims the value to the standard 2-letter country code (e.g., CN, NI, US).

After import, verify in **Shopify Admin** > **Products** > select a product > scroll to a variant > **Country/Region of origin**.

---

## Supported Metafield Types

SupplyMaster writes metafield values as text by default. Shopify will infer or use the type from an existing metafield definition. Common types that work well with supplier data:

| **Type** | **Use Case** |
| --- | --- |
| Single-line text | Country of origin, brand name, short values |
| Multi-line text | Product specs, descriptions, long-form content |
| URL | Image URLs (side/back images with URL prefix modifier) |
| Number (integer/decimal) | Numeric values like weight, dimensions |
| List of single-line text | Category names, tags (comma-separated values) |

If you need a specific type, create the metafield definition in **Shopify Admin** > **Settings** > **Custom data** before running your first import. Otherwise, Shopify will auto-create the definition based on the first value written.

---

## Troubleshooting

- Verify your field mapping in **Match Fields** — make sure the source field is correct and the namespace/key format is valid (`namespace.key`).
- Check that you're mapping variant data to **variant.metafields** (not product-level **Metafield**).
- Re-import or trigger a sync for the products. Metafield values are written during import and sync, not retroactively.
- In Shopify Admin, check **Products** > select a product > scroll to **Metafields** (or open a variant to see variant metafields).

SupplyMaster does not support mapping a variant price directly to a product metafield, since each variant can have a different price. If all variants share the same price and you need it as a product metafield, use a Shopify automation app to copy the value after import.

---

## Tips

- Use the `custom` namespace for most metafields — it's Shopify's recommended default.
- Keep namespace and key names short and descriptive: `custom.specs`, `custom.country_of_origin`, `custom.side_image`.
- Metafield values are updated on every sync according to your **Update Settings**. If you manually edit a metafield in Shopify, it may be overwritten on the next sync.
- You can map up to 25 metafields per product/variant in a single import run.