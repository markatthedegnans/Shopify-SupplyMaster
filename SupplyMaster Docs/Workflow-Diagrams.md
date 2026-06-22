# SupplyMaster Workflow Diagrams

> **Project:** Shopify SupplyMaster x Cutter and Buck -- The Golf Shop at Torrey Pines
> **Purpose:** Text-based workflow diagrams for coworker briefing on app setup, product import, and order PO generation.
> **Created:** 2026-06-18

---

## DIAGRAM 1 -- SupplyMaster and Shopify Initial Setup

    SUPPLYMASTER + SHOPIFY: INITIAL SETUP
    =======================================

    [Shopify Admin]
         |
         v
    Install SupplyMaster App
         |
         v
    Select Subscription Plan
    (Basic 29/mo, Pro 99/mo, Plus 279/mo, Premium 499/mo)
    5-day free trial on all plans
         |
         v
    Add Supplier
         |
         +-- Select supplier (e.g., Cutter and Buck)
         +-- Enter API credentials
         +-- Click Test Credentials -> confirm green checkmark
         |
         v
    Configure INVENTORY SETTINGS
         |
         +-- Assign Shopify location(s) -> Import Supplier Inventory
         +-- OR assign specific supplier warehouse(s)
         |
         v
    Configure PRODUCT SETTINGS
         |
         +-- Sales Channels: select Shopify channels products publish to
         |   (e.g., Online Store, POS)
         |   [NOTE] Torrey Pines current: NO channels selected
         |          Safe default -- products not visible on storefront
         |
         +-- Match Fields (Field Mapping):
             +-- Title       -> supplier title  [optional modifier]
             +-- Price       -> supplier price  [optional formula]
             +-- SKU         -> supplier SKU    [NO modifier -- required for PO]
             +-- Description -> supplier desc
             +-- Images      -> supplier images
             +-- Weight      -> supplier weight [optional default formula]
             +-- Tags/Type   -> requires explicit mapping
         |
         v
    Click Save Supplier
         |
         v
    Supplier connection active [DONE]

---

## DIAGRAM 2 -- Product Selection and Import

    PRODUCT SELECTION AND IMPORT WORKFLOW
    ======================================

    [Saved Supplier in SupplyMaster]
         |
         v
    Open View and Import Products
         |
         v
    FILTER PRODUCTS
    ----------------
    Product Filters:      Variant Filters:
    +-- Brand Name        +-- Color Name
    +-- Style Number      +-- Size
    +-- Category          +-- SKU
    (OR use Browse Catalog to search by title/brand)
         |
         v
    Review filtered product list
         |
         v
    Click Import Products
         |
         v
    SupplyMaster runs import (Shopify bulk operation):
         +-- 1. Fetches latest data from supplier
         +-- 2. Applies product and variant filters
         +-- 3. Creates new / updates existing Shopify products
         +-- 4. Populates fields per Match Fields configuration
         +-- 5. Sets inventory levels at configured locations
         +-- 6. Publishes to selected sales channels
         |
         v
    Monitor in Sync History:
    [Queued] -> [Running] -> [Success / Error]
    (10 min to 1 hour depending on product count)
         |
         v
    Verify in Shopify Admin:
         +-- Titles, prices, images, variants   [OK]
         +-- SKUs and barcodes                  [OK]
         +-- Inventory quantities per location  [OK]
         |
         v
    OPTIONAL: AUTO-SYNC
    --------------------
    Toggle Auto Import on supplier card
    OR configure Automatic Sync tab:
         +-- Frequency: Daily or Every 6 Hours
         +-- What updates: price, inventory, etc.
         +-- New/unavailable product behavior

---

