---
title: "Customizing Fields with Liquid Formulas"
source: "https://help.comstack.com/en/articles/13934467-customizing-fields-with-liquid-formulas"
author:
published: 2026-03-09
created: 2026-06-11
description: "SupplyMaster's Modify button lets you write Liquid templates that transform supplier data before it reaches Shopify."
tags:
  - "clippings"
---
SupplyMaster's **Modify** button lets you write Liquid templates that transform supplier data before it reaches Shopify. You can apply markup formulas, combine fields, use conditional logic, set fallback values, and more. This article covers the full range of Liquid techniques available in field modifiers.

---

## Getting Started

1. Navigate to **Edit Supplier** > **Product Settings** > **Match Fields**.
2. Find the destination field you want to customize and click **Modify**.
3. Enter your Liquid template in the editor. You can reference any source field available for your supplier.
4. Use the **Preview** panel to check the output against real sample data from your supplier.
5. Click **Save Supplier** to apply.

Product-level fields (like **title**, **brandName**) are referenced directly. Variant-level fields use the **variant.** prefix (e.g., **variant.piecePrice**, **variant.sku**). For a complete list of fields per supplier, see our **Available Supplier Data Fields** article.

---

## Pricing & Markup Formulas

Multiply the supplier price by a factor to set your retail price:

`{​{ variant.piecePrice | times: 1.5 }​}`

This applies a 50% markup. Change `1.5` to any multiplier you need. The default SupplyMaster markup is 1.2 (20% profit margin).

Add a fixed amount on top of a percentage markup:

`{​{ variant.salePrice | times: 1.5 | plus: 22 }​}`

This multiplies the sale price by 1.5, then adds $22.

Apply different margins based on the price range:

```
{% assign p = variant.piecePrice %}
{% if p <= 10 %}{​{ p | times: 1.5 | round: 1 }​}
{% elsif p <= 30 %}{​{ p | times: 1.2 | round: 1 }​}
{% else %}{​{ p | times: 1.1 | round: 1 }​}
{% endif %}
```

Items $10 and under get a 50% markup, $10–$30 get 20%, and over $30 get 10%.

Ensure a minimum price regardless of the markup calculation:

```
{% assign calc = variant.piecePrice | times: 1.3 %}
{% if calc < 15 %}15
{% else %}{​{ calc | round: 1 }​}
{% endif %}
```

If the 30% markup results in a price below $15, the price is set to $15.

Apply different margins for different brands:

```
{% if brandName contains "Nike" %}{​{ variant.salePrice | times: 1.3 }​}
{% else %}{​{ variant.salePrice | times: 1.5 }​}
{% endif %}
```

Convert a bulk case price to a per-unit price with markup:

`{​{ variant.casePrice | divided_by: variant.caseQty | times: 1.25 | round: 2 }​}`

---

## Fallback Chains

Use the `default` filter to fall back to another field when the primary field is empty or zero:

`{​{ variant.salePrice | default: variant.customerPrice | default: variant.piecePrice }​}`

This tries **salePrice** first, then **customerPrice**, then **piecePrice**.

---

## String Formatting & Combining Fields

Build a product title from several supplier fields:

`{​{ title }​} - {​{ brandName }​} - {​{ styleName }​}`

Or use a different separator:

`{​{ title }​} | {​{ brandName }​} {​{ styleName }​}`

`{​{ brandName | upcase }​} - {​{ styleName }​}`

`CUSTOM-{​{ variant.sku }​}`

SanMar product titles often include the brand name, style number, and trademark symbols. This formula reorders the title and strips unwanted characters:

```
{​{ mill }​} {​{ styleNumber }​} {​{ title | remove: mill | remove: styleNumber | remove: "®" | remove: "™" | remove: "." | replace: "  ", " " | strip }​}
```

**Before:** "Sport-Tek ® Colorblock Raglan Anorak. JST63"  
**After:** "Sport-Tek JST63 Colorblock Raglan Anorak"

