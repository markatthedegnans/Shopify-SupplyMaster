---
title: "Setting Up Inventory by Warehouse Location"
source: "https://help.comstack.com/en/articles/13934826-setting-up-inventory-by-warehouse-location"
author:
published: 2026-03-09
created: 2026-06-11
description: "SupplyMaster can import inventory quantities from your supplier and assign them to specific Shopify locations."
tags:
  - "clippings"
---
SupplyMaster can import inventory quantities from your supplier and assign them to specific Shopify locations. This keeps your stock levels accurate and prevents overselling. Some suppliers provide warehouse-level inventory, letting you map individual warehouses to the Shopify locations where that stock should appear.

---

## How Inventory Location Mapping Works

When you connect a supplier, SupplyMaster detects whether the supplier provides warehouse-level inventory or a single aggregated inventory count. The **Inventory Settings** tab in **Edit Supplier** shows a mapping section where each of your Shopify locations is paired with a supplier inventory source.

- **Suppliers with warehouse data** — You'll see a dropdown listing each supplier warehouse by name. Select which supplier warehouse feeds inventory into each Shopify location.
- **Suppliers without warehouse data** — You'll see two options: **Import Supplier Inventory** (sends the supplier's total stock count to that Shopify location) or **Do Not Import Inventory** (leaves inventory for that location untouched).

Every time an import or sync runs, inventory numbers from the supplier are updated in the matched Shopify location automatically.

---

## Which Suppliers Support Warehouse-Level Inventory?

| **Supplier** | **Warehouse Inventory** | **Notes** |
| --- | --- | --- |
| S&S Activewear | Yes | Individual warehouse locations across the US, Canada, and Puerto Rico. Warehouse inventory filters available (see below). |
| AlphaBroder | Yes | Two inventory types: **All Inventory** (combined warehouse stock) and **Dropshipping Inventory Only** (only stock available for dropship orders). |
| SanMar | Yes | Warehouse locations provided per variant. Warehouse inventory filter available for quantity. |
| All other suppliers | No | A single aggregated inventory count is provided. Use **Import Supplier Inventory** to assign it to a Shopify location. |

---

## Setting Up Your Inventory Mapping

1. Go to **Edit Supplier** > **Inventory Settings**.
2. For each Shopify location listed, select the corresponding supplier inventory source from the dropdown:
	- Choose a specific supplier warehouse name if available.
	- Choose **Import Supplier Inventory** if the supplier provides a single total count.
	- Choose **Do Not Import Inventory** if you don't want SupplyMaster to manage inventory for that Shopify location.
3. Click **Save Supplier**.

If you have multiple Shopify locations and a supplier with warehouse data, you can map different supplier warehouses to different Shopify locations. For example, you might map an S&S Activewear east-coast warehouse to your "East Coast" Shopify location and a west-coast warehouse to your "West Coast" location.

[![The inventory location mapping cards showing Shopify locations paired with supplier warehouses](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322425/6722f15782d66a82687261b69f4a/location-mapping-table.png?expires=1781227800&signature=af31f99897b4c87a8ef969fc5bc0603d828e797c49bf8864cdfe1e25a73912fa&req=diEjFcp8n4VdXPMW1HO4zU%2FghiMOPme3nu3MncsRiUvSuq0DwZdmoRi1q%2FbN%0AFREgP%2B2%2B3TSAyv59GfU%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322425/6722f15782d66a82687261b69f4a/location-mapping-table.png?expires=1781227800&signature=af31f99897b4c87a8ef969fc5bc0603d828e797c49bf8864cdfe1e25a73912fa&req=diEjFcp8n4VdXPMW1HO4zU%2FghiMOPme3nu3MncsRiUvSuq0DwZdmoRi1q%2FbN%0AFREgP%2B2%2B3TSAyv59GfU%3D%0A)

---

## Inventory Adjustment Quantity

The **Inventory Adjustment Quantity** setting creates a safety buffer by reducing the displayed inventory in your store. This helps prevent overselling when the supplier's stock changes between syncs.

For example, if the supplier has 100 shirts in stock and you set an inventory adjustment quantity of 5, the Shopify inventory will show 95 shirts available.

1. In **Edit Supplier** > **Inventory Settings**, find the **Inventory Adjustment Quantity** field.
2. Enter a whole number (e.g., `5`, `10`).
3. Click **Save Supplier**.

The adjustment is applied every time inventory is synced. If you set it to 0 or leave it blank, inventory is imported as-is with no buffer.

[![The Inventory Adjustment Quantity field with a buffer value](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322451/1e7cb03bdad389bb83e0ee1ca2fd/inventory-adjustment-field.png?expires=1781227800&signature=b1c9be59bb17a3552fb8fae03ef8ece5a756df34b761a163fcec728210aa306f&req=diEjFcp8n4VaWPMW1HO4zeMKzOJUsKhiI5CMPHTFWplfbpI8hMK%2F7ityA3sA%0Az2J1SqKSMxPMXen1qGg%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322451/1e7cb03bdad389bb83e0ee1ca2fd/inventory-adjustment-field.png?expires=1781227800&signature=b1c9be59bb17a3552fb8fae03ef8ece5a756df34b761a163fcec728210aa306f&req=diEjFcp8n4VaWPMW1HO4zeMKzOJUsKhiI5CMPHTFWplfbpI8hMK%2F7ityA3sA%0Az2J1SqKSMxPMXen1qGg%3D%0A)

---

## Warehouse Inventory Filters

Some suppliers with warehouse-level inventory also support **warehouse inventory filters**. These let you filter which warehouse data is included when importing inventory.

| **Supplier** | **Available Warehouse Filters** |
| --- | --- |
| S&S Activewear | `closeout`, `dropship`, `excludeFreeFreight`, `fullCaseOnly`, `returnable`, `qty` |
| AlphaBroder | `totalInventory`, `dropshipInventory` |
| SanMar | `qty` |

For example, with S&S Activewear you could filter by `dropship` to only include warehouses that support dropshipping, or filter by `qty` to exclude warehouses where stock falls below a threshold.

Warehouse inventory filters are set in the same filter section as product and variant filters. See our **How to Filter Products for Import** article for details on using filter conditions.

---

## Tips

- If you only sell from one Shopify location, map all supplier inventory to that single location.
- Use **Do Not Import Inventory** for any Shopify location where you manage stock manually or through a different supplier.
- Combine the inventory adjustment quantity with frequent syncing (daily or every 6 hours where available) for the most accurate stock levels.
- If you switch suppliers or change warehouse mappings, run a manual sync afterward to update all inventory counts immediately.