## DIAGRAM 3 -- C and B Order PO Generation (PromoStandards)

    C AND B ORDER PO GENERATION -- PROMOSTANDARDS FLOW
    ====================================================

    PRE-SETUP (one-time):
    ---------------------
    SupplyMaster -> Edit Supplier -> Order Settings
         |
         +-- Order Sync Mode (choose one):
         |    +-- Automatically Fulfill Orders -> places PO every ~30 min
         |    +-- Fulfill at Scheduled Time    -> places PO once/day at set time
         |    +-- Manually Fulfill Orders      -> order held in App Orders
         |    |                                   until you click Submit Now
         |    +-- Disabled                     -> no PO automation;
         |                                        place orders outside SupplyMaster
         |
         +-- Dropship PO Number: e.g., {{ shopifyOrderNumber }}-SHOPIFY
         |
         +-- PromoStandards Credentials:
         |    [!] DIFFERENT from product sync credentials
         |    Contact: CBEDI@cutterbuck.com to request API access
         |
         +-- Shipping Carrier: UPS (default), FedEx, FDX, etc.
         +-- Shipping Service: GRND PREPAID (default)
         +-- Blind Ship: YES (default -- ships under your branding)
         |
         v
    Click Save Supplier

    ORDER FLOW (per transaction):
    -----------------------------

    [Customer places order on shoptorreypines.com]
         |
         v
    Shopify receives order
         |
         v
    SupplyMaster checks: do line items match C and B supplier SKUs?
         |
         +-- NO MATCH -> order skipped
         |              (different supplier or manual product -- expected)
         |
         +-- MATCH -->
                      Order appears in App Orders tab
                      Status: QUEUED / PENDING
                           |
                           v
                      Sync Mode?
                      /          \
                AUTO/SCHED      MANUAL
                    |               |
                    v               v
              Placed auto      Click Submit Now
              per schedule
                    |               |
                    +-------+-------+
                            |
                            v
              PO submitted to C and B via PromoStandards API
                            |
                            v
              C and B processes and ships directly to customer
              (Blind Ship = YES -- ships under Torrey Pines branding)
                            |
                            v
              Tracking number synced back into SupplyMaster / Shopify

---

## DIAGRAM 4 -- Auto Sync and Ongoing Monitoring

    AUTO SYNC AND ONGOING MONITORING
    ==================================

    ONE-TIME SETUP:
    ---------------
    SupplyMaster -> Edit Supplier -> Automatic Sync tab
         |
         +-- Sync Frequency:
         |    +-- Daily at 2:00 AM UTC  [RECOMMENDED for Torrey Pines]
         |    +-- Every 6 Hours
         |
         +-- Update Settings (what fields refresh on each sync):
         |    +-- All Fields            -> full update including images
         |    +-- All Except Images     -> [RECOMMENDED] protects customized content
         |    +-- Variants Only         -> price and inventory only
         |    +-- Inventory Only        -> fastest; stock quantities only
         |
         +-- Auto Create Products and Variants:
         |    +-- New Products and Variants     -> new C and B styles auto-appear
         |    +-- No New Variants on Existing   -> [RECOMMENDED] new colors reviewed first
         |    +-- No New Products or Variants   -> locked catalog; no additions
         |
         +-- Action on Unavailable Products:
              +-- Archive Products   -> [RECOMMENDED] discontinued styles hide automatically
              +-- Delete Products    -> permanent removal
              +-- Do Nothing         -> stays visible even if C and B discontinues
         |
         v
    Toggle AUTO IMPORT ON on supplier card
         |
         v
    Auto Sync is now active [DONE]

    DAILY SYNC CYCLE (automatic):
    ------------------------------

    [2:00 AM UTC -- SupplyMaster triggers sync]
         |
         v
    Fetch latest C and B feed
         |
         v
    Apply filters (only hero style numbers pass through)
         |
         v
    For each matching product/variant:
         +-- Recalculate price using Liquid margin formula
         +-- Update inventory quantities
         +-- Update descriptions, weight, country of origin
         +-- Check for new colors or sizes (per variant creation rule)
         +-- Archive if C and B marks style unavailable
         |
         v
    Sync History updated:
    [Queued] -> [Running] -> [Success / Error]
         |
         v
    Done -- Shopify products reflect latest C and B data

    MONITORING CADENCE:
    --------------------
    Weekly (first month):
         +-- SupplyMaster -> Sync History
         +-- Confirm Status = Success on each daily run
         +-- Check row counts -- unexpected zero could signal a connection issue
         +-- Review any Error entries -- click for detail

    If Status = Failed:
         +-- Check variant count vs. plan limit first (Basic = 5,000 variants)
         +-- Verify C and B connection still active
         +-- Contact SupplyMaster support if issue persists

