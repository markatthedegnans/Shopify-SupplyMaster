---
title: "Supplier Configuration Reference"
source: "https://help.comstack.com/en/articles/13940840-supplier-configuration-reference"
author:
published: 2026-06-01
created: 2026-06-11
description: "A reference for all suppliers integrated with SupplyMaster, including connection requirements and key features."
tags:
  - "clippings"
---
## 1\. Supported Suppliers Overview

SupplyMaster connects to the following suppliers. Each has different connection requirements and features.

| **Supplier** | **Connection Type** | **Order Sync** | **AI+ Enrichment** |
| --- | --- | --- | --- |
| SS Activewear | Account number + API key | Yes | Yes |
| Sanmar | FTP username & password (product sync); separate PromoStandards Username & Password for orders | Yes (PromoStandards) | Yes |
| Alphabroder | Username & password | No | Yes |
| Cap America | Username & password | No | Yes |
| Otto Cap | Username & password | No | Yes |
| Goldstar | Username & password | No | Yes |
| Charles River Apparel | Username & password | No | Yes |
| Cutter & Buck | None required for product sync (PromoStandards credentials for orders only) | Yes (PromoStandards) | Yes |
| Momentec Augusta | None required | No | Yes |
| Champro | None required | No | Yes |
| Sanmar Canada | Email, account ID & password | No | Yes |
| Decky | None required | No | Yes |
| Edwards | FTP username & password | No | Yes |
| AS Colour US | None required | No | Yes |
| ACC (Atlantic Coast Cotton) | FTP username & password | Yes (PromoStandards) | Yes |
| JDS Industries | API key | No | Yes |
| Scrub Authority | SFTP username & password | No | Yes |
| Custom Supplier | Optional username & password | No | No |

Order sync through SupplyMaster is available for S&S Activewear and via PromoStandards (ACC, SanMar, and Cutter & Buck).

---

## 2\. What Is Automatic Sync?

**Automatic sync** is the automatic import of products and variants from your supplier into your Shopify store. SupplyMaster runs syncs on a schedule (e.g., daily or every 6 hours) and applies your saved filters, update settings, and auto-sync settings. New products and variants that match your filters are created; existing products are updated according to your update behavior (e.g., all fields, variant fields only, or inventory only).

**To turn automatic sync on or off:** Open the supplier in SupplyMaster, go to the **Automatic Sync** tab, and set **Frequency of Automatic Sync** to **Never** to turn it off, or to **Daily** (or **Every 6 Hours** for SS Activewear) to turn it on.

---

## 3\. Sync & Update Settings

Most suppliers share the same sync options. You can control how often products update, what happens when items go unavailable, and how new products and variants are created.

Choose how often SupplyMaster automatically syncs product data:

- **Never** — Sync only when you run a manual sync
- **Daily** — Automatic sync once per day
- **Every 6 Hours** — Available for SS Activewear only

If a product becomes unavailable (e.g., removed from the supplier catalog or filtered out):

- **Archive Products** — Archive the product in Shopify
- **No Action** — Leave the product as-is (default)

For products that already exist in your store, you can choose what gets updated during syncs:

- **All Fields with Image Upload** — Full updates including images
- **All Fields Except Images** — Updates everything except product images
- **Only Variant Fields** — Updates SKU, price, inventory, weight
- **Only Inventory** — Updates inventory quantities only

Control whether SupplyMaster creates new products and variants based on your saved filters:

- **Always Create** — Create new products and variants (default)
- **No New Variants on Existing** — Add new products, but no new variants on existing products
- **No New Products** — Add variants to existing products only
- **No New Products or Variants** — Update existing items only

Shopify supports up to 2,048 variants per product. SupplyMaster uses this limit by default. If you have legacy products split by color or size from the older 100-variant limit, you can keep that behavior.

---

## 4\. Connection Details by Supplier

