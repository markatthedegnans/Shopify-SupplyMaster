# Project Overview -- SupplyMaster x Cutter & Buck
### shoptorreypines.com | The Golf Shop at Torrey Pines | Torrey Pines Club Corporation

> **How to Read This Document**
> This is a descending-altitude view of the project -- from the store's strategic context down to the specific implementation task at hand. Read top-to-bottom on first contact. Use the section headers to navigate back to the right altitude when context is needed during execution.

---

## ALTITUDE: 10,000 ft -- shoptorreypines.com as a Strategic Asset

**shoptorreypines.com** is the primary revenue-generating digital asset for Torrey Pines Club Corporation (TPCLUBCORP). It is the organization's complete online retail presence -- serving the customer base of **The Golf Shop at Torrey Pines**, an 8,000 square foot resort pro shop in La Jolla, California, at one of San Diego's premiere destination golf facilities. The store hosts annual PGA TOUR events and serves both walk-in retail and online customers.

The store is operated as a one-person e-commerce operation built on Shopify. All elements are owned in-house: development, catalog management, product photography, order fulfillment, packing, shipping, and customer support. AI-assisted tools support customer communications (Microsoft Copilot for email, Shopify Inbox AI for real-time inquiries). Social media channels (Facebook, Twitter) are managed alongside the store for marketing copy promoting golfer development programs and individual items.

**The catalog challenge:**
The current catalog is limited to items photographed and manually listed in-house -- a time-intensive process that constrains scale. For commodity golf apparel (polos, outerwear, headwear) from established wholesale suppliers, manually photographing and listing every style is not a viable path to catalog growth. The opportunity is to automate the data pipeline for wholesale apparel while preserving the hand-produced quality for unique, Torrey Pines-branded merchandise.

**Why supplier integration matters to this store:**
- Premium golf apparel (Cutter & Buck) is a natural fit for a resort pro shop at a destination golf facility
- A wholesale supplier integration eliminates manual photography and listing for those products
- Catalog, pricing, and inventory stay current automatically -- no ongoing manual maintenance
- The Shopify store can carry a curated premium apparel line alongside the existing Torrey Pines branded merchandise
- PromoStandards order sync eliminates manual PO entry -- purchase orders flow automatically from Shopify sales to C&B fulfillment

**The operational leverage this creates:**
Once the integration is running -- catalog auto-populates, inventory syncs daily, pricing recalculates on a margin formula, and orders auto-submit to C&B -- the apparel offering can scale without proportionally expanding the workload. That leverage is significant for a one-person operation.

**Governing constraints:**
- Products are hand-picked -- the full supplier catalog will not be imported indiscriminately
- Pricing must be formula-driven and maintain a target margin automatically -- prices cannot be managed manually at scale
- The store is live and serving real customers -- changes are validated on a small test set before being applied broadly
- New tools and integrations costing under `~$1,000` can be adopted within the e-commerce domain without a formal approval process; investments above that threshold require a business case demonstrating that the benefit to the organization exceeds the cost

---

## ALTITUDE: 7,500 ft -- SupplyMaster as the Integration Platform

SupplyMaster is a Shopify app built by Comstack that connects wholesale supplier catalogs directly to Shopify stores -- automating product import, inventory sync, pricing, and (for supported suppliers) order placement. It is the top-rated apparel supplier integration on the Shopify App Store in the U.S. and Canada.

**Why SupplyMaster was selected:**
- Direct integration with Cutter & Buck -- no credentials required for catalog sync (connects instantly on supplier type selection)
- PromoStandards order sync supported for C&B -- automatic PO submission at time of sale, blind dropship to end buyer
- Field mapping with Liquid formula support -- margin-targeting pricing rules, text transformations, metafield mapping, all configurable without code
- AI+ enrichment add-on -- generates SEO-optimized product copy, Shopify standard categories, tags, and program-aware descriptions ($99 one-time per supplier type)
- Full sync monitoring dashboard with history visibility
- 5-day free trial on all plans; under $1,000/year at the Basic plan level

**Platform capability map:**