---

## DIAGRAM 5 -- Counter Sale (Walk-In / In-Store Order)

    COUNTER SALE WORKFLOW -- WALK-IN CUSTOMER AT THE GOLF SHOP
    ============================================================

    CONTEXT:
    ---------
    When a walk-in customer purchases a pre-decorated C and B item in person
    at the Golf Shop, the Shopify order IS the base transaction record.
    SupplyMaster processes the C and B line items exactly as it would any
    online order -- detecting the SKU match, submitting the PromoStandards PO
    to C and B, and writing the tracking number back to Shopify when C and B
    ships.

    The NCR CounterPoint in-store POS system is updated from the Shopify
    invoice AFTER the SupplyMaster workflow is complete. That step is a
    separate in-store double-entry workflow and is entirely outside the scope
    of this document.

    CURRENT PROCESS (Manual -- Phase 1):
    --------------------------------------

    [Walk-in customer selects C and B item at the Golf Shop counter]
         |
         v
    Staff opens Shopify Admin (desktop or iPad)
         |
         v
    Create order in Shopify:
         +-- Add customer (search by name/email, or use Guest)
         +-- Add C and B product variant (search by title or SKU)
         +-- Set quantity
         +-- Confirm price reflects the margin formula
         +-- Enter customer shipping address
              (C and B ships direct to customer -- blind ship)
         +-- Collect payment -> mark order as Paid in Shopify
         |
         v
    Shopify order placed -- Shopify is the base transaction record
         |
         v
    SupplyMaster detects C and B SKU match on the order line items
         |
         v
    [SupplyMaster workflow takes over -- see Diagram 3 and Diagram 7]
         |
         v
    Manual mode: go to App Orders tab -> click Submit Now
    (once Phase 2a is active, this step is automatic)
         |
         v
    PO submitted to C and B via PromoStandards API
         |
         v
    C and B processes and ships pre-decorated item directly to customer
    (Blind Ship -- ships under Torrey Pines branding)
         |
         v
    Tracking number synced back into Shopify order automatically
         |
         v
    Customer receives shipping notification email with tracking link
         |
         v
    [SupplyMaster workflow complete]
         |
         v
    [SEPARATE WORKFLOW -- outside scope of this document]
    NCR CounterPoint updated from the Shopify invoice

    PHASE 2 NOTE (Phase 2a):
    ------------------------
    Once Order Sync is switched to Automatically Fulfill Orders,
    the PO submission step requires no manual click -- SupplyMaster
    sends the PO to C and B automatically within ~30 minutes of the
    Shopify order being placed.

---

## QUICK REFERENCE -- Key Settings Summary

    TORREY PINES -- CURRENT CONFIGURATION SNAPSHOT
    =================================================

    Supplier Name:         Cutter and Buck -- Hero Styles -- Pro Shop
    Plan:                  Basic (29/mo) -- up to 5,000 variants
    Order Sync Mode:       Manually Fulfill Orders  [Phase 1 -- change to Auto after test]
    Blind Ship:            YES
    Shipping Carrier:      UPS / GRND PREPAID
    Safety Stock Buffer:   5 units
    Sales Channels:        NONE selected  [products not visible on storefront until assigned]
    Auto Sync:             Daily at 2:00 AM UTC (when enabled)
    Update Settings:       All Except Images  [recommended]
    Variant Creation:      No New Variants on Existing Products  [recommended]
    Unavailable Products:  Archive Products  [recommended]

    FIELD MAPPING STATUS (as of 2026-06-19):
    -----------------------------------------
    Title          ->  Needs modifier: Torrey Pines {{ title }}
    Variant Price  ->  Needs modifier: tiered margin formula (see Module 5)
    Compare At     ->  Needs mapping:  msrp field
    SKU            ->  CORRECT -- no modifier applied
    Inventory      ->  CORRECT -- mapped to store location
    Tags           ->  Not yet mapped
    Product Type   ->  Not yet mapped
    Weight         ->  Needs modifier: default 0.35 when zero
    Country Code   ->  Needs modifier: 2-letter ISO slice


