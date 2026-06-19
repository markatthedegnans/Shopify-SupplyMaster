---
title: "How to Filter Products for Import"
source: "https://help.comstack.com/en/articles/13933680-how-to-filter-products-for-import"
author:
published: 2026-03-09
created: 2026-06-11
description: "Filters control which products from the supplier's catalog get imported into your Shopify store."
tags:
  - "clippings"
---
Filters control which products from the supplier's catalog get imported into your Shopify store. Without filters, thousands of unwanted products may be imported. Use filters to focus on specific brands, styles, sizes, or colors — and keep your store catalog lean and relevant.

---

## Types of Filters

SupplyMaster supports three levels of filtering. Each level narrows the data further before import.

| **Filter Level** | **What It Controls** | **Example** |
| --- | --- | --- |
| Product Filters | Which products are included (by brand, title, style number, category, etc.) | Brand Name — Equal To Any — Gildan, Bella+Canvas |
| Variant Filters | Which sizes, colors, or other variant attributes are included for each product | Size — Not Equal To Any — 3XL, 4XL, 5XL |
| Warehouse Filters | Which warehouse locations are included (for suppliers with warehouse-level inventory) | Warehouse — Equal To Any — Jacksonville, Toronto |

The available filter fields depend on your supplier type. For example, S&S Activewear provides fields like Brand Name, Style Number, and Color Name, while other suppliers may use different field names.

---

## Adding & Editing Filters

