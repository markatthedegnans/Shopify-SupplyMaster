---
title: "FAQ: Importing, Filtering & Syncing"
source: "https://help.comstack.com/en/articles/13935280-faq-importing-filtering-syncing"
author:
published: 2026-05-27
created: 2026-06-11
description: "Common questions about importing products, setting up filters, managing variants, and syncing data with SupplyMaster."
tags:
  - "clippings"
---
## Filters & Product Selection

Go to **View Products** → **Edit Filters**. You can add product filters (e.g., Brand Name, Style Number, Category) and variant filters (e.g., Color Name, Size) to control exactly which items are imported.

Products may appear by default depending on your supplier configuration. Go to **View Products** → **Edit Filters** to include or exclude specific brands or products. Without filters, your supplier’s entire catalog may be imported. Always configure filters before enabling Auto Import.

Use the **Contains Any** condition. Add a product filter for **Brand Name**, set the condition to **Contains Any**, and enter your brands separated by commas (e.g., `Sport-Tek, Nike, New Era`). All products matching any of the listed brands will be included.

Use the **Not Equal To Any** condition. Add a product filter for **Brand Name** (or **Mill**, depending on your supplier), set the condition to **Not Equal To Any**, and enter the brands to exclude. All products except those brands will be included.

Add a product filter for **Style Number** (or **Part Number**), set the condition to **Contains Any**, and enter a comma-separated list of style IDs (e.g., `PTS30, PTS20, 112P`). This is more efficient than creating multiple separate filters.

Use variant filters. Go to **Edit Filters**, add a **Variant Filter**, and select the attribute (e.g., **Color Name** or **Size Name**). Set the condition to **Equal To Any** or **Contains Any** and enter your values. For example:

- **Size Name** — Equal To Any — `S, M, L, XL, 2XL, 3XL`
- **Color Name** — Contains Any — `Black, White, Navy, Red`

Both filters combined with “And” import only variants matching both conditions.

Yes. Filters determine which products SupplyMaster actively manages and syncs. If you remove a product from your filters and run a sync, that product will no longer receive inventory or pricing updates. It remains in your Shopify store but is no longer managed by SupplyMaster.

Use a single filter with all style numbers separated by commas (e.g., `PTS30, PTS20, 112P`) with the **Contains Any** or **Equal To Any** condition. This is easier to manage than multiple separate filters connected by “OR.”

---

## Importing Products

Create a second supplier connection for the alternate version and add all relevant styles to that supplier. This maintains distinct product listings while keeping inventory synced for both through SupplyMaster.

No. In the supplier’s database and in Shopify, each variant is defined by the full combination of color and size. SKUs, barcodes, prices, and weights are all tied to complete variant combinations. You must sync the full variant set, but you can use variant filters to limit which sizes and colors are included.

Use a variant filter for **Size Name** set to **Equal To Any** with only the sizes you want (e.g., `S, M, L, XL`). You can do the same for **Color Name**. This gives you a curated catalog with only the variants you want to sell. You can also hide the size selector on your storefront using theme customization if needed.

No. SupplyMaster requires a paid Shopify plan. Development and trial stores are not supported.

---

## Variant Limits

Each unique combination of size, color, and other options is one variant. A t-shirt with 5 sizes and 20 colors = 100 variants (5 × 20). Your subscription tier is based on total variant count.

A product update is one refresh of a variant’s data (inventory, price, fields) from the supplier. If you have 3,000 variants syncing daily, that’s 3,000 updates per day or about 90,000 per month.

Almost certainly not. Shopify now supports **2,048 variants per product** for all stores, which is enough to handle virtually every supplier product without splitting. Variant splitting is a legacy feature that exists only to support stores that originally imported products under the old 100-variant limit and already have split products in their store. New setups do not need it. See our **Variant Splitting (Legacy Feature)** article for details.

Once your Shopify store reaches 50,000 variants, Shopify caps new variant uploads at 1,000 per day on non-Plus stores. SupplyMaster handles this automatically — with Auto Sync on, variants are created daily over time, and merchants have scaled to 100,000+ variants this way. Shopify Plus stores are not subject to this cap. See our **Shopify's Daily Variant Creation Limit** article.

---

