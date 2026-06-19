---
title: "FAQ: Getting Started & Suppliers"
source: "https://help.comstack.com/en/articles/13935217-faq-getting-started-suppliers"
author:
published: 2026-05-27
created: 2026-06-11
description: "Common questions about SupplyMaster setup, supported suppliers, pricing, and general features."
tags:
  - "clippings"
---
## Suppliers & Features

SupplyMaster integrates with 17 built-in wholesale suppliers — including S&S Activewear, SanMar (US & Canada), AlphaBroder, Cap America, Otto Cap, Goldstar, Charles River Apparel, Cutter & Buck, Champro, Augusta Sportswear (Momentec), AS Colour, Edwards, JDS Industries, ACC, Decky, and Scrub Authority — plus a Custom Supplier option for file-based imports. For a full comparison, see our **Supported Suppliers & Features** article.

Not all features are available for every supplier. Here is a summary:

| **Feature** | **S&S** | **AlphaBroder** | **SanMar** | **Cap America** | **Otto Cap** | **Goldstar** | **Champro** | **Custom** |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| Variant Splitting | Yes | Yes | Yes | Yes | Yes | Yes | Yes | No |
| Warehouse Inventory | Yes | Yes | No | No | No | Yes | No | No |
| Order Sync | Yes | No | No | No | No | No | No | No |
| Field Mapping | Yes | Yes | Yes | Yes | Yes | Yes | Yes | Yes |

- **Variant Splitting** — a legacy feature that splits products by color or size. Originally needed for the old 100-variant limit; not required for new setups since Shopify now supports 2,048 variants per product.
- **Warehouse Inventory** — imports inventory quantities for specific supplier warehouses/locations.
- **Order Sync** — automatically sends eligible Shopify orders to the supplier. Available for S&S Activewear and for PromoStandards suppliers ACC, SanMar, and Cutter & Buck.
- **Field Mapping** — maps supplier data fields to Shopify product fields during import.

SupplyMaster imports supplier data into Shopify using standard product data formats. This ensures compatibility with most Shopify-compatible design tools. You’ll need to choose a design tool from the Shopify App Store that suits your needs.

All Shopify themes work with SupplyMaster. The app does not modify your theme — it only writes product and inventory data to your Shopify admin. If you want to display specific data (e.g., stock levels or metafield values) on your storefront, you may need to customize your theme or use a theme app.

---

## Pricing & Plans

Pricing in SupplyMaster is set per SKU using a formula based on supplier pricing (e.g., piece price or case price). For volume-based pricing tiers at the cart level, you’ll need a separate volume discount app.

Yes. A variant is a unique SKU — one combination of size, color, and other options. A product with 5 sizes and 4 colors has 20 variants. Your subscription tier is based on how many variants are created and managed in your store.

Uninstall the SupplyMaster app from your Shopify store. Once uninstalled, your subscription is automatically canceled and you will not be billed again. If you still see charges after uninstalling, contact support.

This error means your store does not have an active paid Shopify plan. SupplyMaster requires a paid Shopify subscription — development and trial stores are not supported. Activate a paid Shopify plan and try again. For more information, see the [Shopify Community article](https://community.shopify.com/c/payments-shipping-and/why-can-t-my-store-accept-the-provided-charge/m-p/1394873).

---

## B2B & Business Model

Both. SupplyMaster supports wholesale, B2C, and hybrid business models. Many customers are wholesalers or decorators using Shopify to manage large-scale inventory alongside direct-to-consumer sales.

---

## Auto Import & Syncing

Auto Import keeps your product inventory and pricing automatically updated on a recurring schedule (daily or every 6 hours, depending on the supplier). Before enabling it:

1. **Set up filters** — go to **View Products** → **Edit Filters** to control which products are imported.
2. **Configure Auto Create settings** — decide whether new products and variants should be created automatically (see next question).
3. **Set Update Settings** — choose which fields should be updated on subsequent syncs.

**Warning:** Enabling Auto Import without proper filters can import your supplier’s entire catalog. Always configure filters first.

The **Auto Create Products & Variants** setting (under **Edit Supplier** → **Automatic Sync**) controls what gets created during both automatic and manual imports:

- **Always Create Products & Variants** (default) — full automation. Best for resellers.
- **No New Variants on Existing Products** — new products can be created, but existing products keep their current variants. Best for decorators who customize specific sizes/colors.
- **No New Products** — new variants (sizes, colors) are added to existing products, but new product lines are not created. Best for curated catalogs.
- **No New Products or Variants** — only pricing, inventory, and data updates. Best for finalized catalogs.

---

## Orders & Shipping

Your workflow depends on whether you customize before shipping. **Custom or decorated products:** SupplyMaster syncs catalog and inventory from the supplier; you usually place purchase orders yourself (for example to your location first), so set **Order Sync** to **Disabled** under **Edit Supplier** > **Order Settings**. **Dropshipping:** SupplyMaster can place eligible orders with **S&S Activewear** and with PromoStandards suppliers **ACC**, **SanMar**, and **Cutter & Buck**, and sync tracking back to Shopify. For setup, see [Syncing Orders with S&S Activewear](https://help.comstack.com/en/articles/13935083-syncing-orders-with-ss-activewear) and [Syncing Orders with PromoStandards (ACC, SanMar, Cutter & Buck)](https://help.comstack.com/en/articles/14360151-syncing-orders-with-promostandards).

Shipping rates are not managed by SupplyMaster. Set up your shipping rates directly in your Shopify admin or through a shipping app. For instructions, see the [Shopify Shipping Rates Guide](https://help.shopify.com/en/manual/fulfillment/setup/shipping-rates/flat-shipping-rates).

---

## Connection & Setup

1. **Verify credentials** — double-check that the username and API key are accurate.
2. **Contact your supplier** — if credentials appear correct, ask the supplier to verify your account access.
3. **S&S Activewear users** — find your Account Number and API Key at [ssactivewear.com/myaccount](https://www.ssactivewear.com/myaccount/).
4. **SanMar users** — contact SanMar to obtain FTP credentials if needed.

If problems persist, contact support for assistance.

Yes. Go to **Edit Supplier** → **Product Settings** and select the sales channels where imported products should be published (e.g., Online Store, POS, Buy Button). Products will be automatically published to all selected channels after import.

No. SupplyMaster does not interact with your storefront or cart. This is Shopify’s default add-to-cart limit of 50 items. You can adjust it in your Shopify admin under **Settings** → **Checkout**. See the [Shopify checkout settings guide](https://help.shopify.com/en/manual/checkout-settings/add-to-cart-limit).

---

## Uninstalling & Support

Products that were already imported to your Shopify store remain in your store — they are not deleted. SupplyMaster’s internal data (supplier configurations, filter settings, sync history) is cleaned up. Your subscription is automatically canceled. If you reinstall later, you will need to reconfigure your suppliers.

Click the chat icon in the bottom-right corner of the app to reach our support team directly. We typically respond within a few hours during business days.