| **Supplier** | **Connection Details** |
| --- | --- |
| SS Activewear | Account number (as username), API key, and country (US, Canada, or Puerto Rico). Email [api@ssactivewear.com](mailto:api@ssactivewear.com) if you need an API key. |
| Sanmar | FTP username and password. Contact Sanmar for credentials. Your FTP password may differ from your web login. |
| Alphabroder | Username and password. Contact Alphabroder for credentials. |
| Cap America | Promo Standards username and password. Contact Cap America for credentials. |
| Otto Cap | Promo Standards username and password. Contact Otto Cap for credentials. |
| Goldstar | Promo Standards username and password. Contact Goldstar for credentials. |
| Charles River Apparel | Promo Standards username and password. Contact Charles River Apparel for credentials. |
| Cutter & Buck | No product-sync credentials required — the catalog is sourced from a built-in feed. Separate PromoStandards Username and Password are entered under Order Settings if dropshipping. Contact [CBEDI@cutterbuck.com](mailto:CBEDI@cutterbuck.com) for PromoStandards API access. |
| Momentec Augusta | No credentials required. |
| Champro | No credentials required. |
| Sanmar Canada | User email, account ID, and password. Contact Sanmar Canada to enable API access. |
| Decky | No credentials required. |
| Edwards | FTP username and password. |
| AS Colour US | No credentials required. |
| ACC (Atlantic Coast Cotton) | FTP username and password. |
| JDS Industries | API key only. |
| Scrub Authority | SFTP username and password. |
| Custom Supplier | Optional username, password, and additional info. Used for suppliers not yet integrated. Requires custom setup by support. No AI+ enrichment or predefined sync options. |

---

## 5\. Default Pricing by Supplier

SupplyMaster applies a default pricing formula per supplier. You can customize these in the field mapping settings.

| **Supplier** | **Default Formula** |
| --- | --- |
| SS Activewear | 1.2× sale price |
| Sanmar | MSRP |
| Alphabroder | 1.2× piece price |
| Cap America | 1.2× wholesale |
| Otto Cap | 1.2× wholesale |
| Goldstar | 1.2× variant price |
| Charles River Apparel | 1.2× variant price |
| Cutter & Buck | MSRP |
| Momentec Augusta | MSRP |
| Champro | MSRP or 1.5× base price |
| Sanmar Canada | 1.5× cost |
| Decky | MSRP |
| Edwards | MSRP |
| AS Colour US | 2× cost |
| ACC | 2.5× cost |
| JDS Industries | 1.5× cost |
| Scrub Authority | MSRP |

---

## 6\. AI+ Enrichment

All suppliers except Custom Supplier support AI+ mapping fields. AI+ is an add-on that generates enriched product data such as:

- Shopify product categories
- Base and sub-categories
- Clean titles and handles
- Bulleted and short descriptions
- SEO title and description
- Tags, material, and gender

You can use AI+ fields in filters and in field mappings to improve product organization and discoverability.

---

## 7\. Order Placement & Orders Tab

**Order placement** for suppliers that support it is configured under **Edit Supplier** > **Order Settings**. The **Orders** tab on a supplier page shows the App Orders queue when **Order Settings** > **Order Sync** is not **Disabled**.

Automatic order placement is available for **S&S Activewear** and for PromoStandards suppliers **ACC**, **SanMar**, and **Cutter & Buck**. On those suppliers, **Order Settings** includes **Order Sync**, credentials, and shipping options.

For other built-in suppliers, **Order Settings** shows a setup request form: **Contact Email** plus optional username and password. Save the supplier to notify support; custom order sync is typically completed within about one week. See **Supported Suppliers & Features** for the full list and steps.

For PromoStandards catalog suppliers (for example Cap America), credentials on **Connection Settings** are for product data. Order API credentials for dropship can be submitted on **Order Settings** when requesting order sync if placement is not yet enabled in the app.

---

**Need help?** Contact support via chat in the bottom-right corner of the app.