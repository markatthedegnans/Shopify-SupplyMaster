# SupplyMaster Observations Log

> **Project:** Shopify SupplyMaster x Cutter & Buck -- The Golf Shop at Torrey Pines
> **Purpose:** Real-time observations captured during app exploration, to be used in building an employee SOP for shoptorreypines.com.

---

## Entry Format

Each entry follows this structure:

### OBS-[NNN] -- [Short Title]
- **Date:** YYYY-MM-DD
- **Category:** [Catalog | Filters | Field Mapping | Order Sync | Inventory | Sync | AI+ | UI/UX | Pricing | General]
- **Type:** [Observation | Question | Decision]
- **Details:** Full text of the observation as submitted.
- **Context:** Relevant notes pulled from SupplyMaster documentation or project context.

---

## Observations

*(No entries yet -- log is ready for use.)*

---

### OBS-001 -- Imported products arrive in Shopify with Active status
- **Date:** 2026-06-17
- **Category:** UI/UX
- **Type:** Observation
- **Details:** The imported products arrived in Shopify's Products list with Active status, not Draft.
- **Context:** SupplyMaster's default product status is Active unless explicitly changed to Draft in Product Settings during supplier setup. The Module 3 plan called for importing as Draft; however, because no Shopify sales channels were selected in SupplyMaster's Product Settings, Active-status products are still not visible to any storefront. The no-channel default is effectively a safer guard than Draft status alone.

---

### OBS-002 -- No Shopify channels selected in SupplyMaster Product Settings
- **Date:** 2026-06-17
- **Category:** UI/UX
- **Type:** Observation
- **Details:** No Shopify channels are selected under SupplyMaster's Product Settings, so there is no risk of raw imported products being exposed on the storefront prior to review and editing.
- **Context:** A Shopify product set to Active with no assigned sales channels is not visible to customers on any channel (Online Store, POS, etc.). This is SupplyMaster's default behavior and acts as a built-in safety net for raw imports. No manual channel assignment should be made until products are reviewed and ready to publish.

---

### OBS-003 -- Product titles need a "Torrey Pines" prefix; investigating SupplyMaster AI capabilities
- **Date:** 2026-06-17
- **Category:** Field Mapping
- **Type:** Question
- **Details:** After importing raw products, the title needs editing. All published products on shoptorreypines.com are prefixed with "Torrey Pines" for SEO optimization. Raw imports only have C&B's default product title. Investigating whether SupplyMaster AI functions can modify the imported title automatically.
- **Context:** Two approaches confirmed available: (1) Without AI+ -- in Match Fields, map Title with a Modify formula: "Torrey Pines {{ title }}" to prepend the prefix on every import and sync. This is available immediately at no additional cost. (2) With AI+ ($99 one-time) -- map Title to AI_cleanTitle (which strips trademark symbols and formatting artifacts) with the same prepend: "Torrey Pines {{ AI_cleanTitle }}". Recommendation: implement the basic prepend modifier now; upgrade to AI_cleanTitle source when AI+ is enabled. Reference: Customizing Fields with Liquid Formulas.

---

### OBS-004 -- All imported images are non-decorated (standard C&B catalog images)
- **Date:** 2026-06-17
- **Category:** Catalog
- **Type:** Observation
- **Details:** All of the imported product images are non-decorated -- standard C&B wholesale catalog photography with no Torrey Pines embroidery or decoration visible.
- **Context:** Expected for standard undecorated C&B catalog SKUs. The test import used standard undecorated product IDs. Pre-decorated Torrey Pines SKUs (Model A standing program) are separate SKUs held by C&B and may include different image assets. Confirming the correct pre-decorated SKU IDs before the full hero import is critical -- importing standard blank-catalog SKUs would result in POs for undecorated goods. See Module 4 note on SKU format.

---

### OBS-005 -- Product organization fields empty: no type, no collections, no tags; Vendor correct
- **Date:** 2026-06-17
- **Category:** Field Mapping
- **Type:** Observation
- **Details:** In Shopify's product definition page, Product Organization type is "None", no collections are identified, and no tags are populated. Vendor is correctly identified.
- **Context:** Expected with default SupplyMaster field mapping. Product Type, Collections, and Tags all require explicit Match Field configuration (Module 5). Tags are the primary driver of Smart Collections -- once category, vendor, and AI tags are mapped in Match Fields, Smart Collections self-populate automatically on re-import. Vendor populating correctly confirms the vendor field mapping is working.

---

### OBS-006 -- Shopify product category not identified
- **Date:** 2026-06-17
- **Category:** Field Mapping
- **Type:** Observation
- **Details:** The Shopify product category field has not been identified/populated on the imported products.
- **Context:** Shopify's standard taxonomy category requires the AI Shopify Product Category ID field from SupplyMaster's AI+ enrichment to populate automatically. Without AI+, this field must be set manually per product or left blank. Enabling AI+ ($99 one-time for C&B) provides the AI_shopifyProductCategoryId field, which maps directly to Shopify's Category field via the Add AI+ Field Defaults button in Match Fields.

---

### OBS-007 -- Color and size variants appear correct
- **Date:** 2026-06-17
- **Category:** Catalog
- **Type:** Observation
- **Details:** Color and size variants on the imported products appear to be correct.
- **Context:** Positive confirmation that SupplyMaster's variant mapping for C&B color and size options is functioning correctly out of the box. No modifier needed for variant options. Inventory quantities should also be verified per variant.

---

### OBS-008 -- Imported price appears to be MSRP (not margin-targeted)
- **Date:** 2026-06-17
- **Category:** Pricing
- **Type:** Observation
- **Details:** The imported product price looks to be MSRP rather than a margin-targeted retail price.
- **Context:** Expected -- the Project Overview (Module 5) notes: "SupplyMaster's C&B default maps to MSRP." The margin-targeting Liquid formula must be configured in Match Fields (Variant Price → Modify) before the full hero import. The pricing formula targets gross margin by cost tier. This is the next critical configuration step. Products must not go live at MSRP -- re-import after formula is configured.

---

### OBS-009 -- C&B SKUs and barcodes were imported correctly
- **Date:** 2026-06-17
- **Category:** Field Mapping
- **Type:** Observation
- **Details:** C&B's SKUs and barcodes were imported and populated on the Shopify product variants.
- **Context:** Critical positive confirmation. The SKU field is required for PromoStandards order sync -- SupplyMaster uses the mapped SKU to identify the product in the PO submitted to C&B. SKU must match C&B's format exactly and must not have a modifier applied. Barcodes populating is a bonus. Verify that SKU values match the expected C&B format before enabling order sync.

---

### OBS-010 -- Package set to Store default; weight is zero; Country of origin is blank
- **Date:** 2026-06-17
- **Category:** Field Mapping
- **Type:** Observation
- **Details:** Package dimension is set to Store default, weight is zero, and Country of origin is blank on the imported products.
- **Context:** All three are fixable via Match Field modifiers. Weight zero: map variant weight field with modifier "{% if variant.weight == 0 %}0.35{% else %}{{ variant.weight }}{% endif %}" to set a default when supplier reports zero. Country of origin: map variant.countryOfOrigin with modifier "{{ variant.countryOfOrigin | slice: 0, 2 }}" to variant.inventoryItem.countryCodeOfOrigin (2-letter ISO code). These are lower priority than pricing formula and title prefix -- address in Module 5 field mapping pass.
