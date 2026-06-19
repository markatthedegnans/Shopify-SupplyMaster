---
title: "Mapping Supplier Fields to Shopify"
source: "https://help.comstack.com/en/articles/13934405-mapping-supplier-fields-to-shopify"
author:
published: 2026-03-09
created: 2026-06-11
description: "SupplyMaster's Match Fields feature controls how supplier data flows into your Shopify products."
tags:
  - "clippings"
---
SupplyMaster's **Match Fields** feature controls how supplier data flows into your Shopify products. Each mapping connects a supplier source field (like brand name, price, or SKU) to a Shopify destination field (like Title, Variant Price, or Tags). This article explains how Match Fields works, what you can map, and how to customize mappings with the **Modify** button.

---

## How Match Fields Works

Every supplier comes with a set of default field mappings that handle the most common use cases out of the box. For most stores, the default fields and mapping will work without any changes.

Each mapping row has three parts:

1. **Source field** — the data coming from your supplier (e.g., **brandName**, **piecePrice**).
2. **Destination field** — where the data lands in Shopify (e.g., **Title**, **Variant Price**, **Tags**).
3. **Modify** button — opens a Liquid template editor so you can transform the data before it reaches Shopify.

When you run an import or sync, SupplyMaster reads each mapping and writes the source value into the corresponding Shopify field. If a modifier is set, the value is processed through the Liquid template first.

Navigate to **Edit Supplier** > **Product Settings** tab > **Match Fields** section.