| Capability                   | What It Does                                                                             | Relevant to This Project            |
| ---------------------------- | ---------------------------------------------------------------------------------------- | ----------------------------------- |
| Supplier catalog import      | Fetches C&B feed, applies filters, creates/updates Shopify products                      | Core -- primary function             |
| Filters (product + variant)  | Hand-pick styles by style number, category, color, size                                  | Core -- curated catalog strategy     |
| Browse Catalog               | Visual grid/list view of the full supplier catalog for product discovery                 | Core -- used to select hero styles   |
| Field Mapping (Match Fields) | Maps supplier data fields to Shopify fields with optional Liquid modifiers               | Core -- margin pricing, titles, tags |
| Liquid formula modifiers     | Margin-targeting pricing, text cleanup, fallback chains, conditional logic               | Core -- pricing formula              |
| Auto Sync                    | Scheduled daily re-fetch and update across all mapped fields                             | Core -- keep catalog current         |
| Update Settings              | Controls which fields refresh on sync (all / no images / variants only / inventory only) | Core -- protect customized content   |
| AI+ Enrichment               | 15 AI-generated fields: SEO titles, descriptions, categories, tags, material, gender     | High value -- pro shop product copy  |
| Inventory location mapping   | Maps supplier stock to Shopify locations; safety stock buffer                            | Core -- single-location pro shop     |
| Order Sync (PromoStandards)  | Auto-submits PO to C&B at time of sale; C&B blind-ships to end buyer                     | **Core -- required at launch**       |
| Product Mappings             | Links existing Shopify products to supplier inventory for sync                           | Advanced -- for future use           |
| Metafields                   | Maps supplier data to custom Shopify metafields; displayed via theme Liquid              | Advanced -- for future use           |
| Sync History                 | Log of every import and sync: status, row counts, errors                                 | Ongoing monitoring                  |
| Variant Splitting            | Creates one product per color variation (legacy feature)                                 | Advanced -- optional                 |

**Plan sizing for this project:**
Cutter & Buck has ~15,000 total variants across ~330 styles. This integration covers a curated set of hand-picked hero styles. Estimate: `15-30 styles x ~8 colors x ~6 sizes = 720-1,440 variants`. The Basic plan ($29/mo) handles up to 5,000 variants and 200,000 monthly updates -- comfortably sufficient for a focused pro shop catalog. Upgrade to Pro ($99/mo, 50,000 variants) is available if the catalog expands.

---

## ALTITUDE: 5,000 ft -- The Cutter & Buck Integration

Cutter & Buck is a natural fit for The Golf Shop at Torrey Pines: premium recycled-fabric golf programs (Virtue Recycled, Adapt Recycled, Rainier Recycled), a brand profile that aligns with the facility's prestige, and an existing wholesale account with PromoStandards credentials already in hand.

**The Cutter & Buck supplier connection in SupplyMaster:**
- **Catalog credentials:** None required -- connects automatically on supplier type selection
- **PromoStandards credentials:** Already in hand -- required for order sync; configured at launch
- **Default pricing:** SupplyMaster maps C&B data to MSRP by default -- overridden with a margin-targeting Liquid formula based on the wholesale cost field
- **AI+:** $99 one-time charge covering all C&B connections in the store (not recurring); generates program-aware, resort-quality product copy and accurate SEO metadata

**Fulfillment model:**
C&B items (decorated wholesale) -- listed on shoptorreypines.com at margin-targeted retail prices -- customer places order -- SupplyMaster automatically submits a PromoStandards PO to C&B -- C&B blind-ships directly to the end buyer. No manual PO entry.

> **Decoration model confirmed -- Model A (pre-arranged standing program):** C&B holds dedicated Torrey Pines pre-decorated SKUs in their system. SupplyMaster lists and orders using those SKUs. When a PromoStandards PO is submitted for a pre-decorated SKU, C&B fulfills with the decorated item -- no decoration instructions need to be transmitted at order time. No further configuration is needed to support this model.

**Catalog strategy:**
A focused set of hero styles will be hand-picked from the Browse Catalog interface. The import filter will be built using style numbers (Equal To Any). The first import will be limited to 3 test styles; once verified in Shopify admin, the filter will be expanded to the full hero set.

> **NOTE (2026-06-17):** Initial test import used 2 standard undecorated C&B catalog SKUs to verify the import pipeline. These are not pre-decorated Torrey Pines SKUs. Before the full hero import, the correct pre-decorated Torrey Pines SKU IDs must be confirmed with C&B and substituted into the filter.

---

## ALTITUDE: 2,500 ft (Ground) -- The 7-Module Implementation Plan

SupplyMaster is installed and the C&B supplier connection is configured. The following 7-module plan takes the integration from zero to a live, auto-syncing, auto-ordering Cutter & Buck catalog on shoptorreypines.com.

