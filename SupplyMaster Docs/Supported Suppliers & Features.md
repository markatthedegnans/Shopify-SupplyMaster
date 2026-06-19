---
title: "Supported Suppliers & Features"
source: "https://help.comstack.com/en/articles/13933480-supported-suppliers-features"
author:
published: 2026-06-01
created: 2026-06-11
description: "SupplyMaster includes built-in integrations for 17 wholesale suppliers plus a Custom Supplier option."
tags:
  - "clippings"
---
SupplyMaster includes built-in integrations for 17 wholesale suppliers plus a Custom Supplier option. Each supplier supports product import, field mapping, and automatic syncing, but some offer additional capabilities like warehouse-level inventory, order sync, or AI+ enriched data.

Use the table below to see what’s available for each supplier at a glance.

---

## Feature Matrix

| **Supplier** | **Credentials Required** | **Order Sync** | **Warehouse Inventory** | **Variant Splitting** | **AI+** |
| --- | --- | --- | --- | --- | --- |
| S&S Activewear | Yes (Username, API Key) | Yes | Yes | Yes | Yes |
| SanMar (US) | Yes (FTP Username, Password) | Yes | Yes | Yes | Yes |
| AlphaBroder | Yes (Username, Password) | — | Yes | Yes | Yes |
| Cap America | Yes (Username, Password) | Setup request | Yes | Yes | Yes |
| Otto Cap | Yes (Username, Password) | Setup request | Yes | Yes | Yes |
| Goldstar | Yes (Username, Password) | Setup request | Yes | Yes | Yes |
| Charles River Apparel | Yes (Username, Password) | Setup request | Yes | Yes | Yes |
| Cutter & Buck | No (orders only) | Yes | — | Yes | Yes |
| Augusta Sportswear (Momentec) | No | Setup request | — | Yes | Yes |
| AS Colour (US) | No | Setup request | — | Yes | Yes |
| Champro | No | Setup request | — | Yes | Yes |
| Decky | No | Setup request | — | Yes | Yes |
| Edwards | Yes (FTP Username, Password) | Setup request | — | Yes | Yes |
| JDS Industries | Yes (API Key) | Setup request | — | Yes | Yes |
| Atlantic Coast Cotton (ACC) | Yes (SFTP Username, Password) | Yes | — | Yes | Yes |
| SanMar Canada | Yes (Email, Account ID, Password) | Setup request | — | Yes | Yes |
| Scrub Authority | Yes (SFTP Username, Password) | Setup request | — | Yes | Yes |
| Custom Supplier | Optional | — | — | — | — |

---

## Feature Descriptions

Some suppliers require API keys, FTP logins, or account credentials to connect. Suppliers marked "No" can be added immediately without any credentials. For step-by-step instructions on where to find or request credentials for each supplier, see our **How to Get Your Supplier Credentials** article.

In the feature matrix, **Yes** means you can configure and run order placement in the app. **Setup request** means you can ask our team to enable order sync for that supplier; product import works without it.

Order sync automatically forwards Shopify orders to the supplier for fulfillment and receives tracking numbers back. In-app order sync is available for **S&S Activewear**, **SanMar**, **Atlantic Coast Cotton (ACC)**, and **Cutter & Buck**. Configure it under **Edit Supplier** > **Order Settings**. See our **Syncing Orders with S&S Activewear** and **Syncing Orders with PromoStandards** articles for full setup steps.

One Shopify order can include line items from more than one supplier; SupplyMaster captures that in one place, but supplier-side automatic placement runs only for suppliers marked **Yes** in the matrix.

For suppliers marked **Setup request** in the matrix, you can submit details so our support team can enable order sync on your account:

1. Open **Edit Supplier** > **Order Settings**.
2. Review the **Order Sync Settings** introduction at the top of the tab.
3. Enter a **Contact Email**. Optionally add **Username** and **Password** (labeled **PromoStandards Username** and **PromoStandards Password** for PromoStandards catalog suppliers such as Cap America and Otto Cap).
4. Click **Save Supplier**. SupplyMaster notifies support when the contact email changes.
5. Support completes custom order sync setup within about one week. For questions, email [support@comstack.com](mailto:support@comstack.com).

Until setup is complete, the **Orders** tab and automatic order placement are not available for that supplier. Product import, filters, and automatic product sync are not affected.

Suppliers with warehouse inventory provide stock levels broken down by individual warehouse locations. You can map each supplier warehouse to a Shopify location so inventory is tracked per-location — useful for merchants with multiple fulfillment centers or those who want to see regional stock levels.

Suppliers without this feature provide a single total inventory count per variant.

Variant splitting is a legacy feature from when Shopify limited products to 100 variants. Shopify now supports 2,048 variants per product for all stores, so new setups do not need splitting. This feature remains available to support stores that originally imported products under the old 100-variant limit and already have split products in their store.

AI+ is an optional one-time add-on ($99 per supplier type) that generates SEO-optimized titles, descriptions, product categories, tags, and other enriched fields. AI+ is available for all suppliers except Custom Supplier.

---

## Custom Supplier

The Custom Supplier option lets you import products from any supplier not in the built-in list via file upload. Key differences from built-in suppliers:

- **No automatic product fetching** — products are imported from files you upload, not pulled from a supplier API.
- **No Browse Catalog** — since there is no live connection to the supplier, the catalog browsing feature is not available.
- **No auto-sync** — to update product data, upload a new file. Automatic scheduled syncing is not supported.
- **No AI+** — AI-enriched fields are not available for custom suppliers.
- **No variant splitting** — products are imported as-is from the uploaded file.

Custom Supplier is ideal for one-time imports or suppliers that provide data via spreadsheets or CSVs. Contact support if you need help setting up a custom supplier integration.