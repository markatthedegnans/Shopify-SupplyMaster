---
title: "Getting Started with SupplyMaster"
source: "https://help.comstack.com/en/articles/13927961-getting-started-with-supplymaster"
author:
published: 2026-06-01
created: 2026-06-11
description: "SupplyMaster connects your Shopify store to supplier catalogs so you can import products, sync inventory and pricing, and keep your store..."
tags:
  - "clippings"
---
SupplyMaster connects your Shopify store to supplier catalogs so you can import products, sync inventory and pricing, and keep your store up to date automatically. This guide walks you through setup from start to finish.

---

## Before You Begin

- You need a Shopify store with the SupplyMaster app installed.
- You need credentials for at least one supported supplier. Some suppliers (Champro, Momentec Augusta, Decky, AS Colour US) don't require credentials at all. For others, you'll need an API key, FTP login, or PromoStandards username — see our **How to Get Your Supplier Credentials** article for step-by-step instructions on where to find or request them for each supplier.
- A subscription plan is required to start importing. SupplyMaster offers a **5-day free trial** on all plans.

For a visual walkthrough, watch the [SupplyMaster demo video](https://www.youtube.com/watch?v=45KtEhechD4).

---

## Step 1: Choose a Subscription Plan

When you first open the app, you'll see a welcome screen with four subscription plans. Select one to begin your free trial:

| **Plan** | **Price** | **Variants** | **Monthly Updates** |
| --- | --- | --- | --- |
| Basic | $29/mo | 5,000 | 200,000 |
| Pro | $99/mo | 50,000 | 2,000,000 |
| Plus | $279/mo | 200,000 | 8,000,000 |
| Premium | $499/mo | 400,000 | 16,000,000 |

[![Subscription plan selection screen showing available plans and pricing](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551288/d168b042e57dce970bfc96e829f3/subscription-plan-selection.png?expires=1781226900&signature=70897f87247957f905353eab7ff7711ad9bc4474fc4621eb3976d5eddfb485e2&req=diQjH8x7nINXUfMW1HO4zR1isIqEWKD6mYJw4%2BdvcTQ8h%2FQRHrc8LXRrptko%0Af5wLT4y7por0JvZfU%2Bw%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551288/d168b042e57dce970bfc96e829f3/subscription-plan-selection.png?expires=1781226900&signature=70897f87247957f905353eab7ff7711ad9bc4474fc4621eb3976d5eddfb485e2&req=diQjH8x7nINXUfMW1HO4zR1isIqEWKD6mYJw4%2BdvcTQ8h%2FQRHrc8LXRrptko%0Af5wLT4y7por0JvZfU%2Bw%3D%0A)

After selecting a plan, Shopify will ask you to approve the subscription. You won't be charged during the trial period.

---

## Step 2: Add Your First Supplier

Once your plan is active, you'll land on the **Manage Suppliers** page.

[![Manage Suppliers page with Add Supplier button](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551297/65722f1e8b2b47c17abcc4807d47/manage-suppliers-page.png?expires=1781226900&signature=ba2815ff4bbbd38faade9f131dec7919f5ce657da85ab8408790c10ba0ab4b9a&req=diQjH8x7nINWXvMW1HO4zdbaiV0aiCfvObRoR525XxhoAybqxsDtlPil0%2F0s%0AzAzuJvx9e7gYhOVM7AI%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551297/65722f1e8b2b47c17abcc4807d47/manage-suppliers-page.png?expires=1781226900&signature=ba2815ff4bbbd38faade9f131dec7919f5ce657da85ab8408790c10ba0ab4b9a&req=diQjH8x7nINWXvMW1HO4zdbaiV0aiCfvObRoR525XxhoAybqxsDtlPil0%2F0s%0AzAzuJvx9e7gYhOVM7AI%3D%0A)

1. Click the **Add Supplier** button.
2. Select your supplier from the dropdown (e.g., S&S Activewear, SanMar, AlphaBroder). If your supplier is not listed, click **Create Custom Supplier**.
3. The app will guide you through three setup steps with a progress bar at the top.

Enter the connection credentials required for your supplier. The fields vary by supplier — for example:

- **S&S Activewear:** Account Number (Username) and API Key
- **SanMar:** FTP Username and FTP Password
- **AlphaBroder:** Username and Password
- **Champro, Momentec Augusta, Decky:** No credentials required

Give your supplier a name (e.g., "S&S Activewear — Polos and T-Shirts — 50% Margin") so you can identify it in the dashboard. **Tip:** Descriptive names are especially helpful when you manage multiple supplier setups for different product lines or margin strategies.

Click **Test Credentials** to verify your connection before continuing. You'll see a green checkmark if the connection succeeds, or an error message if the credentials are incorrect.

[![Add Supplier form showing credential fields for S&amp;S Activewear](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551302/af6537eabf4dcc70e63e04846cc2/connect-supplier-credentials.png?expires=1781226900&signature=8dd599b81a17710fdb34c8460b38f945bef511b0feaeb59ad335c8c37f31df23&req=diQjH8x7nIJfW%2FMW1HO4zd2hq83FRn88uS78iNND8mzpSQhefvba1d9DpEtp%0AYzD3dn3iOK%2Fy5kEq030%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551302/af6537eabf4dcc70e63e04846cc2/connect-supplier-credentials.png?expires=1781226900&signature=8dd599b81a17710fdb34c8460b38f945bef511b0feaeb59ad335c8c37f31df23&req=diQjH8x7nIJfW%2FMW1HO4zd2hq83FRn88uS78iNND8mzpSQhefvba1d9DpEtp%0AYzD3dn3iOK%2Fy5kEq030%3D%0A)

Click **Next Step** to continue.

Choose which Shopify location should receive the supplier's inventory quantities. Each of your Shopify locations is listed with a dropdown where you can select:

- **Import Supplier Inventory** — inventory from the supplier is synced to this location.
- **Do Not Import Inventory** — this location is skipped.
- A specific supplier warehouse (if the supplier supports warehouse-level inventory, e.g., S&S Activewear or AlphaBroder).

**Important:** If no location is selected, supplier inventory will not be imported and your products will show zero stock.

[![Inventory Settings tab showing Shopify location selector with supplier warehouse options](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551308/f6b6a999cd2300ba625c55b505d5/shopify-location-selector.png?expires=1781226900&signature=3e312d653a6326c437edf9462daf0df0533c4c3e85d19c72c0c466f3a481fd59&req=diQjH8x7nIJfUfMW1HO4zRdIPpTva6ejKzdi4rI32V7NWdFo1AO%2BsDonudWv%0A5nqNR0DUgKLzf6qlErU%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551308/f6b6a999cd2300ba625c55b505d5/shopify-location-selector.png?expires=1781226900&signature=3e312d653a6326c437edf9462daf0df0533c4c3e85d19c72c0c466f3a481fd59&req=diQjH8x7nIJfUfMW1HO4zRdIPpTva6ejKzdi4rI32V7NWdFo1AO%2BsDonudWv%0A5nqNR0DUgKLzf6qlErU%3D%0A)

Click **Next Step** to continue.

On this step you'll see two sections:

**Publish Channels**

Select which Shopify sales channels (e.g., Online Store, Point of Sale) imported products should be published to.

**Field Mapping (Match Fields)**

Supplier data fields are already mapped to Shopify product fields with sensible defaults. For example, the supplier's product title maps to Shopify's Title, the supplier's price maps to Shopify's Price, and so on.

You can customize these later, but for now the defaults work well for most stores.

[![Product Settings tab showing publish channels and field mapping configuration](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551316/6735c1db6782f3d9be196717c2d7/publish-products-field-mapping.png?expires=1781226900&signature=705e6f501f72b91814a7bf741b4bd8f356138e6e18e8f33995eb3b0c615f0c91&req=diQjH8x7nIJeX%2FMW1HO4zUhNFs6vonVUQXxcLHkc018irz%2FfliGK0JySfU2a%0AkDGP1n56sPHW8%2FEuk40%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551316/6735c1db6782f3d9be196717c2d7/publish-products-field-mapping.png?expires=1781226900&signature=705e6f501f72b91814a7bf741b4bd8f356138e6e18e8f33995eb3b0c615f0c91&req=diQjH8x7nIJeX%2FMW1HO4zUhNFs6vonVUQXxcLHkc018irz%2FfliGK0JySfU2a%0AkDGP1n56sPHW8%2FEuk40%3D%0A)

Click **Save Supplier** to finish. You'll see a success banner confirming the supplier was saved.

---

## Step 3: Filter Products for Import

After saving, click **View & Import Products** to go to the product list.

Most suppliers have thousands of products. Use filters to narrow down what you want to import into your Shopify store:

1. Click **Edit Filters** to open the filter panel.
2. Add **Product Filters** to filter by fields like Brand Name, Style Number, or Category.
3. Add **Variant Filters** to filter by fields like Color Name, Size, or SKU.
4. Choose a condition (e.g., Equal To Any, Contains) and enter your values.
5. Click **Save Filters**.

The product list will update to show only matching products. You can also use **Browse Catalog** to search by title or brand and add products to your filter from there.

[![Filter panel showing product and variant filter conditions](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551322/b2f3e7981dd6f74f573fa2de1fa9/filter-panel-overview.png?expires=1781226900&signature=2e10831664eba45313cb739f09108bb5a8e4bc8b8eb4138e70fde77b6aa94a86&req=diQjH8x7nIJdW%2FMW1HO4zeCEzqbwKVoeAtSLp4C2eXzuOCCE1pI5kMrizn4f%0Af9UlkLTPYiKvZTC4hPY%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551322/b2f3e7981dd6f74f573fa2de1fa9/filter-panel-overview.png?expires=1781226900&signature=2e10831664eba45313cb739f09108bb5a8e4bc8b8eb4138e70fde77b6aa94a86&req=diQjH8x7nIJdW%2FMW1HO4zeCEzqbwKVoeAtSLp4C2eXzuOCCE1pI5kMrizn4f%0Af9UlkLTPYiKvZTC4hPY%3D%0A)

---

## Step 4: Import Products

Once your filters are set and you can see the products you want:

1. Click the **Import Products** button.
2. The app will queue a sync that creates products and variants in your Shopify store.
3. You can monitor progress in **Sync History** (accessible from the left sidebar).

The import runs as a Shopify bulk operation, so it may take a few minutes depending on the number of products. You'll see the sync status update from "queued" to "running" to "success."

[![Import Products button on the product list page](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551334/86b9a2b92cfff7fea6bebce2af32/import-products-button.png?expires=1781226900&signature=c71c0bb96716f1de4c0b480166c59a796fad47d04f927b5ff1b8932aad32292a&req=diQjH8x7nIJcXfMW1HO4zUX%2FJylrgGXKl5qDqJGusXSfYXK2KrF%2FBdgEvHw0%0A0HNR2UTxlH2S48rgsXo%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551334/86b9a2b92cfff7fea6bebce2af32/import-products-button.png?expires=1781226900&signature=c71c0bb96716f1de4c0b480166c59a796fad47d04f927b5ff1b8932aad32292a&req=diQjH8x7nIJcXfMW1HO4zUX%2FJylrgGXKl5qDqJGusXSfYXK2KrF%2FBdgEvHw0%0A0HNR2UTxlH2S48rgsXo%3D%0A)

---

## Step 5: Enable Automatic Syncing

To keep your products, inventory, and pricing up to date automatically:

- **Quick method:** Toggle **Auto Import** on the supplier card in the Manage Suppliers page. This enables daily syncing.
- **Detailed method:** Go to **Edit Supplier > Automatic Sync** tab to configure frequency (Daily or Every 6 Hours for S&S Activewear), what gets updated, and how new or unavailable products are handled.

[![Auto Import toggle on the supplier card in Manage Suppliers page](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551341/1ec118e2ee48e92766b0437fed80/enable-auto-sync.png?expires=1781226900&signature=8de7c253939dfab8306f17326bf1012f5677dca481853c4d2de24e31dcfb9427&req=diQjH8x7nIJbWPMW1HO4zfVMRJnBxKLC1oSn9b3IwPQQwBK9K%2FNFMi3W3XSe%0AwwWuZLzkRI8BoqofjPg%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2449551341/1ec118e2ee48e92766b0437fed80/enable-auto-sync.png?expires=1781226900&signature=8de7c253939dfab8306f17326bf1012f5677dca481853c4d2de24e31dcfb9427&req=diQjH8x7nIJbWPMW1HO4zfVMRJnBxKLC1oSn9b3IwPQQwBK9K%2FNFMi3W3XSe%0AwwWuZLzkRI8BoqofjPg%3D%0A)

---

## What's Next

You're up and running! Here are common next steps:

- **Customize field mappings** — adjust prices with markup formulas, combine fields for titles, or map to metafields. Go to **Edit Supplier > Product Settings > Match Fields** to get started.
- **Add more suppliers** — you can connect multiple suppliers and manage them independently.
- **Enable AI+** — enrich your products with AI-generated SEO titles, descriptions, tags, and categories. Look for the **Enable AI+ Data** button in your field mapping settings, or go to **Manage Subscriptions > Lifetime Add-Ons**.
- **Link existing products** — if you already have products in Shopify that you want to sync with a supplier, enable Product Mappings under **Edit Supplier > Advanced Settings**, then use the **Product Mappings** tab.
- **Set up order sync** — for **S&S Activewear**, **SanMar**, **ACC**, and **Cutter & Buck**, go to **Edit Supplier > Order Settings** to configure placement (see **Syncing Orders with S&S Activewear** or **Syncing Orders with PromoStandards**). For other suppliers, use the same tab to submit a setup request; see **Supported Suppliers & Features**.