---

### Module 1 -- Mental Model: What SupplyMaster Actually Does
**Goal:** Understand the full data and order pipeline before touching the app.

**Catalog pipeline:**
```
Cutter & Buck Feed  ->  SupplyMaster  ->  shoptorreypines.com (Shopify)
  (supplier data)       (the bridge)       (your storefront)
```

**Order pipeline (PromoStandards):**
```
Customer order (Shopify)  ->  SupplyMaster  ->  C&B PromoStandards PO  ->  C&B ships to buyer
```

**Key terms to internalize:**

| Term           | Definition                                                                                                                         |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| Variant        | One color + size combination (e.g., Virtue Recycled Polo / Navy / Medium = 1 variant). Plan limits are measured in total variants. |
| Field Mapping  | A rule: take C&B source field -- apply optional modifier -- write to Shopify destination field                                       |
| Modifier       | A Liquid code snippet attached to a mapping that transforms the data (math, text, conditionals)                                    |
| Auto Sync      | The scheduled job that re-fetches C&B data and updates Shopify products automatically                                              |
| Filter         | Rules that gate which products from the C&B catalog enter the Shopify store                                                        |
| PromoStandards | Industry-standard API protocol used to submit purchase orders from SupplyMaster to C&B automatically                               |
| Blind Ship     | C&B ships to the end customer without identifying C&B on the packing slip                                                          |
| Metafield      | A custom data slot in Shopify for storing extra supplier data beyond standard fields                                               |
| Supplier       | The SupplyMaster connection record for Cutter & Buck                                                                               |

**Reference docs:** *What Is SupplyMaster?*, *Glossary of Terms*, *Syncing Orders with PromoStandards (ACC, SanMar, Cutter & Buck)*, *Sell Cutter & Buck on Shopify: Golf & Corporate Apparel Guide*

---

### Module 2 -- Plan Sizing
**Goal:** Choose the right subscription plan before the free trial starts.

Estimate variant count: `[number of hero styles] x [average colors per style] x [sizes per color]`.

Example: `20 styles x 8 colors x 6 sizes = 960 variants` -- Basic plan ($29/mo) is the correct choice (5,000 variant limit, 200,000 monthly updates). The full 5-day free trial runs on whatever plan is selected -- start with Basic.

**AI+ consideration:** $99 one-time for all C&B connections (not recurring). For a curated pro shop with hand-picked hero styles, AI+ delivers strong ROI -- program-aware, resort-quality descriptions and SEO metadata instead of raw spec-sheet text. Best sequencing: enable after the first test import succeeds, re-import the 3 test styles with AI+ active, and compare the copy before committing to the full hero set.

**Reference doc:** *Plans, Pricing & Account Limits*

---

### Module 3 -- Installation & Supplier Setup
**Goal:** Install SupplyMaster and configure the Cutter & Buck supplier connection, including PromoStandards order sync.

**Setup checklist:**
- [x] Install from apps.shopify.com/supply-master
- [x] Approve Shopify subscription -- Basic plan (5-day free trial)
- [x] Manage Suppliers -- **Add Supplier** -- select **Cutter & Buck**
- [x] Name the connection: `Cutter & Buck -- Hero Styles -- Pro Shop`
- [x] No catalog credentials needed -- skip Test Credentials (C&B catalog connects automatically)
- [x] **Next Step** -- Inventory Settings
- [x] Map Shopify location -- **Import Supplier Inventory**
- [x] Set Inventory Adjustment Quantity: `5` (safety buffer -- prevents overselling near the end of available stock)
- [x] **Next Step** -- Product Settings
- [x] Publish Channel: *(none selected -- SupplyMaster default; products import with no channel assigned, providing a safe import buffer)*
- [x] Leave field mapping defaults for now (configure in Module 5)
- [x] **Next Step** -- Order Settings
- [x] Set Order Sync: **Manually Fulfill Orders** *(for the initial test period -- switch to Automatic after first verified orders flow correctly)*
- [x] Enter PromoStandards **Username** and **Password**
- [x] Shipping Carrier: **UPS** | Service: **GRND PREPAID**
- [x] Blind Ship: **Yes**
- [x] **Save Supplier** ✓

