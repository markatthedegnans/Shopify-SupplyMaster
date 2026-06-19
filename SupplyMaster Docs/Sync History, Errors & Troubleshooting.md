---
title: "Sync History, Errors & Troubleshooting"
source: "https://help.comstack.com/en/articles/13934956-sync-history-errors-troubleshooting"
author:
published: 2026-05-27
created: 2026-06-11
description: "The Sync History page shows a log of every import and sync that has run for your store."
tags:
  - "clippings"
---
The **Sync History** page shows a log of every import and sync that has run for your store. Use it to verify that syncs are completing successfully, inspect errors, and cancel an in-progress sync.

---

## Reading the Sync History Page

Navigate to **Sync History** from the app menu. The page displays a table with the following columns:

[![The Sync History page showing a table of recent sync entries](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2430465220/f908f682d2e8b424d769b5549a5a/sync-logs-table.png?expires=1781227800&signature=3111befed915aafb6c0571ef65de80ccead7896efdc81389028d99ab3cb79089&req=diQkFs14mINdWfMW1HO4zerkdPh8pob9uyxLtecH5dbkFUi9ZaIxQUU84xkz%0A0B4Maiu3sPzbMgdaZ5g%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2430465220/f908f682d2e8b424d769b5549a5a/sync-logs-table.png?expires=1781227800&signature=3111befed915aafb6c0571ef65de80ccead7896efdc81389028d99ab3cb79089&req=diQkFs14mINdWfMW1HO4zerkdPh8pob9uyxLtecH5dbkFUi9ZaIxQUU84xkz%0A0B4Maiu3sPzbMgdaZ5g%3D%0A)

| **Column** | **Description** |
| --- | --- |
| Date & Time | When the sync started or last updated |
| Supplier | The supplier name associated with this sync |
| Data Rows | Number of product or variant rows processed |
| Sync Action | The type of operation (e.g., Product Create, Product Update, Image Upload) |
| Status | Current state of the sync (see statuses below) |
| Details | Summary counts (e.g., "150 variants, 12 products") |

Use the pagination controls at the bottom to browse older sync entries. The page auto-refreshes every 30 seconds so you can monitor a running sync in real time.

---

## Sync Statuses

| **Status** | **Meaning** |
| --- | --- |
| Success (green check) | The sync completed without errors. All products were processed. |
| Failed (red X) | The sync encountered an error and could not complete. See the Response column for details. |
| Cancelled (yellow X) | The sync was manually cancelled by you before it finished. |
| Running (spinner) | The sync is currently in progress. |
| Queued (progress bar) | The sync is waiting in line. Only one sync runs at a time per store — queued syncs start once the current one finishes. |

---

## Cancelling a Running Sync

If a sync is in progress and you need to stop it:

1. Go to **Sync History**.
2. Click the **Cancel Syncs** button in the top-right corner (it appears in red when a sync is running).
3. The current sync will be marked as **Cancelled**.

Products that were already created or updated before cancellation remain in your Shopify store. Cancelling only stops the remaining rows from being processed.

---

## Common Errors

This error means Shopify could not find a product that SupplyMaster tried to update. It usually happens when a product was deleted from Shopify but SupplyMaster's records still reference it. SupplyMaster automatically cleans up these stale references when this error occurs, so the issue resolves itself on the next sync.

Similar to the above, but for individual variants. A variant may have been deleted from Shopify outside of SupplyMaster. The stale variant references are automatically cleaned up when this error is detected.

If your subscription is paused or your plan's product update limit has been reached, syncs will stop running. Existing products remain in your store but won't receive updates. To resume syncing, upgrade your plan or wait for your update counter to reset.

Your plan has a maximum number of variants that SupplyMaster can manage. When this limit is reached, new products and variants cannot be created. Existing products continue to sync normally (inventory, pricing, and field updates still run). Upgrade your plan or add a variant add-on to create more products.

If Sync History shows *“Shopify's variant creation limit reached. Non-Shopify Plus stores with 50,000+ variants are capped at 1,000 new variants/day”*, this is a **Shopify platform limit**, not a SupplyMaster limit. It applies to non-Plus stores once total store variants reach 50,000.

No action is required — the next scheduled sync will automatically resume creating new variants the following day. Existing products continue to sync normally in the meantime. See our **Shopify's Daily Variant Creation Limit** article for the full explanation and options.

---

## Failed Syncs & Automatic Retries

When a sync fails due to an **internal or timeout error** (e.g., a temporary Shopify API issue), SupplyMaster automatically retries the failed rows in the next sync cycle. You don't need to do anything — the retry happens behind the scenes.

If a sync continues to fail across multiple attempts, the issue may require investigation. There is no manual "retrigger" button in the UI. Contact support if you see persistent failures.

---

## Stuck Imports

Imports typically take 10 minutes to 1 hour depending on the number of products. If an import appears stuck (showing "Running" for an extended period), here's what to check:

1. **Wait a bit longer** — Large catalogs with thousands of products can take up to an hour.
2. **Check your subscription** — Make sure your plan is active and you haven't hit your update or variant limit.
3. **Check your supplier connection** — Go to **Edit Supplier** and run **Test Connection** to verify credentials are still valid.
4. **Refresh the page** — Click the **Refresh** button on the Sync History page to get the latest status.
5. **Contact support** — If the sync has been running for more than 2 hours with no progress, reach out to the support team.

---

## Tips

- Check Sync History after your first import to confirm everything went through correctly.
- Check the Details column to identify which products had errors.
- If you see repeated `PRODUCT_DOES_NOT_EXIST` errors, verify you haven't deleted products from Shopify that SupplyMaster is still tracking. These clean up automatically after one sync cycle.
- Cancelling a sync does not undo changes already made — products created before cancellation stay in your store.