[![The Match Fields section showing source-to-destination mapping rows with Modify buttons, Add Field, Restore Default Fields, and Enable AI+ Data options](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321726/a74f3ef33b38f4dab98443501ef8/match-fields-overview.png?expires=1781227800&signature=4496776390cba6109c165593670a8ef9a27aa36297ad7be9c123f1dfb84e21cd&req=diEjFcp8nIZdX%2FMW1HO4zWD5bqY7%2F62L%2BVMMCtj%2FNzTeKLHNVUUdS8lkQjs%2B%0AvZ3MnYM81WeHV%2BGA0pY%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321726/a74f3ef33b38f4dab98443501ef8/match-fields-overview.png?expires=1781227800&signature=4496776390cba6109c165593670a8ef9a27aa36297ad7be9c123f1dfb84e21cd&req=diEjFcp8nIZdX%2FMW1HO4zWD5bqY7%2F62L%2BVMMCtj%2FNzTeKLHNVUUdS8lkQjs%2B%0AvZ3MnYM81WeHV%2BGA0pY%3D%0A)

---

## Available Shopify Destination Fields

You can map supplier data to any of these Shopify fields:

| **Category** | **Destination Fields** |
| --- | --- |
| Product-level | Title, Handle, Description (HTML), Product Type, Vendor, Category, Tags, Status, SEO Title, SEO Description, Metafield |
| Variant-level | SKU, Barcode, Price, Compare At Price, Cost per Item, Country of Origin, Weight, Weight Unit, Position, Tax Code, Taxable, Inventory Policy, Variant Metafields |

**Important:** Variant-level source fields can only be mapped to variant-level destinations. Product-level source fields can be mapped to either product or variant destinations. For a complete list of source fields available for each supplier, see our **Available Supplier Data Fields** article.

---

## Adding & Removing Mappings

1. In the **Match Fields** section, click **Add Field** to create a new mapping row.
2. Select a **Source** field from the left dropdown.
3. Select a **Destination** field from the right dropdown.
4. To remove a mapping, click the delete icon on the right side of the row.
5. Click **Save Supplier** to apply your changes.

Some default mappings are marked as not editable — these are required for SupplyMaster to function correctly and cannot be removed.

---

## Using the Modify Button

The **Modify** button next to each destination field opens a Liquid template editor. Modifiers let you transform, combine, or calculate values before they are written to Shopify.

Click **Modify** on any mapping row to open the editor. You can:

- Write Liquid code directly in the template field.
- Use **AI Assist** to describe what you want in plain English and have SupplyMaster generate the Liquid code for you.
- Preview the output against real sample data from your supplier before saving.

The image below shows the **AI Assist** interface within the modifier editor, where you can enter a plain-English prompt to generate Liquid code automatically.

[![The AI Assist interface within the modifier editor showing a prompt input, generated Liquid template, and preview pane](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321775/bd6b9ed11896ba9fd1029fe4f2bb/modify-liquid-editor.png?expires=1781227800&signature=6305c02a8ba5fc93a3707288680bad9baf72004bbc4fdb9838aa9200bb171449&req=diEjFcp8nIZYXPMW1HO4zauJCgt%2FR9BoGmvh94NbYbB5T0BXxgciZjzo3niW%0AGP1JEMZ8039jtMDz7Ak%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321775/bd6b9ed11896ba9fd1029fe4f2bb/modify-liquid-editor.png?expires=1781227800&signature=6305c02a8ba5fc93a3707288680bad9baf72004bbc4fdb9838aa9200bb171449&req=diEjFcp8nIZYXPMW1HO4zauJCgt%2FR9BoGmvh94NbYbB5T0BXxgciZjzo3niW%0AGP1JEMZ8039jtMDz7Ak%3D%0A)

| **Goal** | **Liquid Template** |
| --- | --- |
| Multiply price by 2.5 | `{​{ price \| times: 2.5 \| round: 2 }​}` |
| Set default weight when missing | `{% if weight == 0 %}0.35{% else %}{​{ weight }​}{% endif %}` |
| Combine title, brand, and style | `{​{ title }​} - {​{ brandName }​} - {​{ styleName }​}` |

For a full guide to Liquid formulas — including math, string filters, conditional logic, tiered pricing, and more — see our **Customizing Fields with Liquid Formulas** article.

---

## Default Profit Margin

By default, SupplyMaster applies a profit margin to the **Variant Price** field for your supplier. This means the supplier's cost is multiplied before being written to your Shopify price. For example, if the default margin is 1.2× and the supplier price is $10.00, the Shopify price will be set to $12.00.

To change the default margin:

1. Navigate to **Edit Supplier** > **Product Settings** > **Match Fields**.
2. Find the **Variant Price** row and click **Modify**.
3. Edit the multiplier in the Liquid template. For example, change `{​{ piecePrice | times: 1.2 }​}` to `{​{ piecePrice | times: 1.5 }​}` for a 50% margin, or `{​{ piecePrice | times: 2.5 | round: 2 }​}` for a 150% markup.
4. Preview the result, then click **Save Supplier**.

The profit margin applies on every import and sync, so your prices stay consistent as supplier costs change. If your supplier has a sale, the new price is automatically reflected with your margin applied.

---

## Mapping Category Names to Tags or Metafields

Some suppliers (like S&S Activewear) provide category name data that you can map to Shopify **Tags** or **Metafields**. This is useful for creating automated collections or displaying category information on product pages.

- **Map to Tags:** Add a mapping with **categories** (or **categoryNames**) as the source and **Tags** as the destination. Category values are imported as comma-separated tags.
- **Map to Metafields:** Set the destination to **Metafield** and enter a namespace and key (e.g., `custom.categories`). The category data is stored as a metafield value.

You can also add a prefix to each category name using a Liquid modifier. For example, to prefix each category with `SM_`:

`{% for category in categories_names %}SM_{​{ category }​},{% endfor %}`

This produces tags like `SM_T-Shirts`, `SM_Polos`, making it easy to distinguish supplier categories from your own tags. For more on metafield mapping, see our **Using Metafields with SupplyMaster** article.

---

## AI+ Default Mappings

[![The Match Fields header showing the Enable AI+ Data button, Restore Default Fields button, and Add Field button](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321803/ea22512475987d5b621e2615e3a7/ai-plus-default-mappings-button.png?expires=1781227800&signature=34b8183747de433bdf0472fb979201c9c8a7285b6beee5a70cd76deb3e32b525&req=diEjFcp8nIlfWvMW1HO4zSddOYy0iVjrsorGrS7b6XzCjkpCoGc9EYJfQChg%0AIYp1giF0itX5qEoDcoc%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321803/ea22512475987d5b621e2615e3a7/ai-plus-default-mappings-button.png?expires=1781227800&signature=34b8183747de433bdf0472fb979201c9c8a7285b6beee5a70cd76deb3e32b525&req=diEjFcp8nIlfWvMW1HO4zSddOYy0iVjrsorGrS7b6XzCjkpCoGc9EYJfQChg%0AIYp1giF0itX5qEoDcoc%3D%0A)

If you have **AI+** enabled for a supplier, SupplyMaster provides enriched default mappings that include AI-generated fields such as SEO titles, SEO descriptions, clean handles, categorization, and formatted product descriptions. These mappings are applied automatically when AI+ is active.

To load AI+ defaults, click **AI+ Default Mappings** at the top of the Match Fields section. You can still customize any AI+ mapping using the **Modify** button. For more details, see our **AI+ Enriched Product Data** article.

---

## Restoring Default Mappings

If you've made changes and want to start over, click **Restore Default Fields** at the top of the Match Fields section. This resets all mappings to the supplier's default configuration. Any custom modifiers you've added will be removed.

---

## Tips

- Start with the defaults — they cover title, description, price, SKU, weight, images, and inventory for most suppliers.
- Use the preview in the Modify editor to check your formulas against real data before saving.
- If you only need inventory updates and want to keep your own product titles and descriptions, adjust your **Update Settings** in the Automatic Sync tab rather than removing field mappings.
- Mapping changes take effect on the next import or sync. Existing products are updated according to your **Update Settings**.