**Observations from setup (2026-06-17):**
- Products imported as **Active** status (not Draft) -- safe because no sales channels are assigned by default
- SupplyMaster's default is no channel selected -- Active + no channel = not visible to any storefront
- This is a better safety net than Draft status: products remain hidden even if status is accidentally changed

**Reference docs:** *Getting Started with SupplyMaster*, *How to Add & Manage Suppliers*, *Setting Up Inventory by Warehouse Location*, *Syncing Orders with PromoStandards (ACC, SanMar, Cutter & Buck)*

---

### Module 4 -- Filtering: Hand-Picking Hero Styles
**Goal:** Configure filters that import only the selected hero styles.

**Filter strategy:**
- Primary filter: **Style Number -- Equal To Any -- [style numbers, comma-separated]**
- Discovery method: **Browse Catalog tab** -- visual product grid -- check each hero style -- **Save to Import Filters** (builds the filter automatically -- no manual entry required)
- Optional variant filter: **Size -- Not Equal To Any -- [sizes not carried]** (e.g., XS, 4XL, 5XL)

**Test-first approach:** Set the filter to exactly 3 styles for the first import. Verify in Shopify admin. Expand to the full hero set after confirming results.

**Cutter & Buck style number format:** Alphanumeric IDs. Standard blank styles use formats like `BCB00101` (men's) and `LCB00101` (women's). **Pre-decorated Torrey Pines SKUs will have different style numbers** than the standard undecorated catalog -- they are dedicated SKUs assigned by C&B for the standing decoration program. Use Browse Catalog to locate and confirm the exact pre-decorated SKU IDs. Do not use standard blank-catalog style numbers as filters; doing so will result in POs for undecorated goods.

> **NOTE (2026-06-17):** The initial 2-product test import used standard undecorated C&B catalog SKUs (no variant filters). This was intentional -- to verify the import pipeline works before switching to pre-decorated SKUs. The full hero import must use the correct pre-decorated Torrey Pines SKU IDs. Confirm these with C&B before proceeding.

**Safety net:** Filter History saves every filter snapshot -- roll back anytime from Edit Filters -- More Actions -- Filter History.

**Reference docs:** *How to Filter Products for Import*, *Browsing & Searching the Supplier Catalog*, *Using AI Tools for Filters & Formulas*

---

### Module 5 -- Field Mapping & Pricing
**Goal:** Configure how C&B data maps to Shopify fields and build the margin-targeting pricing formula.

**Key C&B data fields for the pro shop:**

| Field                        | Level   | Purpose                                         |
| ---------------------------- | ------- | ----------------------------------------------- |
| `title`                      | Product | Shopify Title                                   |
| `descriptionHtml`            | Product | Shopify Description                             |
| `vendor` / `brandName`       | Product | Shopify Vendor, Tags                            |
| `category`                   | Product | Tags / Product Type                             |
| `cost`                       | Variant | **Pricing formula base (wholesale cost)**       |
| `msrp`                       | Variant | Compare At Price (C&B MSRP shown as reference)  |
| `color` / `colorHexValue`    | Variant | Option 1, color swatch                          |
| `size`                       | Variant | Option 2                                        |
| `sku`                        | Variant | SKU -- also used by PromoStandards PO submission |
| `availableQuantity`          | Variant | Inventory                                       |
| `primaryImageURL` - `image6` | Variant | Product images                                  |
| `colorSwatchImageURL`        | Variant | Color swatch (metafield, advanced)              |

> **Note on SKU:** The SKU field is critical for PromoStandards order sync -- SupplyMaster uses the mapped SKU to identify the product in the PO submitted to C&B. Ensure `sku` is mapped to Shopify's Variant SKU field and that the value matches C&B's SKU format exactly. Do not apply a modifier to the SKU field. **CONFIRMED (2026-06-17): SKUs and barcodes imported correctly on test import.**

**Default pricing note:** SupplyMaster's C&B default maps to MSRP. **CONFIRMED (2026-06-17): Test import prices are MSRP.** Override this by pointing Variant Price to the `cost` field with a margin-targeting modifier. **This is the immediate next action.**

**Title prefix requirement (2026-06-17):** All published products on shoptorreypines.com are prefixed with "Torrey Pines" for SEO. Configure in Match Fields -- Title -- Modify:
```
Torrey Pines {{ title }}
```
When AI+ is enabled, upgrade to:
```
Torrey Pines {{ AI_cleanTitle }}
```

**Margin-targeting pricing formula (Variant Price modifier):**

