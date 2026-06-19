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

## DIAGRAM 5 -- Counter Sale (In-Store to Shopify Order) Workflow

    COUNTER SALE WORKFLOW -- IN-STORE TO SHOPIFY ORDER
    ====================================================

    CONTEXT:
    ---------
    When a customer purchases a C and B pre-decorated item in person at the
    Golf Shop, the sale is rung through NCR CounterPoint (POS). Because C and B
    ships direct (blind drop-ship), a corresponding Shopify order must be created
    so SupplyMaster can submit the PromoStandards PO to C and B.

    CURRENT PROCESS (Manual -- Phase 1):
    --------------------------------------

    [Customer purchases at counter -- NCR CounterPoint]
         |
         v
    Ring sale in CounterPoint as normal
         |
         v
    Open Shopify Admin on desktop/iPad
         |
         v
    Create Draft Order in Shopify Admin:
         +-- Add customer (or Guest)
         +-- Add C and B product variant (by SKU or title search)
         +-- Set quantity
         +-- Set price to match CounterPoint transaction
         +-- Add note: Counter sale -- CounterPoint [transaction number]
         |
         v
    Mark order as Paid (payment collected in-store via CounterPoint)
         |
         v
    Order appears in SupplyMaster App Orders tab
         |
         v
    Submit PO to C and B (Manual mode: click Submit Now)
         |
         v
    C and B ships pre-decorated item directly to customer
    (Blind Ship -- ships under Torrey Pines branding)
         |
         v
    Tracking number synced back into Shopify order
         |
         v
    Notify customer of shipment (Shopify order notification email)

    NOTE: Order Sync must be set to Manually Fulfill Orders during Phase 1.
    Switch to Automatically Fulfill Orders (Phase 2a) only after 5-10 manual
    POs confirm the flow is correct end-to-end.

    FUTURE STATE (Phase 2d -- after standardized procedure):
    ---------------------------------------------------------
    Evaluate a CounterPoint -> Shopify connector or Zapier bridge to reduce
    the manual double-entry step. Standardize a Shopify draft order template
    with pre-filled C and B product fields before automating.

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

