---
title: "Syncing Orders with PromoStandards (ACC, SanMar, Cutter & Buck)"
source: "https://help.comstack.com/en/articles/14360151-syncing-orders-with-promostandards-acc-sanmar-cutter-buck"
author:
published: 2026-06-01
created: 2026-06-11
description: "SupplyMaster can forward eligible Shopify orders to suppliers supporting PromoStandards — ACC, SanMar, and Cutter & Buck — for dropshippi..."
tags:
  - "clippings"
---
SupplyMaster can forward eligible Shopify orders to suppliers supporting PromoStandards — **ACC**, **SanMar**, and **Cutter & Buck** — for dropshipping, or you can place orders manually if you customize before shipping.

This article explains both workflows, the shared **Order Settings**, supplier-specific options (shipping carrier, service, and Blind Ship defaults), timing, and the **Orders** tab. **ACC**, **SanMar**, and **Cutter & Buck** use the full **Order Settings** fields described here. Other PromoStandards catalog suppliers (for example Cap America and Otto Cap) use a setup request form on the same tab until in-app order sync is enabled; see **Supported Suppliers & Features**.

---

## Two Business-Model Workflows

If you customize products before shipping — for example screen printing, embroidery, or heat transfer — you usually consolidate inventory to your location, decorate, then ship to the customer. In this workflow:

- SupplyMaster syncs product and inventory data from the supplier to your Shopify store.
- You place orders with the supplier through their portal or your usual process; goods ship to you first.
- In SupplyMaster, open the supplier and go to **Edit Supplier** > **Order Settings**. Set **Order Sync** to **Disabled**.

If you sell without customization, you can have SupplyMaster place orders with the supplier via PromoStandards so they ship directly to your customer with blind shipping. Tracking is synced back into SupplyMaster.

1. Go to **Edit Supplier** > **Order Settings**. Set **Order Sync** to **Automatically Fulfill Orders**, **Fulfill Orders at Scheduled Time** (if scheduled, choose **Order Placement Time** in your local timezone), or **Manually Fulfill Orders** if you want orders captured in **App Orders** but placed only when you click **Submit Now**. The **Orders** tab on the supplier page appears when order sync is not **Disabled**.
2. Set the **Dropship PO Number** if you wish to customize it.
3. Provide your **PromoStandards Username** and **PromoStandards Password**. Note that these are API credentials for PromoStandards and may be distinct from your FTP or catalog login (especially for ACC, SanMar, and Cutter & Buck, where the product feed and order API use different credentials).
4. Specify the **Shipping Carrier**, **Shipping Service**, and (for SanMar and Cutter & Buck) **Blind Ship**. The available carrier and service options vary per supplier — see the **Supplier-Specific Order Settings** section below.
5. Click **Save Supplier**.