## Images

SupplyMaster does not support changing which image is the default/featured image. Image URLs can be imported as metafields, but they won’t replace the main product image.

Shopify allows only one image per variant by default. You can import additional image URLs (e.g., side and back images) as metafields using Match Fields, then display them on your storefront with theme customization. See our **Displaying Supplier Data on Your Shopify Theme** article.

The most reliable fix is to delete those products from your Shopify store. SupplyMaster will recreate them with complete data (including images) on the next sync. Waiting for a sync to fix missing images on existing products may not work unless **Always Update Variant Images** is enabled.

---

## Syncing & Updates

Yes. Newly imported products always receive images on their first import, regardless of Update Settings. The “All Fields Except Images” setting only applies to existing products that have been in your store for more than 2 hours. This grace period ensures new products are fully populated.

Check the **Sync History** tab for status updates. If you see a failed import or the issue persists for more than an hour, contact support. Common causes include temporary supplier API issues, large catalog sizes, or subscription limits being reached.

SupplyMaster does not have a built-in option for this. However, you can bulk-edit products in Shopify to enable “Continue selling when sold out.”

Different suppliers have different product IDs, APIs, and data formats. Shopify treats imported products from a new supplier as new products. To manage duplicates, turn on auto-archive for the old supplier, modify its filters so no products are selected, and run a sync to archive old products. You will still need to reassign metafields, categories, and collections on the new products.

---

## Inventory & Locations

Go to **Edit Supplier** → **Inventory Settings**. Select the Shopify location and choose which supplier warehouse to map. Warehouse-level inventory is supported for:

- **S&S Activewear** — individual U.S. and Canadian warehouses (e.g., Reading PA, Jacksonville FL, Olathe KS, and more)
- **AlphaBroder** — All Inventory or Dropshipping Inventory Only

SanMar and other suppliers currently provide only total inventory quantities, not warehouse-level breakdowns.

Inventory levels are visible in your Shopify admin but are not automatically displayed to storefront visitors. To show stock levels to customers, customize your theme or use a Shopify app. See this [Shopify Community discussion](https://community.shopify.com/c/shopify-design/how-to-display-stock-levels-in-dawn-product-pages/m-p/1962171).

This is a Shopify setting, not a SupplyMaster feature. Go to your Shopify admin and configure your theme or collection settings to hide out-of-stock products. See Shopify’s [guide on hiding sold-out variants](https://help.shopify.com/en/manual/online-store/themes/customizing-themes/product-pages#hide-sold-out-variants).

---

## Deleting & Archiving Products

Yes. If the products are still in the supplier’s catalog and still match your active filters, SupplyMaster will recreate them on the next sync. To prevent this, update your filters to exclude those products *before* deleting them from Shopify.

1. **Exclude from filters** — go to **Edit Filters** and remove the products you want to delete.
2. **Enable auto-archive** — in **Automatic Sync**, set **Action on Unavailable Products** to **Archive Products**.
3. **Run a sync** — SupplyMaster will archive the excluded products.
4. **Review and delete** — in Shopify admin, filter to “Archived” products, review, and permanently delete.

This method is safe (archive first, delete second) and prevents SupplyMaster from recreating deleted products on future syncs.

---

## Auto Create Settings

The **Auto Create Products & Variants** setting (in **Edit Supplier** → **Automatic Sync**) offers four levels:

- **Always Create Products & Variants** (default) — full automation for resellers.
- **No New Variants on Existing Products** — protects customized variant selections for decorators.
- **No New Products** — updates existing products but doesn’t add new product lines, for curated catalogs.
- **No New Products or Variants** — only pricing, inventory, and data updates, for finalized catalogs.

This setting can be configured per supplier and applies to both automatic and manual imports.

---

## Other

Go to **Match Fields**, find the **Vendor** row, click **Modify**, and enter your custom vendor name or a Liquid formula.

SanMar specification PDF links can be mapped to a product metafield using Match Fields. After importing, display the PDF links on your storefront using Custom Liquid in your theme. See this [Shopify Community discussion](https://community.shopify.com/c/shopify-discussions/opening-a-pdf-image-file-metafield-as-a-pop-up-in-product-page/td-p/2548944) for implementation examples.