The goal is to set a retail price that achieves a target gross margin from the wholesale cost. The formula below targets a consistent gross margin by cost tier. Adjust the multipliers to match your margin requirements.

```liquid
{% assign p = variant.cost %}
{% if p <= 30 %}{{ p | times: 2.2 | round: 2 }}
{% elsif p <= 70 %}{{ p | times: 1.9 | round: 2 }}
{% elsif p <= 120 %}{{ p | times: 1.7 | round: 2 }}
{% else %}{{ p | times: 1.5 | round: 2 }}
{% endif %}
```

**How to interpret the multipliers:**
- `x 2.2` = `~55% gross margin` (cost is ~45% of retail)
- `x 1.9` = `~47% gross margin`
- `x 1.7` = `~41% gross margin`
- `x 1.5` = `~33% gross margin`

Adjust multipliers to your target margin tier. Always use the **Preview** pane in the Modify editor to verify against real C&B sample data before saving.

**AI Assist for Liquid:** In the Modify editor, click the purple wand icon, describe your target margin in plain English (e.g., "price should yield a 50% gross margin from the cost field"), and SupplyMaster generates the Liquid. Always verify in Preview before saving.

**Compare At Price:** Map `msrp` -- Compare At Price (no modifier). Displays the C&B MSRP as the crossed-out reference price.

**Tags to configure:**
- `category` -- Tags (drives category Smart Collections)
- `vendor` / `brandName` -- Tags and Vendor field (brand filtering)
- `AI_tags` -- Tags (if AI+ enabled -- program tags: Virtue Recycled, Adapt Recycled, etc.)
- `AI_gender` -- Tags (Men's / Women's collections)

**Additional field mappings to configure (from 2026-06-17 test import observations):**
- Weight: `{% if variant.weight == 0 %}0.35{% else %}{{ variant.weight }}{% endif %}` (sets default when supplier reports zero)
- Country of origin: `{{ variant.countryOfOrigin | slice: 0, 2 }}` -- map to `variant.inventoryItem.countryCodeOfOrigin`

**AI+ enrichment:** Enable from Match Fields -- **Enable AI+ Data** -- Load AI+ default mappings -- approve the $99 one-time Shopify charge. Enable after the first test import, compare copy on test styles before committing to the full hero set. AI+ also solves the Shopify product category gap (OBS-006) via AI_shopifyProductCategoryId.

**Reference docs:** *Mapping Supplier Fields to Shopify*, *Customizing Fields with Liquid Formulas*, *AI+ Enriched Product Data*, *Available Supplier Data Fields*

---

### Module 6 -- First Import & Verification
**Goal:** Import test styles, verify every field in Shopify admin, fix any issues, then scale to the full hero set.

**Pre-import checklist:**
- [x] Filter: 2 test styles imported (standard undecorated C&B catalog SKUs -- pipeline verification only)
- [x] Inventory: location mapped; safety buffer = 5
- [ ] Variant Price modifier: margin formula to be configured -- **NEXT ACTION**
- [ ] Title modifier: "Torrey Pines {{ title }}" to be configured -- **NEXT ACTION**
- [ ] Compare At Price: map to `msrp`
- [x] SKU: mapped to Variant SKU (no modifier) -- CONFIRMED correct (OBS-009)
- [ ] Tags: category + vendor to be mapped
- [ ] Publish channel: to be selected when products are ready to go live
- [x] Product status: Active with no channel assigned (equivalent safety to Draft) -- OBS-001/OBS-002
- [x] Order sync: set to Manual (review mode) ✓

**Post-import verification findings (2026-06-17, 2 test products):**

| Field            | Status | Notes |
| ---------------- | ------ | ----- |
| Title            | Needs work | C&B default title only -- "Torrey Pines" prefix not yet configured |
| Description      | Not verified | Supplier copy (AI+ not yet enabled) |
| Price            | Fix required | Showing MSRP -- margin formula not yet configured (OBS-008) |
| Compare At Price | Not mapped | MSRP mapping not yet configured |
| Images           | Imported -- non-decorated | Standard C&B catalog images; pre-decorated SKU images TBD (OBS-004) |
| Variants         | Correct | Color and size options correct (OBS-007) |
| Tags             | Empty | Not yet mapped (OBS-005) |
| SKU              | Correct | Populated on all variants; C&B format confirmed (OBS-009) |
| Vendor           | Correct | (OBS-005) |
| Product Type     | None | Not yet mapped (OBS-005) |
| Category         | None | Requires AI+ to auto-populate (OBS-006) |
| Weight           | Zero | Modifier needed (OBS-010) |
| Country of origin| Blank | Modifier needed (OBS-010) |

