---
title: "AI+ Enriched Product Data"
source: "https://help.comstack.com/en/articles/13935142-ai-enriched-product-data"
author:
published: 2026-05-27
created: 2026-06-11
description: "AI+ is a one-time add-on that uses AI to generate optimized, search-friendly product content for every product in a supplier catalog."
tags:
  - "clippings"
---
AI+ is a one-time add-on that uses AI to generate optimized, search-friendly product content for every product in a supplier catalog. Once enabled, AI-generated fields appear alongside standard supplier fields in Match Fields and can be mapped to Shopify just like any other field.

---

## What AI+ Adds

AI+ enriches each product with 15 additional fields. These fields are prefixed with `AI_` in the Match Fields source dropdown:

| **AI+ Field** | **Description** |
| --- | --- |
| AI SEO Title | Search-optimized product title |
| AI SEO Description | Meta description written for search engines |
| AI Bulleted Description | Feature list formatted as bullet points |
| AI Short Description | One–two sentence summary |
| AI Medium Description | Paragraph-length description |
| AI Long Description | Full marketing description |
| AI Clean Title | Cleaned-up product title (removes symbols and formatting artifacts) |
| AI Clean Handle | SEO-friendly URL handle |
| AI Shopify Product Category | Human-readable Shopify standard product category |
| AI Shopify Product Category ID | Numeric Shopify taxonomy category ID — maps directly to the **Category** field |
| AI Base Category | Top-level product category (e.g., “T-Shirts”) |
| AI Sub Category | More specific category (e.g., “Performance T-Shirts”) |
| AI Tags | Auto-generated tags for filtering and collections |
| AI Material | Fabric or material type (e.g., “Cotton”, “Polyester”) |
| AI Gender | Target gender (e.g., “Men”, “Women”, “Unisex”) |

AI+ also adds four filter fields — **AI Base Category**, **AI Sub Category**, **AI Gender**, and **AI Material** — so you can filter your import using AI-enriched data instead of (or alongside) the supplier’s original values.

---

## Pricing

AI+ is a **one-time purchase of $99 per supplier type**. For example, if you have two S&S Activewear supplier connections, you only pay once for the S&S Activewear type. Adding a different supplier type (e.g., SanMar) requires a separate $99 purchase.

The charge appears as a one-time Shopify charge on your store’s invoice. There are no recurring fees for AI+ data.

---

## How to Enable AI+

There are two ways to activate AI+ for a supplier:

1. Open your supplier and go to the **Match Fields** section.
2. Click the **Enable AI+ Data** button (purple magic-wand icon) at the top of the field list.
3. Review the features in the confirmation modal and approve the $99 one-time Shopify charge.
4. Once approved, AI+ fields appear in the source dropdown and the **Add AI+ Field Defaults** button becomes available.

1. Go to the product listing for your supplier (View Products).
2. Select **Enable AI+ Fields**.
3. Approve the charge in the confirmation modal.

---

## Default AI+ Field Mappings

After enabling AI+, click **Add AI+ Field Defaults** in Match Fields to apply a recommended set of mappings. These defaults give you a solid starting point — you can adjust or remove any of them afterward:

| **Shopify Field** | **AI+ Source** | **Modifier** |
| --- | --- | --- |
| Description (HTML) | AI Bulleted Description | `{​{ AI_shortDescription }​} <br/> {​{ AI_bulletedDescription }​}` |
| Category | AI Shopify Product Category ID | — |
| SEO Title | AI SEO Title | — |
| SEO Description | AI SEO Description | — |
| Product Type | AI Base Category | — |
| Tags | AI Tags | — |
| Tags | AI Material | — |
| Tags | AI Gender | — |

The defaults merge with your existing mappings. For **Tags**, new sources are added alongside any tags you already have. For other fields (Description, Category, etc.), the AI+ source replaces the previous source for that field.

---

## Supported Suppliers

AI+ is available for all built-in suppliers that include AI-enriched data in their catalog:

- S&S Activewear
- SanMar (US)
- SanMar Canada
- AlphaBroder
- Augusta Sportswear (Momentec)
- AS Colour (US)
- Edwards
- Cap America
- Otto Cap
- Goldstar
- Charles River Apparel
- Cutter & Buck
- Champro
- JDS Industries
- Atlantic Coast Cotton (ACC)
- Decky
- Scrub Authority

Custom Suppliers do not support AI+ because the enrichment relies on known catalog structures from each built-in supplier.

---

## Legacy AI+ Monthly Plan

AI+ was previously available as a monthly add-on ($29/mo). It has since been replaced by the one-time $99 per-supplier-type model. If your account still has the legacy monthly plan active alongside a one-time purchase, you will see a banner on the **Manage Subscriptions** page prompting you to remove the monthly add-on and re-approve your subscription at a lower price. Clicking the banner removes the redundant monthly charge — your one-time AI+ access is not affected.