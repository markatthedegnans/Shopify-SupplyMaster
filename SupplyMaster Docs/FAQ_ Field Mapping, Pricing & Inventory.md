---
title: "FAQ: Field Mapping, Pricing & Inventory"
source: "https://help.comstack.com/en/articles/13935312-faq-field-mapping-pricing-inventory"
author:
published: 2026-03-09
created: 2026-06-11
description: "Common questions about mapping supplier fields to Shopify, price formulas, metafields, and inventory sync."
tags:
  - "clippings"
---
## Price & Cost Mapping

Go to **Edit Supplier** → **Match Fields**. Find the row for **Cost per item** and set the source to the supplier’s case price (or piece price, depending on your cost basis). This populates Shopify’s cost field so you can track margins and calculate profit.

Yes. If your supplier updates their pricing (including promotional or sale prices), SupplyMaster will automatically update the mapped price fields in your Shopify store on the next sync, based on your field mapping settings and Liquid formulas.

---

## Sync Scope

Only products currently included in your active filters. If you remove a product from your filters, it will no longer receive price or inventory updates. It stays in your Shopify store but is no longer managed by SupplyMaster.

---

## Metafields

No. Variant data can only be mapped to variant metafields. Product metafields cannot be populated with variant-level data because each variant may have a different value (e.g., a different price per size). If you need variant data at the product level, consider using a Shopify automation app to copy from variant metafields to product metafields.

Not directly. Since each variant can have a different price, SupplyMaster cannot map a single variant price to a product-level field. If all variants share the same price, an automation app can copy it from a variant metafield to a product metafield.

Check these common causes:

- **Mapping direction** — make sure you are mapping to a variant metafield (not a product metafield) when using variant-level data.
- **Metafield namespace and key** — verify the namespace and key in Match Fields match what you expect in Shopify (e.g., `custom.specs`).
- **Filter cache** — try clearing your filter cache and re-importing.
- **Sync timing** — metafields are populated during import/sync, not retroactively. If you added the mapping after the initial import, run a new sync to populate existing products.

---

## Liquid Templates & Formulas

Use a Liquid template in the **Modify** field. For example:

```
{​{ title }​} | {​{ brandName }​} {​{ styleName }​}
```

This combines the product title, brand name, and style name into one formatted string. You can use any source fields available for your supplier.

Use this Liquid template in the **Title** modifier:

```
{​{ mill }​} {​{ styleNumber }​} {​{ title | remove: mill | remove: styleNumber | remove: "®" | remove: "™" | remove: "." | replace: "  ", " " | strip }​}
```

This turns “Sport-Tek ® Colorblock Raglan Anorak. JST63” into “Sport-Tek JST63 Colorblock Raglan Anorak.” Key SanMar fields: `mill` (brand), `styleNumber` (item number), `title` (full original title).

For more Liquid examples including price markup, tiered pricing, conditional logic, and fallback chains, see our **Customizing Fields with Liquid Formulas** article.

---

## Tags & Categories

In **Match Fields**, map a source field to the **Tags** destination. You can map multiple sources to Tags — for example, map `brandName` to Tags and also map `AI_tags` to Tags. Each source adds to the tag list. You can also use a Liquid modifier to format tag values (e.g., prefix with a category label).

Create multiple supplier connections, each with its own filters and tag mappings. For example, set up one supplier for men’s apparel with a “Mens” tag and another for women’s with a “Womens” tag. Each supplier can have different filters, field mappings, and tag configurations. Note: products imported for the first time via a new supplier connection will be created as new products in Shopify.

---

## Images & Specs

SupplyMaster does not currently support selecting specific images during import. All available images from the supplier are imported. This feature is being considered for a future release.

Yes. Map the supplier’s specs field to a metafield (e.g., `custom.specs`) in Match Fields. To display the specs as a tab on your product page, add a Custom Liquid section in your Shopify theme. See our **Displaying Supplier Data on Your Shopify Theme** article for step-by-step instructions and code examples.