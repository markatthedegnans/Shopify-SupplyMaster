---
title: "Importing Products to Your Shopify Store"
source: "https://help.comstack.com/en/articles/13933771-importing-products-to-your-shopify-store"
author:
published: 2026-03-09
created: 2026-06-11
description: "Once your supplier is connected and your filters are configured, you're ready to import products."
tags:
  - "clippings"
---
Once your supplier is connected and your filters are configured, you're ready to import products. This article explains what happens when you start an import, how long it takes, how to monitor progress, and how to cancel if needed.

---

## Before You Import

Make sure these are set up before clicking Import:

- **Product filters** — define which products and variants will be imported. Without filters, every product in the supplier's catalog will be brought into your store, which may be thousands of items. See our **How to Filter Products for Import** article.
- **Publish channels** — choose which Shopify sales channels (Online Store, Point of Sale, etc.) imported products should be published to. Configure this under **Edit Supplier** > **Product Settings** > **Product Sales Channels**. Products will automatically be published on all selected channels after import.
- **Field mapping** — review how supplier data maps to Shopify product fields (title, description, price, SKU, etc.). The default mapping works for most use cases, but you can customize it under **Edit Supplier** > **Product Settings** > **Match Fields**.

[![The publish channels selector in Product Settings showing available Shopify sales channels](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321313/425b3c53c03e268abfacda68fed2/publish-channel-selector.png?expires=1781227800&signature=6bf03260a358d25edd33934cdc048415c8b25a87518476c442c83efa8419b685&req=diEjFcp8nIJeWvMW1HO4zQCd%2BavIYo0WXeM6VQWCaIwOqyClz1WRaHMsO1y0%0AHqxfzTSswu3RNSoACuY%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321313/425b3c53c03e268abfacda68fed2/publish-channel-selector.png?expires=1781227800&signature=6bf03260a358d25edd33934cdc048415c8b25a87518476c442c83efa8419b685&req=diEjFcp8nIJeWvMW1HO4zQCd%2BavIYo0WXeM6VQWCaIwOqyClz1WRaHMsO1y0%0AHqxfzTSswu3RNSoACuY%3D%0A)

---

## Starting an Import

1. From the **Manage Suppliers** page, click the supplier name or click **View** in the Actions column.
2. On the **Products for Import** tab, verify the product list matches what you expect. The right side shows a preview of products matching your current filters.
3. Click **Import Products**.

The import is added to a sync queue and begins processing. A status bar appears at the top of the page showing the progress.

[![The Products for Import header with the Import Products and Edit Filters buttons](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321334/f717ed633600efbf6a8a7197c796/import-products-button.png?expires=1781227800&signature=f91ac4a5bbe07bdb472a6ab6d1205c8391fad4fbbe98a5bc99b5dd0ce1008e2d&req=diEjFcp8nIJcXfMW1HO4zQdmeZOd9shA5WMU1rIGxdSvpwoSHLvA0kqo4lnZ%0AX1p9k7M%2BPceDPye2qic%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143321334/f717ed633600efbf6a8a7197c796/import-products-button.png?expires=1781227800&signature=f91ac4a5bbe07bdb472a6ab6d1205c8391fad4fbbe98a5bc99b5dd0ce1008e2d&req=diEjFcp8nIJcXfMW1HO4zQdmeZOd9shA5WMU1rIGxdSvpwoSHLvA0kqo4lnZ%0AX1p9k7M%2BPceDPye2qic%3D%0A)

---

## What Happens During Import

When the import runs, SupplyMaster:

1. Fetches the latest product data from the supplier.
2. Applies your product and variant filters to determine which items to include.
3. Creates new Shopify products for items that don't exist yet, or updates existing products that were previously imported.
4. Populates product fields (title, description, price, images, SKU, weight, etc.) based on your field mapping configuration.
5. Sets inventory levels at your configured Shopify locations.
6. Publishes products to the sales channels you selected.

**Important:** Data is imported based on the settings in the **Edit Supplier** tab. If you haven't configured field mapping or inventory settings, the defaults are used.

---

## How Long Does It Take?

An import can take **10 minutes to 1 hour** depending on how many products are being imported. A small catalog of a few hundred products will finish quickly, while importing thousands of products with images will take longer.

**Tip:** For your first import, start with a filter for just a few products or a single brand. Verify the results in your Shopify admin, then expand your filters to import more.

---

## Monitoring Progress

While the import is running:

- A **status bar** appears at the top of the Products for Import tab showing the current state (e.g., "Importing Products...").
- The filter panel is disabled during import to prevent changes to filter settings while a sync is in progress.
- For more detail, check the **Sync History** page in the left sidebar. It shows the status, row count, and any errors for each sync. See our **Sync History, Errors & Troubleshooting** article.

---

## Canceling an Import

If an import was started by mistake or you notice your filters aren't configured correctly:

1. Click **Cancel Import** on the Products for Import tab. This button replaces the Import Products button while a sync is running.
2. The import will stop, but **products that were already created remain in your Shopify store**. They are not automatically removed.
3. After canceling, adjust your filters before starting a new import.

If you need to remove products that were imported before the cancel, delete them manually from your Shopify admin or set up filters to exclude them and use the **Archive Products** setting in the Automatic Sync tab.

---

## After Import

Once the import completes:

- Check your Shopify admin to see the new products. Verify that titles, prices, images, and variants look correct.
- If images are missing on some products, you can delete those products and re-import (they will be recreated with all data including images).
- Consider enabling **Auto Import** on the supplier card or configuring **Automatic Sync** settings to keep inventory and pricing up to date going forward.

---

## Troubleshooting

| **Issue** | **What to Do** |
| --- | --- |
| Import seems stuck or shows "data processing" for a long time | Check the **Sync History** page for status updates. Large imports can take up to an hour. If it's been longer, contact support. |
| Products imported without images | Delete the affected products from Shopify and re-import. They will be recreated with complete data including images. |
| Too many products imported | Cancel the import if still running, then refine your filters to be more specific before starting again. |
| Products appeared without setting up filters | Products may import based on default settings. Go to **Edit Filters** to add product and variant filters to control what gets imported. |