[![Order Settings tab showing Order Sync, Dropship PO Number, and PromoStandards Credentials](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551534/6266b2896f2a73a57a7a46d638bd/promo-standards-order-settings.png?expires=1781228700&signature=dfd79b4a2dfd888789d5966d4bf1f2fad096108e9b162c145c82de89497541ef&req=diQjH8x7nIRcXfMW1HO4zeDYUOz4449zgtNaPt7c9SJTLDKf8qIYYklIIoSu%0AB66OkpqdfueklXLMdY0%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551534/6266b2896f2a73a57a7a46d638bd/promo-standards-order-settings.png?expires=1781228700&signature=dfd79b4a2dfd888789d5966d4bf1f2fad096108e9b162c145c82de89497541ef&req=diQjH8x7nIRcXfMW1HO4zeDYUOz4449zgtNaPt7c9SJTLDKf8qIYYklIIoSu%0AB66OkpqdfueklXLMdY0%3D%0A)

---

## Order Settings Explained

Order placement is configured on the **Order Settings** tab, not under **Automatic Sync** (that tab controls product import frequency and update behavior only).

| **Setting** | **What It Does** |
| --- | --- |
| **Order Sync** — Automatically Fulfill Orders | Eligible orders are placed with the supplier every 30 minutes |
| **Order Sync** — Fulfill Orders at Scheduled Time | Orders are placed once per day after your chosen time (local timezone), on the next processing run after that time. |
| **Order Sync** — Manually Fulfill Orders | Eligible orders appear in App Orders as **Pending**; they are not auto-placed on the ~30-minute schedule. Use **Submit Now** when ready (and **Hold Order** / **Release Hold** as needed). |
| **Order Sync** — Disabled | No automatic placement; manage orders outside SupplyMaster. |
| **Dropship PO Number** | The purchase order number sent to the supplier. You can customize this using Liquid (e.g., {{ shopifyOrderNumber }}-SHOPIFY). |
| **PromoStandards Username & Password** | API credentials for the supplier's PromoStandards order endpoint. This is distinct from FTP or catalog credentials. |
| **Shipping Carrier & Service** | Specifies the shipping method for dropshipped orders (e.g., UPS, UPS GROUND). The available options depend on the supplier — see **Supplier-Specific Order Settings** below. |
| **Blind Ship** (SanMar and Cutter & Buck only) | When set to **Yes**, orders ship under your branding rather than the supplier's. Default is **No** for SanMar and **Yes** for Cutter & Buck. |

---

## Supplier-Specific Order Settings

Each PromoStandards supplier has its own list of carriers and services, and its own default for Blind Ship. Use the table below to pick the right values for the supplier you are configuring.

- **PromoStandards credentials** — separate from your FTP product-feed credentials. Contact ACC for PromoStandards API access.
- **Shipping Carrier** — specify the carrier on each PO (e.g., UPS).
- **Shipping Service** — specify the service level (e.g., UPS GROUND).

- **PromoStandards credentials** — separate from your SanMar FTP product-feed credentials. Contact SanMar for PromoStandards API access.
- **Shipping Carrier** — UPS (default), USPS, or PSST.
- **Shipping Service** — service level for the selected carrier (default is **Ground**). The available services depend on the chosen carrier.
- **Blind Ship** — default **No**. Set to **Yes** to ship under your branding rather than SanMar's.

- **PromoStandards credentials** — required for orders. Cutter & Buck does not require product-sync credentials (the catalog is sourced from a built-in feed). Contact **[CBEDI@cutterbuck.com](mailto:CBEDI@cutterbuck.com)** for PromoStandards API access.
- **Shipping Carrier** — UPS (default), FedEx, FDX, FedEx SmartPost, Purolator, Share Ship, Routing Guide, or Other.
- **Shipping Service** — service code scoped to the selected carrier (default is **GRND PREPAID**). Changing the carrier resets the available service options.
- **Blind Ship** — default **Yes**. Set to **No** only if the customer wants Cutter & Buck branding on packages.

---

## Managing Orders in the App

On the supplier page, open the **Orders** tab (visible when **Order Settings** > **Order Sync** is not **Disabled**).

Shows orders captured from Shopify and their status. Status may be **Queued**, **Pending**, or **On Hold**. Use **Hold Order** or **Release Hold** as needed. **Submit Now** is available when the order is **Queued** or **Pending**; if it is **On Hold**, release it first, then use **Submit Now**. Failed orders cannot be retried from the app to avoid duplicate supplier orders; use **Details** to see the error and contact support if needed.

[![Orders tab App Orders showing a data table with Date, Shopify order number, status, and actions](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551538/7e5694249093a048c520bb5a6623/order-list-table.png?expires=1781228700&signature=b65351e710896e5765eb7d308f496ec9f7e0a7408e36e0af8b7e5c5aafac17cf&req=diQjH8x7nIRcUfMW1HO4zf1HO9zB4B4kjPE1on7I9Sw1x0elyXP3H8ZTIsY%2B%0AiM9jBO%2BifzP%2Ba%2FY%2FEvM%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551538/7e5694249093a048c520bb5a6623/order-list-table.png?expires=1781228700&signature=b65351e710896e5765eb7d308f496ec9f7e0a7408e36e0af8b7e5c5aafac17cf&req=diQjH8x7nIRcUfMW1HO4zf1HO9zB4B4kjPE1on7I9Sw1x0elyXP3H8ZTIsY%2B%0AiM9jBO%2BifzP%2Ba%2FY%2FEvM%3D%0A)

---

## Troubleshooting

Check your **PromoStandards Username** and **PromoStandards Password**. Ensure they are correct and that the supplier has granted your account API access for order placement.

If an order is skipped because no products match this supplier, the Shopify line items were not imported from this supplier connection or are not mapped. This is expected for orders from other suppliers or manual products.