---

## DIAGRAM 6 -- Field Mapping Deep Dive

    FIELD MAPPING PIPELINE (HOW MATCH FIELDS WORKS)
    =================================================

    CONCEPT:
    ---------
    SupplyMaster reads raw data from the C and B supplier feed and writes it
    into Shopify product and variant fields. Match Fields is where each mapping
    rule is defined. Every rule has three parts:

    [C and B Source Field]
              |
              v
    [Optional Liquid Modifier]    <- math, text, conditionals, or none
              |
              v
    [Shopify Destination Field]

    If no modifier: raw supplier value is written directly.
    If modifier applied: Liquid formula transforms the value before writing.

    HOW TO ACCESS:
    ---------------
    SupplyMaster -> Edit Supplier -> Product Settings -> Match Fields tab

    PRODUCT-LEVEL MAPPINGS:
    ------------------------

    C and B Source         Modifier                          Shopify Destination
    -----------------------------------------------------------------------
    title               -> Torrey Pines {{ title }}       -> Title
                           (plain text prepend)
    descriptionHtml     -> none (raw supplier copy)        -> Description (HTML)
                           OR AI_description (if AI+)
    vendor / brandName  -> none                            -> Vendor
    category            -> none                            -> Tags (drives Smart Collections)
    AI_tags             -> none (requires AI+)             -> Tags (program tags)
    AI_gender           -> none (requires AI+)             -> Tags (Men's / Women's)

    VARIANT-LEVEL MAPPINGS:
    ------------------------

    C and B Source         Modifier                          Shopify Destination
    -----------------------------------------------------------------------
    sku                 -> NONE -- do not modify             -> Variant SKU
                           [!] SKU must match C and B format exactly
                               for PromoStandards PO to route correctly
    cost                -> Tiered margin formula (below)     -> Variant Price
    msrp                -> none                              -> Compare At Price
    availableQuantity   -> none                              -> Inventory Quantity
    color               -> none                              -> Option 1 (Color)
    size                -> none                              -> Option 2 (Size)
    weight              -> Default formula (below)           -> Variant Weight
    countryOfOrigin     -> ISO slice formula (below)         -> Country Code of Origin
    primaryImageURL     -> none                              -> Product Images
    colorSwatchImageURL -> none (or metafield mapping)       -> Color Swatch (advanced)

    MODIFIER EXAMPLES:
    -------------------

    Title prefix:
         Torrey Pines {{ title }}
         Output example: Torrey Pines CB Drytec Polo

    Tiered margin pricing (Variant Price modifier):
         {% assign p = variant.cost %}
         {% if p <= 30 %}{{ p | times: 2.2 | round: 2 }}
         {% elsif p <= 70 %}{{ p | times: 1.9 | round: 2 }}
         {% elsif p <= 120 %}{{ p | times: 1.7 | round: 2 }}
         {% else %}{{ p | times: 1.5 | round: 2 }}
         {% endif %}
         Example: cost = $55.00 -> price = $104.50 (~47% gross margin)

    Weight default when supplier reports zero:
         {% if variant.weight == 0 %}0.35{% else %}{{ variant.weight }}{% endif %}
         Output: 0.35 lbs if zero reported; otherwise uses actual weight

    Country of origin -- 2-letter ISO code:
         {{ variant.countryOfOrigin | slice: 0, 2 }}
         Output example: VN from VNM or Vietnam

    AI+ FIELD DEFAULTS (requires $99 one-time activation):
    -------------------------------------------------------
    When AI+ is enabled, click Add AI+ Field Defaults in Match Fields.
    SupplyMaster pre-loads mappings for:
         AI_cleanTitle            -> Title (replaces raw supplier title)
         AI_description           -> Description (SEO-optimized copy)
         AI_tags                  -> Tags (program, material, fit tags)
         AI_gender                -> Tags (Men's / Women's)
         AI_shopifyProductCategoryId -> Shopify Category (standard taxonomy)

    MODIFIER EDITOR -- HOW TO USE:
    --------------------------------
    1. In Match Fields, click the pencil icon next to any source field
    2. The Modify editor opens -- enter Liquid code in the text area
    3. Click Preview pane -- SupplyMaster runs the formula against real
       C and B sample data and shows the output value
    4. Verify the output is correct before clicking Save
    5. Purple wand icon: describe target in plain English -- SupplyMaster
       generates the Liquid code for you (AI Assist)

    IMPORTANT RULES:
    -----------------
    [!] Do NOT apply a modifier to SKU -- raw SKU must pass through unchanged
    [!] Always verify pricing modifier in Preview before saving
    [!] Modifiers apply on every import AND every auto sync
    [!] Fields not mapped here will not be populated in Shopify


