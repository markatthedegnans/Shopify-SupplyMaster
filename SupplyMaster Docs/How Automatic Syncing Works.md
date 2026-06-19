---
title: "How Automatic Syncing Works"
source: "https://help.comstack.com/en/articles/13934887-how-automatic-syncing-works"
author:
published: 2026-03-09
created: 2026-06-11
description: "Automatic syncing keeps your Shopify products up to date with your supplier's catalog."
tags:
  - "clippings"
---
Automatic syncing keeps your Shopify products up to date with your supplier's catalog. When enabled, SupplyMaster periodically fetches the latest product data — including pricing, inventory, images, and new items — and applies changes to your store based on the settings you configure. This article covers sync frequency, update settings, auto-creation rules, and how to handle unavailable products.

---

## Auto Import vs. Full Auto Sync Settings

[![The Manage Suppliers page showing the Auto Import toggle on each supplier row](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322649/545110b8703f0ea22e4a39672923/auto-import-toggle-list.png?expires=1781227800&signature=85fb60c9d48376ec009397d49104a5ad5e24b6488d6941163467146c6fdf1eab&req=diEjFcp8n4dbUPMW1HO4zeiNI38ytt4XF0%2FHFicJd3A95Qkd4pgVfwHz%2FzRQ%0Aq5T45C3iV%2BqC9Crctfk%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322649/545110b8703f0ea22e4a39672923/auto-import-toggle-list.png?expires=1781227800&signature=85fb60c9d48376ec009397d49104a5ad5e24b6488d6941163467146c6fdf1eab&req=diEjFcp8n4dbUPMW1HO4zeiNI38ytt4XF0%2FHFicJd3A95Qkd4pgVfwHz%2FzRQ%0Aq5T45C3iV%2BqC9Crctfk%3D%0A)

There are two levels of automation:

- **Auto Import toggle** — A quick on/off switch on each supplier card. When enabled, SupplyMaster runs a daily import using your saved filters. This is the simplest way to keep products flowing in.
- **Full Auto Sync Settings** — Found in **Edit Supplier** > **Automatic Sync**. These settings give you fine-grained control over sync frequency, which fields get updated, whether new products and variants are auto-created, and what happens to products that disappear from the supplier catalog.

[![The Automatic Sync tab showing all sync configuration settings](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322681/f6251f5408b8226c6f8c5ce38c9e/automatic-sync-tab-overview.png?expires=1781227800&signature=a83517b0c5531465d535924db9738a867a82190fb72fcb68254db52d3c99becc&req=diEjFcp8n4dXWPMW1HO4zcjHWfAOjPcIUfgw34jMNEp3tcJyYbrw48AUZutg%0An5pE9aOJUguegF5Tpmo%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322681/f6251f5408b8226c6f8c5ce38c9e/automatic-sync-tab-overview.png?expires=1781227800&signature=a83517b0c5531465d535924db9738a867a82190fb72fcb68254db52d3c99becc&req=diEjFcp8n4dXWPMW1HO4zcjHWfAOjPcIUfgw34jMNEp3tcJyYbrw48AUZutg%0An5pE9aOJUguegF5Tpmo%3D%0A)

The Auto Import toggle uses the default daily schedule. For more control, configure the full Auto Sync Settings described below.

---

## Sync Frequency

[![The Sync Frequency setting showing Never, Daily, and Every 6 Hours options](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322746/a0e493a2b7022b2bfcc8d6765cda/sync-frequency-setting.png?expires=1781227800&signature=c3991339afcdb4178b8f5af4392714e54ae72f53f2571094814fc12096e8f0c5&req=diEjFcp8n4ZbX%2FMW1HO4zdqCHg7y6l8jcu3C5sPaY%2FLsD0hOouoaYHe5SNSZ%0ACv7UQxq9qrLA0n1fAcg%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322746/a0e493a2b7022b2bfcc8d6765cda/sync-frequency-setting.png?expires=1781227800&signature=c3991339afcdb4178b8f5af4392714e54ae72f53f2571094814fc12096e8f0c5&req=diEjFcp8n4ZbX%2FMW1HO4zdqCHg7y6l8jcu3C5sPaY%2FLsD0hOouoaYHe5SNSZ%0ACv7UQxq9qrLA0n1fAcg%3D%0A)

Choose how often SupplyMaster automatically syncs product data from the supplier.

| **Option** | **Schedule** | **Availability** |
| --- | --- | --- |
| Never | No automatic sync — manual imports only | All suppliers |
| Daily | Once per day at 02:00 UTC | All suppliers |
| Every 6 Hours | Four times daily at 02:00, 08:00, 14:00, and 20:00 UTC | S&S Activewear only |

Most suppliers support **Never** and **Daily**. S&S Activewear also offers an **Every 6 Hours** option for merchants who need more frequent inventory and pricing updates.

---

## Update Settings

[![The Update Settings dropdown with options for All Fields with Images, All Fields Except Images, Only Variant Fields, and Only Inventory](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322763/2d792bca6950b89af605442100c3/update-settings-card.png?expires=1781227800&signature=70d2cccabcf88f4d09be11e6e293e78363a462792f9be5849f0525fb2f7566bc&req=diEjFcp8n4ZZWvMW1HO4zZdzhtgTXAKvXRc9lJmGtyX3m85YKW%2FqJM3LpqZ8%0AwAeZEcU8TEVAJ6j6TKg%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322763/2d792bca6950b89af605442100c3/update-settings-card.png?expires=1781227800&signature=70d2cccabcf88f4d09be11e6e293e78363a462792f9be5849f0525fb2f7566bc&req=diEjFcp8n4ZZWvMW1HO4zZdzhtgTXAKvXRc9lJmGtyX3m85YKW%2FqJM3LpqZ8%0AwAeZEcU8TEVAJ6j6TKg%3D%0A)

After products are first imported, **Update Settings** controls which fields get refreshed during future syncs. Choose the option that matches how you manage your product data:

| **Option** | **What Gets Updated** | **Best For** |
| --- | --- | --- |
| All Fields with Images | Everything — titles, descriptions, pricing, inventory, weight, images | Missing images or when you want a complete refresh every sync |
| All Fields Except Images | Titles, descriptions, pricing, inventory, weight — but not images | Blank reselling (most efficient — saves time and bandwidth) |
| Only Variant Fields | Color, size, pricing, inventory, and weight only | Manually editing product titles, descriptions, or images and wanting to keep those edits |
| Only Inventory | Inventory quantities only | Managing all other product data manually and only needing stock-level updates |

Update Settings only take effect after a product or variant has existed for at least **12 hours**. During that initial window, all fields are updated regardless of your setting. This allows the system to retry and fully complete the product creation process — ensuring all data (titles, descriptions, images, pricing, and inventory) is brought up to date even if errors occurred during the initial import.

After the 12-hour window, future syncs follow your Update Settings. For example, if you've set it to **Only Variant Fields**, only pricing and inventory will continue to update automatically while product-level fields like titles and descriptions remain unchanged.

---

## Auto Create Products & Variants

[![The Auto Create Products and Variants setting with options for Always Create, No New Variants, No New Products, and No New Products or Variants](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322783/3d3bd606fe65141fd6908710c253/auto-create-setting.png?expires=1781227800&signature=08270695e713d46f3cc8e8e3289b5674b7ce020f339f6484def37c249cfcec40&req=diEjFcp8n4ZXWvMW1HO4zcXHERKw%2FUUw7OyaqxRrb2Dtt7HkDAd0wf6Pn6VU%0Aq5bN%2Bk2OHCE7VaDzev4%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322783/3d3bd606fe65141fd6908710c253/auto-create-setting.png?expires=1781227800&signature=08270695e713d46f3cc8e8e3289b5674b7ce020f339f6484def37c249cfcec40&req=diEjFcp8n4ZXWvMW1HO4zcXHERKw%2FUUw7OyaqxRrb2Dtt7HkDAd0wf6Pn6VU%0Aq5bN%2Bk2OHCE7VaDzev4%3D%0A)

This setting controls what happens when the supplier adds new products or new sizes and colors to existing products. Choose based on how you curate your catalog:

| **Option** | **Behavior** | **Best For** |
| --- | --- | --- |
| Always Create Products & Variants | Every new product and variant matching your filters is automatically created in Shopify | Resellers who want full automation |
| No New Variants on Existing Products | New products are created, but new variants (sizes/colors) are not added to products that already exist | Decorators who customize variant selections and don't want new sizes appearing unexpectedly |
| No New Products (Variants may be added) | No new products are created, but new variants can be added to existing products | Stores that manually choose which products to carry but want size/color updates |
| No New Products or Variants | Nothing new is created — only existing products and variants are updated | Curated stores that want full manual control over their catalog |

---

## Action on Unavailable Products

[![The Action on Unavailable Products setting with Archive Products and No Action options](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322810/e636434d818c5cafa2fb42e551ff/action-on-unavailable-setting.png?expires=1781227800&signature=8b781f8a721acaecf0502c19ceef1e1833ebec62cfa0b61006a2f78833c0e225&req=diEjFcp8n4leWfMW1HO4zbuvRDJf%2FfmcjvDGM9dvehDFnoJWs8wa1hIBTfWb%0A2D3HYK2MUUBQdRqY5GE%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322810/e636434d818c5cafa2fb42e551ff/action-on-unavailable-setting.png?expires=1781227800&signature=8b781f8a721acaecf0502c19ceef1e1833ebec62cfa0b61006a2f78833c0e225&req=diEjFcp8n4leWfMW1HO4zbuvRDJf%2FfmcjvDGM9dvehDFnoJWs8wa1hIBTfWb%0A2D3HYK2MUUBQdRqY5GE%3D%0A)

When a product disappears from the supplier catalog or no longer matches your filters, SupplyMaster can take one of two actions:

- **Archive Products** — Automatically archives the product in Shopify. Archived products are hidden from your storefront but remain in your Shopify admin. You can restore them at any time.
- **No Action** — The product stays active in your store but stops receiving updates. Inventory will not be adjusted, and the product may show stale data.

The default is **No Action**. If you want to keep your storefront clean and avoid listing discontinued products, switch to **Archive Products**.

---

## Always Update Variant Images

[![The Always Update Variant Images setting with Use Update Settings and Always Update Images options](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322836/a716bef04b5389be1f98634accfb/always-update-images-setting.png?expires=1781227800&signature=e07c6837fcab6221f61f5f68be02605b1d89e19c89a42d3d336cb9b73f1b7ed6&req=diEjFcp8n4lcX%2FMW1HO4zZ5XJiNITV9ownueZoZ6CIWd088Qq3rvhe4Re1rd%0Ay6x41SaV0afPHo4UA8A%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143322836/a716bef04b5389be1f98634accfb/always-update-images-setting.png?expires=1781227800&signature=e07c6837fcab6221f61f5f68be02605b1d89e19c89a42d3d336cb9b73f1b7ed6&req=diEjFcp8n4lcX%2FMW1HO4zZ5XJiNITV9ownueZoZ6CIWd088Qq3rvhe4Re1rd%0Ay6x41SaV0afPHo4UA8A%3D%0A)

This setting overrides the **Update Settings** for images specifically. It only appears when your Update Settings is not already set to **All Fields with Images**.

- **Use Update Settings** — Images update (or don't) based on your chosen Update Settings.
- **Always Update Images** — Images are refreshed on every sync regardless of the Update Settings. Useful when a supplier frequently updates product photos and you want to keep your store current.