**Immediate next steps:**
1. Configure Match Fields -- Variant Price -- Modify with margin formula
2. Configure Match Fields -- Title -- Modify with "Torrey Pines {{ title }}" prefix
3. Configure Compare At Price, Tags, Product Type mappings
4. Re-import the 2 test products and verify pricing and title are correct
5. Confirm pre-decorated Torrey Pines SKU IDs with C&B
6. Rebuild filter using confirmed pre-decorated SKUs
7. Consider enabling AI+ ($99) to solve category, tags, and clean titles in one step

**Scale-up after successful test:**
Edit Filters -- add remaining hero style numbers to the Equal To Any filter -- Import Products -- monitor Sync History -- final verification pass in Shopify admin -- switch Order Sync to **Automatically Fulfill Orders** once PO flow is confirmed correct.

**Reference docs:** *Importing Products to Your Shopify Store*, *Sync History, Errors & Troubleshooting*, *SupplyMaster: Importing Products*, *Syncing Orders with PromoStandards (ACC, SanMar, Cutter & Buck)*

---

### Module 7 -- Autopilot Configuration & Ongoing Management
**Goal:** Enable automatic daily catalog syncing, confirm automatic order submission is running, and establish an ongoing monitoring cadence.

**Auto Sync settings (Edit Supplier -- Automatic Sync):**

| Setting                         | Recommended Value                        | Reason                                                                             |
| ------------------------------- | ---------------------------------------- | ---------------------------------------------------------------------------------- |
| Sync Frequency                  | **Daily** (2:00 AM UTC)                  | Catches new colors, price changes, and inventory updates overnight                 |
| Update Settings                 | **All Fields Except Images**             | Updates pricing/inventory/descriptions without re-downloading all images every day |
| Auto Create Products & Variants | **No New Variants on Existing Products** | New C&B color drops don't auto-appear on the storefront until reviewed             |
| Action on Unavailable Products  | **Archive Products**                     | Discontinued styles hide from storefront automatically                             |

Toggle **Auto Import ON** on the supplier card.

**Order Sync -- switch to fully automatic after verified test:**
Once the Manual-mode test orders confirm the PO flow is working correctly, go to Edit Supplier -- Order Settings and change Order Sync from **Manually Fulfill Orders** to **Automatically Fulfill Orders**. From this point, every qualifying Shopify order automatically generates and submits a PromoStandards PO to C&B with no human intervention required.

**Ongoing monitoring cadence:**
- Check Sync History weekly for the first month -- confirm "Success" status on daily catalog syncs
- Monitor Shopify order fulfillment status -- C&B returns tracking numbers via PromoStandards, which SupplyMaster writes back to the Shopify order
- Repeated "Failed" sync status: check subscription variant limit first, then supplier connection, then contact SupplyMaster support
- Check plan variant count periodically as the hero set expands -- upgrade to Pro ($99/mo, 50,000 variants) if approaching the Basic limit

**Reference docs:** *How Automatic Syncing Works*, *Syncing Orders with PromoStandards (ACC, SanMar, Cutter & Buck)*, *Sync History, Errors & Troubleshooting*

---

### Advanced Features -- Available When Ready

Not needed at launch. Revisit as the integration matures.

**Metafields + Theme Customization**
Map C&B color swatch images (`colorSwatchImageURL`) to a `custom.color_swatch` variant metafield. Display via a Custom Liquid section in the Shopify theme. SupplyMaster documentation includes ready-to-paste Liquid and CSS code.
*Reference: Using Metafields with SupplyMaster, Displaying Supplier Data on Your Shopify Theme*

**Product Mappings (Linking Existing Products)**
If shoptorreypines.com already has C&B products with customized images or club-branded descriptions, use Product Mappings to link them to the live C&B feed for inventory and pricing sync -- without overwriting the custom content.
*Reference: Linking Existing Products to Supplier Inventory*

**Duplicate Supplier (Multiple Pricing Rules)**
Create a second C&B supplier connection (e.g., `Cutter & Buck -- Outerwear -- Pro Shop`) with a margin formula calibrated for the higher-cost outerwear range. Use Duplicate Supplier to copy the first connection, then adjust the style number filter and pricing formula independently.
*Reference: How to Add & Manage Suppliers, Supplier Configuration Reference*