[![The Edit Product Import Filters panel showing filter cards, Save Filters button, Add Product Filter, and More Actions menu](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320670/e2baf0a5fe7cecf49e3048890558/filter-panel-overview.png?expires=1781227800&signature=f84650d9dc85edd0e8aff637da1c4b0f16b24d8d0f5282968c0be87a1e3553a0&req=diEjFcp8nYdYWfMW1HO4zTEQzgpBdRf5s1MmRXR533cNfcBn%2F3DrTqeR9alU%0AisS%2Bnp3uivST8PLEycQ%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320670/e2baf0a5fe7cecf49e3048890558/filter-panel-overview.png?expires=1781227800&signature=f84650d9dc85edd0e8aff637da1c4b0f16b24d8d0f5282968c0be87a1e3553a0&req=diEjFcp8nYdYWfMW1HO4zTEQzgpBdRf5s1MmRXR533cNfcBn%2F3DrTqeR9alU%0AisS%2Bnp3uivST8PLEycQ%3D%0A)

1. Go to the **Manage Suppliers** page and click the supplier name, or click **View** in the Actions column.
2. On the **Products for Import** tab, click **Edit Filters** to open the filter panel.
3. Click **Add Product Filter** to add a product-level filter. To add variant or warehouse filters, click **More Actions** and select the filter type.
4. For each filter row:
	- **Field** — select the supplier data field to filter on (e.g., Brand Name, Style Number, Color Name).
	- **Condition** — choose a filter condition (see the full list below).
	- **Value** — enter the value(s) to match. For conditions ending in "Any," enter multiple values separated by commas.
5. Click **Save Filters** when finished. The product list on the right updates to show matching products.

To remove a single filter, click the delete icon next to it. To clear everything, click **More Actions** > **Delete All Filters**.

---

## Filter Conditions

Every filter uses one of the following conditions:

| **Condition** | **Description** | **Example** |
| --- | --- | --- |
| Contains | Value contains the filter text | Title — Contains — Hoodie |
| Contains Any |  | Title — Contains Any — T-Shirt, Hoodie, Sweatshirt |
| Does Not Contain | Value does not contain the filter text | Color Name — Does Not Contain — Heather |
| Equal To | Value exactly matches the filter value | Brand Name — Equal To — Gildan |
| Equal To Any | Value exactly matches any of the comma-separated values | Brand Name — Equal To Any — Gildan, Bella+Canvas, Next Level |
| Not Equal To | Value does not match the filter value | Brand Name — Not Equal To — Discontinued Brand |
| Not Equal To Any | Value does not match any of the comma-separated values | Brand Name — Not Equal To Any — Brand A, Brand B |
| Exists | Field has a value (is not empty) | Style Number — Exists |
| Does Not Exist | Field is empty or missing | Color Image — Does Not Exist |
| Is Greater Than | Numeric value is greater than the filter value | Price — Is Greater Than — 10 |
| Is Less Than | Numeric value is less than the filter value | Price — Is Less Than — 100 |

---

## And / Or Logic

[![Two filter rows connected by an And/Or operator dropdown, showing how multiple conditions combine](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320691/9d10e9e9d932de44e767f516bd5e/filter-and-or-logic.png?expires=1781227800&signature=d8cadbaefa3f21b27bcb6a414c5bd792256fc5e446ae03dc5b562c2f929a3e3d&req=diEjFcp8nYdWWPMW1HO4zemCEG2ctsPVX0T2Bxf0KHIcpP%2B1OpS8Drb%2F70b6%0AeJOBaOepQuWJOe%2FeEQE%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320691/9d10e9e9d932de44e767f516bd5e/filter-and-or-logic.png?expires=1781227800&signature=d8cadbaefa3f21b27bcb6a414c5bd792256fc5e446ae03dc5b562c2f929a3e3d&req=diEjFcp8nYdWWPMW1HO4zemCEG2ctsPVX0T2Bxf0KHIcpP%2B1OpS8Drb%2F70b6%0AeJOBaOepQuWJOe%2FeEQE%3D%0A)

When you add multiple filters within the same filter group (e.g., two product filters), each filter row has an **And** or **Or** operator:

- **And** — a product must match *all* filters to be included.
- **Or** — a product is included if it matches *any* of the filters.

For example, to import only Gildan t-shirts: set the first filter to Brand Name — Equal To — Gildan, then add a second filter with **And**, set to Title — Contains — T-Shirt.

---

## Match Case

Each text filter has a **Match Case** checkbox. When enabled, the filter comparison is case-sensitive (e.g., "black" would not match "Black"). Leave it unchecked for case-insensitive matching, which is the default.

---

## Real-World Filter Examples

To import only certain brands, add a product filter:

- Brand Name — **Equal To Any** — Gildan, Bella+Canvas, Next Level

This is the most common way to build a focused catalog. Separate brand names with commas in a single filter rather than creating multiple individual filters.

To import everything except certain brands:

- Brand Name — **Not Equal To Any** — Brand A, Brand B, Brand C

To import a curated list of specific styles:

- Style Number — **Equal To Any** — 64000, 5000, PTS30, PTS20, 112P

Enter all style numbers separated by commas in a single filter. This is more efficient than adding separate filters for each style.

To skip extended sizes from your import, add a variant filter:

- Size — **Not Equal To Any** — 3XL, 4XL, 5XL

To import only your best-selling colors:

- Color — **Contains Any** — Black, White, Red, Navy, Gray

Product and variant filters work together. If you set a product filter for Brand Name — Equal To Any — Gildan, Bella+Canvas *and* a variant filter for Size — Not Equal To Any — 4XL, 5XL, only products from those brands will be imported, and only in sizes up to 3XL.

---

## Filter History

[![The Filter History modal showing a list of saved filter snapshots with timestamps, a preview of the selected snapshot's filters, and Restore/Cancel buttons](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320716/d82363d460ceb4565c7ac5fb1774/filter-history-modal.png?expires=1781227800&signature=3b4628ccf754c55304fb2f361bb3cbb77d3c92524f465732b2f9862f8a90e85a&req=diEjFcp8nYZeX%2FMW1HO4zT%2FIMhgHsT93bHsfAR5ex1yegAr3h1TuPEVIiLRH%0AGYUnEMof7hUreaswdtI%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320716/d82363d460ceb4565c7ac5fb1774/filter-history-modal.png?expires=1781227800&signature=3b4628ccf754c55304fb2f361bb3cbb77d3c92524f465732b2f9862f8a90e85a&req=diEjFcp8nYZeX%2FMW1HO4zT%2FIMhgHsT93bHsfAR5ex1yegAr3h1TuPEVIiLRH%0AGYUnEMof7hUreaswdtI%3D%0A)

Every time you save filters, SupplyMaster creates a snapshot of your filter configuration. If you make a mistake or want to go back to an earlier setup, you can restore a previous snapshot.

1. Open the filter panel by clicking **Edit Filters**.
2. Click **More Actions** > **Filter History**.
3. Browse the list of saved snapshots on the left. Each entry shows when it was saved (e.g., "2 hours ago") and a summary (e.g., "3 product filters, 1 variant filter").
4. Select a snapshot to preview its filters on the right.
5. Click **Restore** to apply it, or **Cancel** to go back without changes.

Up to 20 filter snapshots are stored per supplier. Older snapshots are automatically removed.

---

## AI Filter Generator

[![The Generate Filters with AI Assist modal showing the current filters, an AI prompt input field, and Generate/Apply buttons](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320773/05bc85708eee25d47e27afb383f0/ai-filter-generator-modal.png?expires=1781227800&signature=73940bc50469b810980533981d85939da9fe3fee458d31cbfaff51d6cb71801f&req=diEjFcp8nYZYWvMW1HO4zcABuPW5yMcfYeNICVsZDqoi0NsNsIQC%2BFIlooHb%0A2tYyIhN4KPxt4avVFOE%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143320773/05bc85708eee25d47e27afb383f0/ai-filter-generator-modal.png?expires=1781227800&signature=73940bc50469b810980533981d85939da9fe3fee458d31cbfaff51d6cb71801f&req=diEjFcp8nYZYWvMW1HO4zcABuPW5yMcfYeNICVsZDqoi0NsNsIQC%2BFIlooHb%0A2tYyIhN4KPxt4avVFOE%3D%0A)

If you're not sure which filter conditions to use, the **AI Filter Generator** can help. Click the AI icon in the filter panel and describe what you want in plain English (e.g., "import only Gildan and Bella+Canvas t-shirts in black and white"). The AI will suggest filter conditions that you can review and apply. See our **Using AI Tools for Filters & Formulas** article for more details.

---

## Important Tips

- **Start small.** Begin with a filter for just a few products or brands, run an import, and verify the results. Add more products to your filters as needed.
- **Filters must stay active.** Products must remain in your filter criteria to continue receiving sync updates (inventory, pricing, etc.). If you remove a product from filters, it stays in your Shopify store but will no longer be updated by SupplyMaster.
- **Deleted products can be re-imported.** If you delete a product from Shopify but it still matches your filters, SupplyMaster will re-create it on the next sync. To prevent this, adjust your filters to exclude the product before deleting it.
- **Hide zero-inventory products.** If you want products with zero stock to be hidden from your storefront, configure this in Shopify under **Settings** > **Online Store** > **Preferences**. See [Shopify's guide to hiding sold-out products](https://help.shopify.com/en/manual/online-store/themes/customizing-themes/product-pages#hide-sold-out-products).
- **Use Browse Catalog for discovery.** Not sure which products to filter for? Use the **Browse Catalog** tab to search and preview products before setting up filters. See our **Browsing & Searching the Supplier Catalog** article.