---

## Weight Conversion

Convert ounces to pounds:

`{​{ variant.pieceWeight | divided_by: 16 | round: 2 }​}`

Set a default weight when the supplier reports zero:

`{% if variant.weight == 0 %}0.35{% else %}{​{ variant.weight }​}{% endif %}`

---

## Country of Origin

S&S Activewear provides a **countryOfOrigin** field on each variant. Some entries include extra characters beyond the 2-letter country code. Use the `slice` filter to trim it:

`{​{ variant.countryOfOrigin | slice: 0, 2 }​}`

This always sends the standard 2-letter code (e.g., CN, NI, US) to Shopify's **Country of Origin** field. Map it to the destination **variant.inventoryItem.countryCodeOfOrigin**.

---

## Image URL Prefixes

Some suppliers provide relative image paths rather than full URLs. Use a modifier to prepend the base URL. For S&S Activewear side images:

`https://www.ssactivewear.com/{​{ variant.colorSideImage }​}`

This works for any image field — swap **colorSideImage** for **colorBackImage**, **colorOnModelFrontImage**, etc. Map the result to a **Variant Metafield** to store the image URL. See our **Using Metafields with SupplyMaster** article for setup details.

---

## Category Name Prefixes

Add a prefix to each category name so supplier categories are easy to distinguish from your own tags:

`{% for category in categories_names %}sub_cat_{​{ category }​},{% endfor %}`

This produces tags like `sub_cat_T-Shirts`, `sub_cat_Polos`, `sub_cat_Fleece`.

---

## Liquid Syntax Reference

| **Filter** | **Example** | **Result** |
| --- | --- | --- |
| `times` | `{​{ 10 \| times: 1.5 }​}` | 15 |
| `divided_by` | `{​{ 100 \| divided_by: 3 \| round: 2 }​}` | 33.33 |
| `plus` | `{​{ 10 \| plus: 5 }​}` | 15 |
| `minus` | `{​{ 10 \| minus: 3 }​}` | 7 |
| `modulo` | `{​{ 10 \| modulo: 3 }​}` | 1 |
| `round` | `{​{ 4.567 \| round: 2 }​}` | 4.57 |
| `ceil` | `{​{ 4.1 \| ceil }​}` | 5 |
| `floor` | `{​{ 4.9 \| floor }​}` | 4 |

| **Filter** | **Description** |
| --- | --- |
| `upcase` | Converts to uppercase |
| `downcase` | Converts to lowercase |
| `capitalize` | Capitalizes first letter |
| `append` | Adds text to end: `{​{ "hello" \| append: " world" }​}` |
| `prepend` | Adds text to beginning |
| `replace` | Replaces text: `{​{ title \| replace: "old", "new" }​}` |
| `remove` | Removes text: `{​{ title \| remove: "®" }​}` |
| `strip` | Removes leading and trailing whitespace |
| `truncate` | Limits string length: `{​{ title \| truncate: 50 }​}` |
| `slice` | Extracts substring: `{​{ field \| slice: 0, 2 }​}` |
| `default` | Fallback value: `{​{ field \| default: "N/A" }​}` |

Use `if`, `elsif`, and `else` for branching:

`{% if condition %}...{% elsif other %}...{% else %}...{% endif %}`

Available operators: `==`, `!=`, `<`, `>`, `<=`, `>=`, `contains`, `and`, `or`

Assign intermediate values with `assign`:

`{% assign markup = variant.piecePrice | times: 1.3 %}`

---

## Tips

- Always use the **Preview** panel to test your formula against real supplier data before saving.
- Use **AI Assist** in the Modify editor — describe what you want in plain English and SupplyMaster will generate the Liquid code for you.
- Chain multiple filters left to right: `{​{ variant.price | times: 1.5 | plus: 2 | round: 2 }​}`.
- If your modifier produces unexpected results, check that you're using the correct field prefix (**variant.** for variant fields, no prefix for product fields).