---
title: "Glossary of Terms"
source: "https://help.comstack.com/en/articles/13940839-glossary-of-terms"
author:
published: 2026-03-09
created: 2026-06-11
description: "A quick reference for terms used throughout SupplyMaster and this Help Center."
tags:
  - "clippings"
---
## Archive

Archiving is a Shopify product status that hides a product from your storefront and sales channels without deleting it. In SupplyMaster, the **Action on Unavailable Products** setting can automatically archive products that are no longer in the supplier catalog or no longer match your filters.

---

## Auto Sync

Automatic synchronization of products from a supplier to your Shopify store. When enabled, SupplyMaster fetches the supplier catalog, applies your filters, and creates or updates products on a schedule. The **Auto Import** toggle on each supplier card is a quick on/off control; for detailed options, use **Edit Supplier** → **Automatic Sync**, where you configure sync frequency (Daily or Every 6 Hours), Update Settings, Auto Create rules, and Action on Unavailable Products. See our **How Automatic Syncing Works** article for details.

---

## Field Mapping

The configuration that controls how supplier data fields are matched to Shopify product and variant fields during import. For example, you can map the supplier's **title** to Shopify's **Title**, or **variant.price** to **Price** with a markup modifier. Field mappings are configured under **Edit Supplier** → **Product Settings** → **Match Fields**. See our **Mapping Supplier Fields to Shopify** article.

---

## Filter History

A list of saved filter configurations for a supplier. SupplyMaster stores up to 20 entries per supplier so you can view or restore previous filter setups. Open it from **Products for Import** → **Edit Filters** → **More Actions** → **Filter History**. Useful when you experiment with filters and need to revert to a known working set.

---

## Manual Import

A product import you trigger yourself, on demand. Go to the supplier’s **Products for Import** tab, configure your filters, then click **Import Products**. SupplyMaster fetches the supplier catalog, applies your filters, and creates or updates products in your store. Manual imports run immediately; automatic syncs run on a schedule. To avoid conflicts, turn off auto sync before running a manual import.

---

## Metafield

A custom data field in Shopify that stores additional information beyond the standard product and variant fields. SupplyMaster can map supplier data (e.g., specs, category names, image URLs) to product or variant metafields. Shopify automatically creates metafield definitions when SupplyMaster writes a value for the first time. See our **Using Metafields with SupplyMaster** article.

---

## Modifier

A Liquid code template applied to a field mapping that transforms the supplier data before it is written to Shopify. Common uses include price markup (`{​{ variant.price | times: 1.5 | round: 2 }​}`), URL prefixes for image paths, weight fallbacks, and text formatting. Modifiers are set by clicking the **Modify** button on any mapped field. See our **Customizing Fields with Liquid Formulas** article.

---

## Product Mapping

A manual link between an existing Shopify product and a supplier product. Product mappings let you connect products that were not originally created by SupplyMaster — for example, products with customized images or descriptions — so they receive inventory and pricing updates from the supplier. Variant-level mappings control which Shopify variant maps to which supplier variant. See our **Linking Existing Products to Supplier Inventory** article.

---

## Product Update

A single write operation where SupplyMaster updates one product's data in Shopify during an import or sync. Product updates count toward your plan's monthly update limit. Each product touched during a sync — whether its inventory, price, title, or any other field changes — counts as one product update.

---

## Publish Channel

A Shopify sales channel where imported products are made available for sale. When you configure a supplier, you choose which channels (e.g., Online Store, Point of Sale, Google & YouTube) products should be published to after import. This is set under **Edit Supplier** → **Product Settings** → **Product Sales Channels**.

---

## SKU

Stock Keeping Unit — a unique identifier for a specific product variant. Each supplier assigns SKUs to their variants, and SupplyMaster maps them to Shopify's **SKU** field by default. SKUs are used for inventory tracking, order fulfillment, and linking variants between the supplier and your store.

---

## Supplier Type

The identifier for a supplier integration in SupplyMaster (e.g., S&S Activewear, SanMar, AlphaBroder). Each supplier type has its own set of credentials, available fields, filter options, and sync features. You select the supplier type when adding a new supplier.

---

## Variant

A specific version of a product defined by its options — typically color and size. For example, a “Gildan 5000 T-Shirt” in Red / Medium is one variant, while Red / Large is another. Shopify supports up to 2,048 variants per product. Variants carry their own SKU, price, inventory, and weight. Your plan’s variant limit counts all variants across all supplier-imported products in your store.

---

## Variant Splitting

A legacy SupplyMaster feature that splits products exceeding the variant limit into multiple Shopify products. This was originally needed when Shopify limited products to 100 variants. Since Shopify now supports 2,048 variants per product, splitting is no longer required for new setups. It remains available to support stores that already have split products from the old limit. Products can be split by **Color** or by **Size**, with a customizable title template. Configured under **Auto Sync Settings** → **Handle Variant Limit**. See our **Variant Splitting (Legacy Feature)** article.