---

## DIAGRAM 7 -- PromoStandards Order Flow (Detailed)

    PROMOSTANDARDS ORDER FLOW -- DETAILED
    ========================================

    WHAT IS PROMOSTANDARDS?
    ------------------------
    PromoStandards is an industry-wide API protocol used by promotional
    products and wholesale apparel suppliers (including Cutter and Buck,
    SanMar, and ACC) to accept purchase orders electronically and return
    order status and tracking data -- without email, phone, or manual entry.

    SupplyMaster acts as the bridge:
         Shopify order  ->  SupplyMaster  ->  PromoStandards API  ->  C and B

    TWO SEPARATE CREDENTIAL SETS:
    ------------------------------
    [1] Catalog / Product Sync Credentials
         -- Used to fetch the C and B product feed (pricing, inventory, images)
         -- NOT required for Cutter and Buck -- catalog connects automatically
         -- Do not confuse with order credentials

    [2] PromoStandards Order Sync Credentials
         -- DIFFERENT set of credentials -- required specifically for PO submission
         -- Username and Password provided by C and B
         -- Contact: CBEDI@cutterbuck.com to request API access
         -- Entered in Edit Supplier -> Order Settings
         -- [!] Without these, SupplyMaster CANNOT submit POs to C and B

    -----------------------------------------------------------------------
    STEP 1 -- SUPPLYMASTER SKU MATCH CHECK
    -----------------------------------------------------------------------

    When a Shopify order is placed, SupplyMaster scans every line item:

    [Shopify Order Received]
         |
         v
    For each line item in the order:
         |
         +-- Read the Variant SKU from the Shopify product
         |
         v
    Does this SKU exist in the C and B supplier connection?
         |
         +-- NO MATCH:
         |    SKU belongs to a different supplier, a manual product,
         |    or a Torrey Pines branded item (not dropshipped via C and B)
         |    -> Line item is SKIPPED -- no PO generated for this item
         |    -> Other non-C and B items in the same order are unaffected
         |
         +-- MATCH:
              SKU found in C and B supplier feed
              -> Line item is QUEUED for PO submission
              -> Appears in SupplyMaster App Orders tab
              -> Status: PENDING

    [!] WHY SKU ACCURACY IS CRITICAL:
    The MATCH check uses the exact SKU string stored on the Shopify variant.
    If the SKU was modified during import (e.g., a prefix was added via a
    Liquid modifier in Match Fields), the string will NOT match the C and B
    feed SKU and the order will be skipped silently.
    -> Always map SKU with NO modifier applied.
    -> Confirmed correct on test import (OBS-009).

    -----------------------------------------------------------------------
    STEP 2 -- PO CONSTRUCTION AND SUBMISSION
    -----------------------------------------------------------------------

    Once a line item is matched and queued:

    [Order Status: PENDING in App Orders]
         |
         v
    Sync Mode check:
         |
         +-- MANUALLY FULFILL ORDERS:
         |    Order waits in App Orders tab
         |    Staff reviews the queued PO
         |    Click Submit Now to send
         |    [!] Torrey Pines current mode -- Phase 1 review period
         |
         +-- AUTOMATICALLY FULFILL ORDERS:
         |    SupplyMaster sends PO automatically every ~30 minutes
         |    No human action required
         |    [Switch to this after 5-10 successful manual POs confirmed]
         |
         +-- FULFILL AT SCHEDULED TIME:
              PO batch sent once per day at a configured time
         |
         v
    SupplyMaster constructs the PromoStandards PO:

         PO CONTENTS:
         +-- PO Number:        e.g., 12345-SHOPIFY
         |                     (from Dropship PO Number template)
         +-- Line Items:       C and B SKU + quantity per item
         +-- Ship-To Address:  Customer shipping address from Shopify order
         +-- Shipping Carrier: UPS (configured in Order Settings)
         +-- Shipping Service: GRND PREPAID (configured in Order Settings)
         +-- Blind Ship Flag:  YES -- C and B ships under Torrey Pines branding
         |                     (no C and B branding on packing slip)
         +-- Decoration:       NONE -- pre-decorated SKUs already carry the
                               Torrey Pines embroidery at C and B; no
                               decoration instructions needed at order time
                               (Model A standing program)
         |
         v
    PO transmitted to C and B via PromoStandards Purchase Order API (HTTPS)
         |
         v
    C and B acknowledges receipt -- PO Status: CONFIRMED
         |
         v
    Status updated in SupplyMaster App Orders tab:
    PENDING -> SUBMITTED -> CONFIRMED

    -----------------------------------------------------------------------
    STEP 3 -- FULFILLMENT AND TRACKING WRITEBACK
    -----------------------------------------------------------------------

    After C and B confirms and ships the order:

    [C and B picks, packs, and ships the pre-decorated item]
         |
         v
    C and B generates tracking number (UPS GRND PREPAID)
         |
         v
    C and B posts shipment status via PromoStandards OrderStatus API
         |
         v
    SupplyMaster polls the PromoStandards OrderStatus endpoint periodically
         |
         v
    Tracking number and carrier info retrieved
         |
         v
    SupplyMaster writes tracking data back to Shopify:
         +-- Fulfillment record created on the Shopify order
         +-- Carrier: UPS
         +-- Tracking number populated
         +-- Fulfillment status: FULFILLED
         |
         v
    Shopify triggers automatic shipping notification email to customer
    (includes UPS tracking link)
         |
         v
    Order complete -- no manual tracking entry required

    ERROR SCENARIOS:
    -----------------
    PO REJECTED by C and B:
         -- SKU not found in C and B system (wrong SKU format or non-existent)
         -- Insufficient inventory at C and B
         -- PromoStandards credentials expired or invalid
         -> Check App Orders for error detail
         -> Verify SKU against C and B catalog
         -> Contact CBEDI@cutterbuck.com if credentials issue

    TRACKING NOT RETURNING:
         -- C and B has not yet shipped (normal -- allow processing time)
         -- PromoStandards credentials need refresh
         -> Check App Orders status; allow 24-48 hours before escalating

    FULL ORDER FLOW SUMMARY:
    -------------------------

    Customer order (Shopify)
         |
         v
    SupplyMaster SKU MATCH check
         |
         +-- No match -> skipped (non-C and B item)
         +-- Match   -> QUEUED in App Orders
                            |
                            v
                       Manual: click Submit Now
                       Auto:   sent every ~30 min
                            |
                            v
                       PO transmitted via PromoStandards API
                            |
                            v
                       C and B confirms -> status: CONFIRMED
                            |
                            v
                       C and B ships (blind, pre-decorated)
                            |
                            v
                       PromoStandards OrderStatus returns tracking
                            |
                            v
                       SupplyMaster writes tracking to Shopify order
                            |
                            v
                       Customer receives shipping email with tracking link
                            |
                            v
                       Order FULFILLED -- no manual steps required

