---
title: "Syncing Orders with S&S Activewear"
source: "https://help.comstack.com/en/articles/13935083-syncing-orders-with-s-s-activewear"
author:
published: 2026-06-01
created: 2026-06-11
description: "SupplyMaster can forward eligible Shopify orders to S&S Activewear for dropshipping, or you can place orders manually if you customize be..."
tags:
  - "clippings"
---
SupplyMaster can forward eligible Shopify orders to S&S Activewear for dropshipping, or you can place orders manually if you customize before shipping.

This article explains both workflows, **Order Settings**, warehouse selection, payment, timing, and the **Orders** tab. **Note:** Automatic placement through SupplyMaster is available for S&S Activewear and for PromoStandards suppliers **ACC**, **SanMar**, and **Cutter & Buck** (see **Syncing Orders with PromoStandards**). For other suppliers, you can request order sync setup from **Edit Supplier** > **Order Settings**; see **Supported Suppliers & Features**. A single Shopify order can include products from multiple suppliers; SupplyMaster records which suppliers apply, and places orders with supported suppliers accordingly.

---

## Two Business-Model Workflows

If you customize products before shipping — for example screen printing, embroidery, or heat transfer — you usually consolidate inventory to your location, decorate, then ship to the customer. In this workflow:

- SupplyMaster syncs product and inventory data from S&S Activewear to your Shopify store.
- You place orders with S&S through their portal or your usual process; goods ship to you first.
- In SupplyMaster, open the supplier and go to **Edit Supplier** > **Order Settings**. Set **Order Sync** to **Disabled**.

If you sell without customization, you can have SupplyMaster place orders with S&S so they ship directly to your customer with blind shipping. Tracking is synced back into SupplyMaster.

1. Go to **Edit Supplier** > **Order Settings**. Set **Order Sync** to **Automatically Fulfill Orders**, **Fulfill Orders at Scheduled Time** (if scheduled, choose **Order Placement Time** in your local timezone), or **Manually Fulfill Orders** if you want orders captured in **App Orders** but placed only when you click **Submit Now**. The **Orders** tab on the supplier page appears when order sync is not **Disabled**.
2. Choose **Warehouse Selection** (see table below).
3. Choose **Shipping Method** for how S&S ships dropship orders (default: Cheapest, where S&S chooses the lowest cost service based on their internal routing).
4. Set **Order Payment Settings (Profile Email Address)**: billing profile email for card payment, or type `Credit` if you have a credit arrangement with S&S.
5. In **Inventory Settings**, map Shopify locations to supplier warehouses and choose a dropshipping-compatible location so catalog and policies align.
6. Click **Save Supplier**.

[![Order Settings tab showing Order Sync, Warehouse Selection, and Order Payment Settings for S&amp;S Activewear](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551479/c33b3a9a122a97d9fc6efa8f5765/order-sync-settings.png?expires=1781227800&signature=a581a912cdf2c7829f1fa1588a4116dda8d2d71b4a9064c229561810aa4dc79b&req=diQjH8x7nIVYUPMW1HO4zdG1G8OspcejOA6vQyYNy3WG3nwPQbsMdydIV3GF%0AZL7f73nPgbNgVqIp5PE%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551479/c33b3a9a122a97d9fc6efa8f5765/order-sync-settings.png?expires=1781227800&signature=a581a912cdf2c7829f1fa1588a4116dda8d2d71b4a9064c229561810aa4dc79b&req=diQjH8x7nIVYUPMW1HO4zdG1G8OspcejOA6vQyYNy3WG3nwPQbsMdydIV3GF%0AZL7f73nPgbNgVqIp5PE%3D%0A)

---

## Order Settings Explained

Order placement is configured on the **Order Settings** tab, not under **Automatic Sync** (that tab controls product import frequency and update behavior only).

| **Setting** | **What It Does** |
| --- | --- |
| **Order Sync** — Automatically Fulfill Orders | Eligible orders are placed with S&S every 30 minutes |
| **Order Sync** — Fulfill Orders at Scheduled Time | Orders are placed once per day after your chosen time (local timezone), on the next processing run after that time. |
| **Order Sync** — Manually Fulfill Orders | Eligible orders appear in App Orders as **Pending**; they are not auto-placed on the ~30-minute schedule. Use **Submit Now** when ready (and **Hold Order** / **Release Hold** as needed). |
| **Order Sync** — Disabled | No automatic placement; manage orders outside SupplyMaster. |
| **Warehouse Selection** | **Auto Select Warehouses:** warehouses are chosen for you. **From Fulfillment Locations:** uses the Shopify fulfillment location on the order (configure mappings in **Inventory Settings**). **From Line Item Properties:** reads a `warehouse` property on each line item (warehouse abbreviation or mapped location ID). |
| **Shipping Method** | Service level sent to S&S on each placed order (UPS, FedEx, ground, expedited, pickup, etc.). Default is **Cheapest** (S&S selects the most cost-effective ground option). Choose another option if your account or workflow requires a specific carrier or speed. |
| **Order Payment Settings** | Card: email on your S&S billing profile with a saved card. **Credit:** type `Credit` only if S&S has approved credit on your account. |

---

## Managing Orders in the App

On the supplier page, open the **Orders** tab (visible when **Order Settings** > **Order Sync** is not **Disabled**).

Shows orders captured from Shopify and their status toward placement with S&S. Status may be **Queued**, **Pending**, or **On Hold**. Use **Hold Order** or **Release Hold** as needed. **Submit Now** is available when the order is **Queued** or **Pending**; if it is **On Hold**, release it first, then use **Submit Now**. Failed orders cannot be retried from the app to avoid duplicate supplier orders; use **Details** to see the error and contact support if needed.

[![Orders tab App Orders showing a data table with Date, Shopify order number, status, and actions](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551494/e49bc8767bfe9d0b292680ec100c/order-list-table.png?expires=1781227800&signature=792568be27fdc883a18975f72ae4463d885abc8b2297657bfb3a775678724d67&req=diQjH8x7nIVWXfMW1HO4zVesX6eBaBCDavNlixSyhfNr9x%2BZEpnjeHfgToem%0AsEk7F%2FD3tVD3BM8CtOg%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551494/e49bc8767bfe9d0b292680ec100c/order-list-table.png?expires=1781227800&signature=792568be27fdc883a18975f72ae4463d885abc8b2297657bfb3a775678724d67&req=diQjH8x7nIVWXfMW1HO4zVesX6eBaBCDavNlixSyhfNr9x%2BZEpnjeHfgToem%0AsEk7F%2FD3tVD3BM8CtOg%3D%0A)

---

## Troubleshooting

Check **Order Payment Settings**: credit must be approved at S&S; card payments need the correct billing profile email and a saved card. Contact S&S if your account is not in good standing.

If an order is skipped because no products match this supplier, the Shopify line items were not imported from this S&S connection or are not mapped. This is expected for orders from other suppliers or manual products.

If placement fails with a location or warehouse error, confirm **Warehouse Selection** matches how you fulfill in Shopify, and that **Inventory Settings** maps Shopify locations to S&S warehouses where required.