**Variant Splitting (One Product Per Color)**
For hero polos where each color warrants its own product page -- useful for targeted email campaigns -- use the legacy variant splitting feature with Split by Color.
*Reference: Variant Splitting (Legacy Feature)*

---

### Automation Roadmap -- Manual Foundation First, Then Automate

**Guiding principle:** Every workflow in this integration starts as a deliberate, manually executed process. The manual version is the reference point -- it defines what "correct" looks like. Automation is only introduced after the manual version is reliable and understood. Skills are built at each stage as a parallel outcome.

---

**Phase 1 -- What SupplyMaster Automates at Launch (No Additional Work Required)**

These automations are built into SupplyMaster and go live as part of the standard setup:

| Automation                   | What It Does                                                                                   | When It Runs             |
| ---------------------------- | ---------------------------------------------------------------------------------------------- | ------------------------ |
| Catalog sync                 | Fetches C&B feed, updates product data (prices, inventory, descriptions)                       | Daily at 2:00 AM UTC     |
| Pricing recalculation        | Applies Liquid margin formula to every variant on each sync                                    | On every sync            |
| Inventory update             | Writes C&B stock quantities to Shopify inventory                                               | On every sync            |
| Product archiving            | Archives Shopify products when C&B marks them unavailable                                      | On every sync            |
| PromoStandards PO submission | Submits purchase order to C&B when Shopify order is placed (once switched to Automatic mode)   | On each qualifying order |
| Tracking number writeback    | C&B returns tracking data via PromoStandards; SupplyMaster writes it back to the Shopify order | When C&B ships           |

---

**Phase 1 -- What Stays Manual (Build the Foundation)**

These workflows are executed manually during Phase 1. Each one is a skill-building exercise that produces the understanding required before automation is introduced.

| Workflow                 | Manual Process                                                                            | Skill Being Built                                                         |
| ------------------------ | ----------------------------------------------------------------------------------------- | ------------------------------------------------------------------------- |
| Hero style selection     | Browse Catalog -- identify pre-decorated SKUs -- build Equal To Any filter                  | Understanding the C&B catalog structure and SKU format                    |
| Pricing formula          | Write and test Liquid modifier in the Modify editor with Preview                          | Liquid formula syntax; margin calculation logic                           |
| Order sync (initial)     | Review each queued PO in Manual mode before approving                                     | Understanding how SupplyMaster constructs and submits a PromoStandards PO |
| Counter sale fulfillment | NCR CounterPoint transaction -- manual Shopify Admin order entry -- SupplyMaster submits PO | Understanding the full order pipeline from both ends                      |
| Sync health monitoring   | Check Sync History weekly; interpret status codes and error messages                      | Reading SupplyMaster's monitoring tools                                   |
| Field mapping review     | Verify each mapped field in Shopify admin after import                                    | Understanding the full field mapping pipeline                             |

---

**Phase 2 -- Automation Opportunities (Introduce After Phase 1 Is Reliable)**

Once each manual workflow is stable and well-understood, evaluate these automation opportunities in sequence:

**2a. Order Sync -- Switch to Automatic (SupplyMaster)**
After 5-10 manually reviewed POs confirm the flow is correct, switch Order Sync from Manually Fulfill Orders to **Automatically Fulfill Orders**. This is the first and most impactful automation -- eliminates human approval from every sale.
*Skill required: Familiarity with SupplyMaster's PO structure before trusting it to run unsupervised.*

**2b. Sync Failure Notifications (Zapier)**
SupplyMaster provides no native alerting when a daily sync fails. Build a Zapier automation that monitors Shopify for expected inventory update patterns and sends an alert if the daily sync appears to have not run. Alternatively, a simple scheduled Zapier check against the Sync History could serve as an early warning system.
*Skill required: Basic Zapier workflow construction (already proven with the voicemail transcription automation).*

**2c. Shopify Flow -- Auto-Tagging and Collection Rules**
As the C&B catalog grows, use Shopify Flow to automatically tag new imported products (e.g., by vendor, price tier, or category) and assign them to Smart Collections -- eliminating manual collection maintenance.
Example: When a product is created with vendor "Cutter & Buck" and a tag containing "Virtue Recycled," Flow automatically adds it to the "Virtue Recycled Program" collection.
*Skill required: Shopify Flow builder (visual, no-code interface; manageable learning curve).*

