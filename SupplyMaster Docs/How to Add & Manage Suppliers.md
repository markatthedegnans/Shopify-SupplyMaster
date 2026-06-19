---
title: "How to Add & Manage Suppliers"
source: "https://help.comstack.com/en/articles/13933606-how-to-add-manage-suppliers"
author:
published: 2026-03-09
created: 2026-06-11
description: "SupplyMaster lets you connect to wholesale suppliers, import their product catalogs, and keep everything synced automatically."
tags:
  - "clippings"
---
SupplyMaster lets you connect to wholesale suppliers, import their product catalogs, and keep everything synced automatically. This article covers how to add a new supplier, edit settings, duplicate or delete a supplier, and use the Auto Import toggle.

---

## Adding a New Supplier

1. From the **Manage Suppliers** page, click the **Add Supplier** button in the top-right corner.
2. Select your supplier type from the dropdown (e.g., S&S Activewear, SanMar, AlphaBroder).
3. Enter a **Supplier Name** — this is your internal label, so use something memorable like "S&S Activewear - US" or "SanMar Blanks."
4. Fill in the required connection credentials for that supplier. For help finding your credentials, see our **How to Get Your Supplier Credentials** article.
5. Click **Test Credentials** to verify the connection. You'll see a green success message if everything is correct.
6. Click **Save Supplier**.

Once saved, additional configuration tabs appear: **Inventory Settings**, **Product Settings** (including field mapping), **Automatic Sync**, and **Advanced Settings** — as shown in the [Editing a Supplier](#editing-a-supplier) screenshot below. You can configure these now or come back later.

If your supplier isn't in the dropdown, click the **Create Custom Supplier** button below the supplier selection. Custom suppliers are handled by our support team — see our **Setting Up a Custom Supplier** article for details.

---

## The Supplier List

[![The Manage Suppliers page showing the supplier list table with columns for name, type, auto import, last sync, date created, and actions](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143380973/a7a1c3903c8c7db856be49c05d14/supplier-list-table.png?expires=1781227800&signature=68d6332f66a6b3ec9d88e88644a184456908ba08002de8accbbe704241ae346a&req=diEjFcp2nYhYWvMW1HO4zU8aJjBKeDFS9nT5jDud0s6cKH3QLCuqkwjIlbj9%0A4v6OP1LhemvhJSoEZ4o%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143380973/a7a1c3903c8c7db856be49c05d14/supplier-list-table.png?expires=1781227800&signature=68d6332f66a6b3ec9d88e88644a184456908ba08002de8accbbe704241ae346a&req=diEjFcp2nYhYWvMW1HO4zU8aJjBKeDFS9nT5jDud0s6cKH3QLCuqkwjIlbj9%0A4v6OP1LhemvhJSoEZ4o%3D%0A)

The **Manage Suppliers** page shows all your connected suppliers in a sortable table with these columns:

| **Column** | **Description** |
| --- | --- |
| Supplier Name | Click to view that supplier's product list (not available for custom suppliers) |
| Type | The supplier integration type (e.g., S&S Activewear, SanMar) |
| Auto Import | Toggle switch for daily automatic syncing |
| Last Sync | Date and time of the most recent successful sync |
| Date Created | When the supplier was first added |
| Actions | View, Edit, and More (Duplicate, Manage Orders, Delete) |

---

## Editing a Supplier

[![The Edit Supplier page showing Connection Settings, Inventory Settings, Product Settings, Automatic Sync, and Advanced Settings tabs](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143381000/75596ae1af61f3ab5f1f503798d8/edit-supplier-tabs.png?expires=1781227800&signature=564464417d1d362506f2e1d3a8dba28cc92f2eff6580d12bf1bf123f4086b3bf&req=diEjFcp2nIFfWfMW1HO4zbsXduOQwNNv2UksCq0gQf3OL86m%2BP4R5%2BOXwNGw%0A84hvvZ5J1qiCFlvEEuQ%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143381000/75596ae1af61f3ab5f1f503798d8/edit-supplier-tabs.png?expires=1781227800&signature=564464417d1d362506f2e1d3a8dba28cc92f2eff6580d12bf1bf123f4086b3bf&req=diEjFcp2nIFfWfMW1HO4zbsXduOQwNNv2UksCq0gQf3OL86m%2BP4R5%2BOXwNGw%0A84hvvZ5J1qiCFlvEEuQ%3D%0A)

To edit an existing supplier's settings:

1. Click the **Edit** button in the Actions column for the supplier you want to change.
2. Navigate between tabs: **Connection Settings**, **Inventory Settings**, **Product Settings**, **Automatic Sync**, and **Advanced Settings**.
3. Make your changes and click **Save Supplier**. Click **Discard Changes** to undo unsaved edits.

---

## Duplicating a Supplier

Duplicating creates a copy of an existing supplier with all its settings, field mappings, and product filters. This is useful when you want a second configuration for the same supplier — for example, one for a curated storefront and another for your full catalog.

1. Click **More** in the Actions column for the supplier you want to copy.
2. Select **Duplicate Supplier**.
3. Enter a name for the new supplier (defaults to " *Original Name* (Copy)").
4. Click **Create Duplicate**.

The new supplier is created with the same connection settings, field mappings, and product filters. You can edit any of these after creation. Duplicate is not available for custom suppliers.

---

## Deleting a Supplier

1. Click **More** in the Actions column, then select **Delete Supplier**.
2. Confirm in the dialog by clicking **Yes, Delete**.

**Important:** Deleting a supplier permanently removes all product links created through that supplier and cannot be recovered. However, products that were already imported to your Shopify store remain in your store — they are not deleted from Shopify. They will simply no longer be linked to SupplyMaster or receive sync updates.

---

## Auto Import Toggle

**Auto Import** and **Automatic Sync** are the same feature — they both control whether your supplier catalog syncs automatically. The toggle in the supplier list is a quick way to turn daily syncing on or off without opening the supplier's settings.

- **Enabled** (green) — the supplier will sync automatically once per day.
- **Disabled** (gray) — no automatic syncing. You can still run manual imports.

Toggling Auto Import on sets the sync frequency to **Daily**. Toggling it off sets the frequency to **None**. For more granular scheduling options (such as every 6 hours for S&S Activewear), open the supplier's **Automatic Sync** tab.

The Auto Import toggle is not available for custom suppliers.

---

## Email Support for Setup

If you prefer a hands-off start, SupplyMaster includes a built-in option to have the support team do the entire setup for you.

1. On the **Manage Suppliers** page (when no suppliers have been added yet), look for the **Need help getting started?** card.
2. Select a supplier from the dropdown.
3. Click **Email Support for Setup** — this opens a pre-filled email with your store ID, the selected supplier, and placeholders for your credentials and product preferences.
4. Fill in the blanks and send. The support team will configure the supplier and import settings on your behalf.