**2d. Counter Sale Workflow -- Standardized Template and Staff Procedure**
Before automating the NCR CounterPoint -- Shopify Admin bridge, standardize the manual process into a written procedure with a Shopify Admin order template (saved draft with pre-filled C&B product fields). Reduce the friction of the double-entry step. Evaluate whether a formal bridge (Zapier or a lightweight CounterPoint -- Shopify connector) is worth the investment once the volume of counter sales is known.
*Skill required: Shopify Admin order draft configuration; eventually Zapier or API-level connector evaluation.*

**2e. Inventory Threshold Alerts (Shopify Flow or Zapier)**
Set up automated alerts when a C&B pre-decorated SKU's inventory in Shopify drops below a threshold (e.g., 5 units). Provides early warning to check C&B availability before a customer tries to order a style that's nearly out of stock.
*Skill required: Shopify Flow (inventory trigger) or Zapier (Shopify inventory webhook).*

**2f. Sync History Reporting (Zapier + Grok)**
Extend the existing Grok-based reporting approach to include a weekly SupplyMaster sync summary -- variant counts updated, products archived, errors encountered. Consistent with the approach used for the PDF summarization workflow that replaced the proprietary software.
*Skill required: Zapier data extraction + Grok prompt engineering (existing skills).*

---

**Skills Development Log**

Track skills built as each phase is completed:

| Skill                                                       | Status      | Phase    |
| ----------------------------------------------------------- | ----------- | -------- |
| C&B catalog navigation and pre-decorated SKU identification | Not started | Phase 1  |
| SupplyMaster supplier setup and configuration               | In Progress | Phase 1  |
| Liquid formula writing (margin pricing)                     | Not started | Phase 1  |
| SupplyMaster field mapping                                  | Not started | Phase 1  |
| PromoStandards PO structure and review                      | Not started | Phase 1  |
| Shopify Admin manual order creation                         | Not started | Phase 1  |
| SupplyMaster Sync History interpretation                    | Not started | Phase 1  |
| SupplyMaster Order Sync (Automatic mode)                    | Not started | Phase 2a |
| Zapier webhook / monitoring workflows                       | Not started | Phase 2b |
| Shopify Flow builder                                        | Not started | Phase 2c |
| Shopify Flow inventory triggers                             | Not started | Phase 2e |

---

### Current Status & Immediate Next Action

**Status:** Module 3 complete. Module 6 in progress. SupplyMaster installed on shoptorreypines.com. C&B supplier connection configured with PromoStandards credentials. 2 test products successfully imported using standard undecorated C&B catalog SKUs (pipeline verification). Field mapping and pricing formula not yet configured.

**What the test import confirmed (2026-06-17):**
- Import pipeline works end-to-end
- SKUs and barcodes import correctly (critical for PromoStandards PO)
- Color and size variants correct
- Vendor populates correctly
- Default price is MSRP (pricing formula required before go-live)
- Products import Active with no channel assigned (safe -- not visible to storefront)
- Title, tags, product type, category, weight, country of origin all need field mapping

**Immediate next actions (in priority order):**
1. **Configure margin pricing formula** -- Match Fields -- Variant Price -- Modify -- enter the tiered Liquid formula (Module 5). Preview against real C&B data before saving.
2. **Configure title prefix** -- Match Fields -- Title -- Modify -- enter `Torrey Pines {{ title }}`.
3. **Configure Compare At Price** -- map to `msrp` (no modifier).
4. **Configure Tags** -- map category + vendor fields.
5. **Re-import the 2 test products** -- verify price, title, and tags are now correct.
6. **Confirm pre-decorated Torrey Pines SKU IDs** with C&B -- these are required for the full hero import.
7. **Consider AI+** ($99 one-time) -- solves category, clean titles, program tags, and SEO fields in one step. Best activated before the full hero import.

**Note on approval threshold:** At $29/mo (Basic plan), this is well under the ~$1,000 threshold. AI+ at $99 one-time is also under the threshold. Both can proceed within the e-commerce domain without a formal approval process.

**Decoration model confirmed:** The standing program is Model A -- C&B holds dedicated Torrey Pines pre-decorated SKUs. SupplyMaster will list and auto-order those SKUs. The test import used standard catalog SKUs for pipeline verification only -- the full hero import requires the pre-decorated SKU IDs.
