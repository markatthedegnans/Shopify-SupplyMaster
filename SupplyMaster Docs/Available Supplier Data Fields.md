---
title: "Available Supplier Data Fields"
source: "https://help.comstack.com/en/articles/13933616-available-supplier-data-fields"
author:
published: 2026-05-27
created: 2026-06-11
description: "Every supplier in SupplyMaster provides a set of product-level and variant-level data fields."
tags:
  - "clippings"
---
Every supplier in SupplyMaster provides a set of product-level and variant-level data fields. These fields are the building blocks for field mapping, product filters, and Liquid modifier formulas. This reference lists every available field for each supported supplier.

---

## Where to Use These Fields

| **Feature** | **Where to Find It** | **How Fields Are Used** |
| --- | --- | --- |
| Match Fields | **Edit Supplier > Product Settings > Match Fields** | Map a supplier source field to a Shopify destination field (e.g., map *brandName* to *Vendor*) |
| Liquid Modifiers | Click **Modify** on any mapped field | Reference fields inside Liquid templates (e.g., `{​{ variant.piecePrice \| times: 1.5 }​}`) |
| Product Filters | **Edit Supplier > Product Settings > Filters** | Filter products by field values before import (e.g., Brand Name — Contains Any — Gildan, Bella+Canvas) |

**Product-level fields** apply to the entire product (e.g., title, brand, description). **Variant-level fields** apply to individual variants (e.g., color, size, price, SKU). When referencing variant fields in Liquid modifiers, prefix them with `variant.` — for example, `variant.piecePrice` or `variant.colorName`.

---

## S&S Activewear

styleID, partNumber, brandName, styleName, uniqueStyleName, title, description, baseCategory, categories, catalogPageNumber, newStyle, comparableGroup, companionGroup, brandImage, styleImage, prop65Chemicals, specs

sku, gtin, colorName, colorCode, colorGroup, colorSwatchImage, colorFrontImage, colorSideImage, colorBackImage, colorOnModelFrontImage, colorOnModelSideImage, colorOnModelBackImage, sizeName, sizeCode, sizeOrder, caseQty, unitWeight, mapPrice, piecePrice, dozenPrice, casePrice, salePrice, customerPrice, caseWeight, qty, countryOfOrigin, inventoryQuantities

---

## SanMar (US)

title, productDescription, styleNumber, availableSizes, specSheet, categoryName, subcategoryName, mill, productStatus, companionStyles, brandLogoImageURL, thumbnailImageURL, productImageURL, frontModelImageURL, productMeasurements, pmsColor, decorationSpecSheet, vendor, type

uniqueKey, gtin, priceGroup, colorName, size, qty, colorSquareImage, colorProductImage, colorSwatchImageURL, frontModelImageURL, backModelImageURL, frontFlatImageURL, backFlatImageURL, pieceWeight, priceText, suggestedPrice, msrp, mapPricing, piecePrice, dozensPrice, casePrice, caseSize, sizeIndex, sku, grams, inventoryQty, price, weightUnit

---

## SanMar Canada

supplierProductId, title, descriptionHtml, vendor

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, size, sku, weight, weightUnit, availableQuantity, inventoryUnit, primaryImageURL, cost, currency, status, casePackQty, sizeRank, rowDataUpdatedAt

---

## AlphaBroder

title, styleNumber, millCode, millName, category, subcategory, millDescription, millStyleNumber, styleName, fullFeatureDescription

itemNumber, colorName, colorGroupCode, colorCode, hexCode, sizeGroup, sizeCode, size, caseQty, thumbnailName, normalImageName, brandPageNumber, frontOfImageName, backOfImageName, sideOfImageName, gtin, launchDate, pmsColor, sizeSortOrder, frontImageHiResUrl, backImageHiResUrl, sideImageHiResUrl, markupCode, mktgColorNumber, mktgColorName, mktgColorHexCode, piecePrice, dozenPrice, casePrice, retailPrice, colorDescription, sizeDescription, unitWeight, weightUnit, caseQuantity, warehouse, orderByMultiple, pieceQuantity, totalInventory, dropshipInventory, closeoutStatus, closeoutPrice, closeoutStartDate, closeoutEndDate

---

## Augusta Sportswear (Momentec)

supplierProductId, title, descriptionHtml, vendor, status, category, features, countryOfOrigin, productVideoUrl, launchDate

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, colorHexValue, size, sku, barcode, weight, weightUnit, volume, volumeUnit, casePackQty, availableQuantity, inventoryQuantity, unitOfMeasure, warehouseId, msrp, cost, currency, primaryImageURL, additionalImageURL1, swatchImageURL, sizeChartImageURL

---

## Champro

supplierProductId, title, descriptionHtml, vendor, status, isDiscontinued

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, size, sku, barcode, weight, weightUnit, availableQuantity, inventoryQuantity, nextAvailableQuantity, nextAvailableDate, futureAvailableQuantity, futureAvailableDate, height, length, width, msrp, price1, price2, price3, price4, price5, unitOfMeasureUDF, sizeMatrixUDF, alternativeSizeMatrixUDF, primaryImageURL, imageURL1, imageURL2, imageURL3

---

## Decky

supplierProductId, title, descriptionHtml, vendor, category

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, size, sku, barcode, weight, weightUnit, packageWeight, packageDimensions, availableQuantity, msrp, cost, currency, sizeRank, primaryImageURL, image1, image2, image3, image4, image5, image6, sizeChartImageURL, launchDate, receiveDate, daysOut

---

## Cap America

sourceProductId, title, productName, description, vendor, categories, subCategories, primaryImageUrl, price\_description, complianceInfoAvailable, productKeywords, productBrand, export, lineName, defaultSetupCharge, defaultRunCharge, imprintSize

partId, color\_colorName, price, price\_quantityMin, price\_discountCodes, price\_groupName, price\_currency, maxPrice, maxPriceQtyLimit, minPrice, minPriceQtyLimit, isCaution, cautionComment, isCloseout, countryOfOrigin, color\_hex, color\_approximatePms, unspsc, gtin, isRushService, productPackage\_default, productPackage\_packageType, productPackage\_description, productPackage\_quantity, productPackage\_dimensionUom, productPackage\_depth, productPackage\_height, productPackage\_width, productPackage\_weightUom, productPackage\_weight, shippingPackage\_packageType, shippingPackage\_description, shippingPackage\_quantity, shippingPackage\_dimensionUom, shippingPackage\_depth, shippingPackage\_height, shippingPackage\_width, shippingPackage\_weightUom, shippingPackage\_weight, nmfcDescription, nmfcNumber, isOnDemand, isHazmat

---

## Otto Cap

sourceProductId, title, productName, description, vendor, categories, subCategories, primaryImageURL, price\_description, complianceInfoAvailable, productKeywords, productBrand, export, lineName, defaultSetupCharge, defaultRunCharge, imprintSize

partId, color, size, gtin, price, price\_quantityMin, price\_discountCodes, price\_groupName, price\_currency, maxPrice, maxPriceQtyLimit, minPrice, minPriceQtyLimit, primaryImageURL, frontImageURL, rearImageURL, rightImageURL, insideImageURL, decoratedImageURL, leftImageURL, topImageURL, bottomImageURL, outsideImageURL, standardImageURL, highImageURL, podcastURL, specsURL, productSafetyURL, factsURL, complianceURL, artTemplateURL, marketingURL, isCaution, cautionComment, isCloseout, countryOfOrigin, color\_hex, color\_approximatePms, color\_colorName, unspsc, isRushService, productPackage\_default, productPackage\_packageType, productPackage\_description, productPackage\_quantity, productPackage\_dimensionUom, productPackage\_depth, productPackage\_height, productPackage\_width, productPackage\_weightUom, productPackage\_weight, shippingPackage\_packageType, shippingPackage\_description, shippingPackage\_quantity, shippingPackage\_dimensionUom, shippingPackage\_depth, shippingPackage\_height, shippingPackage\_width, shippingPackage\_weightUom, shippingPackage\_weight, nmfcDescription, nmfcNumber, isOnDemand, isHazmat, mainPart, partColor, labelSize, quantityAvailable\_uom, quantityAvailable\_value, manufacturedItem, buyToOrder, replenishmentLeadTime

---

## Goldstar

sourceProductId, title, productName, description, vendor, categories, subCategories, primaryImageURL, price\_description, complianceInfoAvailable, productKeywords, productBrand, export, lineName, defaultSetupCharge, defaultRunCharge, imprintSize, specsURL, productSafetyURL, factsURL, complianceURL, artTemplateURL, marketingURL, podcastURL

partId, color, size, gtin, price, price\_quantityMin, price\_discountCodes, price\_groupName, price\_currency, alt\_price, alt\_price\_quantityMin, maxPrice, maxPriceQtyLimit, minPrice, minPriceQtyLimit, primaryImageURL, frontImageURL, rearImageURL, rightImageURL, leftImageURL, topImageURL, bottomImageURL, insideImageURL, outsideImageURL, standardImageURL, highImageURL, decoratedImageURL, isCaution, cautionComment, isCloseout, countryOfOrigin, color\_hex, color\_approximatePms, color\_colorName, apparelSize\_apparelStyle, apparelSize\_labelSize, apparelSize\_customSize, unspsc, isRushService, productPackage\_default, productPackage\_packageType, productPackage\_description, productPackage\_quantity, productPackage\_dimensionUom, productPackage\_depth, productPackage\_height, productPackage\_width, productPackage\_weightUom, productPackage\_weight, shippingPackage\_packageType, shippingPackage\_description, shippingPackage\_quantity, shippingPackage\_dimensionUom, shippingPackage\_depth, shippingPackage\_height, shippingPackage\_width, shippingPackage\_weightUom, shippingPackage\_weight, nmfcDescription, nmfcNumber, isOnDemand, isHazmat, mainPart, partColor, labelSize, quantityAvailable\_uom, quantityAvailable\_value, manufacturedItem, buyToOrder, replenishmentLeadTime

---

## Charles River Apparel

sourceProductId, title, productName, description, vendor, categories, subCategories, primaryImageURL, price\_description, complianceInfoAvailable, productKeywords, productBrand, export, lineName, defaultSetupCharge, defaultRunCharge, imprintSize, specsURL, productSafetyURL, factsURL, complianceURL, artTemplateURL, marketingURL, podcastURL

partId, color, size, gtin, price, price\_quantityMin, price\_discountCodes, price\_groupName, price\_currency, alt\_price, alt\_price\_quantityMin, maxPrice, maxPriceQtyLimit, minPrice, minPriceQtyLimit, primaryImageURL, frontImageURL, rearImageURL, rightImageURL, leftImageURL, topImageURL, bottomImageURL, insideImageURL, outsideImageURL, standardImageURL, highImageURL, decoratedImageURL, isCaution, cautionComment, isCloseout, countryOfOrigin, color\_hex, color\_approximatePms, color\_colorName, apparelSize\_apparelStyle, apparelSize\_labelSize, apparelSize\_customSize, unspsc, isRushService, productPackage\_default, productPackage\_packageType, productPackage\_description, productPackage\_quantity, productPackage\_dimensionUom, productPackage\_depth, productPackage\_height, productPackage\_width, productPackage\_weightUom, productPackage\_weight, shippingPackage\_packageType, shippingPackage\_description, shippingPackage\_quantity, shippingPackage\_dimensionUom, shippingPackage\_depth, shippingPackage\_height, shippingPackage\_width, shippingPackage\_weightUom, shippingPackage\_weight, nmfcDescription, nmfcNumber, isOnDemand, isHazmat, mainPart, partColor, labelSize, quantityAvailable\_uom, quantityAvailable\_value, manufacturedItem, buyToOrder, replenishmentLeadTime

---

## Cutter & Buck

supplierProductId, title, descriptionHtml, vendor, category, status, productType, brandName, mill, companionStyles, handle, priceText

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, colorHexValue, pmsColor, size, sizeIndex, sku, barcode, weight, weightUnit, cartonQuantity, availableQuantity, inventoryKey, msrp, cost, currency, mapPricing, dozensPrice, casePrice, primaryImageURL, image1, image2, image3, image4, image5, image6, colorSwatchImageURL

---

## Edwards

supplierProductId, title, descriptionHtml, vendor, status, category, features, unitOfMeasure

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, colorHexValue, pantoneColor, size, sizeScale, fit, sku, barcode, weight, weightUnit, width, height, length, availableQuantity, inventoryQuantity, msrp, cost, currency, closeOutProduct, comments, primaryImageURL, backImageURL, leftImageURL, rightImageURL, onModelImageURL, thumbImageURL, swatchImageURL

---

## ACC (Atlantic Coast Cotton)

supplierProductId, title, descriptionHtml, vendor, status

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, colorHexValue, size, sku, barcode, weight, weightUnit, availableQuantity, cartonQuantity, sizeRank, msrp, cost, currency, primaryImageURL

---

## JDS Industries

supplierProductId, title, descriptionHtml, vendor, category, status, countryOfOrigin, material, gender, keywords, catalogid, pages

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, size, sku, weight, weightUnit, cartonQuantity, availableQuantity, localQuantity, sizeRank, length, height, width, cost, currency, priceBreak1, priceBreak2, priceBreak3, priceBreak4, priceBreak5, primaryImageURL, image1, image2, image3

---

## Scrub Authority

supplierProductId, title, descriptionHtml, vendor, category, status, gender, material, line, manufacturer

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, colorCode, size, sku, barcode, weight, weightUnit, msrp, cost, currency, availableQuantity, primaryImageURL, image1, image2, image3, image4, image5, image6

---

## AS Colour US

supplierProductId, title, descriptionHtml, vendor, category, shortDescription, printingTechniques, composition, productWeight, coreRange, countryOfOrigin, hsCode

supplierVariantId, option1Name, option1Value, option2Name, option2Value, color, size, sku, barcode, cost, currency, availableQuantity, hexCode1, hexCode2, pantone1, pantone2, cartonQuantity, quantityCA, quantityNC, etaCA, etaNC, sizeRank, primaryImageURL, image1, image2, image3, image4, image5, image6, sizeChartImageURL

---

## AI+ Enriched Fields

If you have the **AI+** add-on enabled for a supplier, additional enriched fields become available for mapping. These fields are the same across all AI+ supported suppliers:

AI\_shopifyProductCategoryId, AI\_shopifyProductCategory, AI\_baseCategory, AI\_subCategory, AI\_cleanTitle, AI\_bulletedDescription, AI\_shortDescription, AI\_mediumDescription, AI\_longDescription, AI\_seoTitle, AI\_seoDescription, AI\_tags, AI\_material, AI\_gender, AI\_cleanHandle

AI+ fields are automatically mapped to recommended Shopify fields by default. You can customize these mappings in the **Match Fields** section. For more on AI+, see our **AI+ Enriched Product Data** article.

---

## Quick Liquid Examples

Below are common Liquid modifier formulas you can use with any supplier's fields. Enter these in the **Modify** box on a mapped field. For a full guide, see our **Customizing Fields with Liquid Formulas** article.

| **Use Case** | **Liquid Formula** |
| --- | --- |
| Price markup (50%) | `{​{ variant.piecePrice \| times: 1.5 \| round: 2 }​}` |
| Markup plus flat fee | `{​{ variant.salePrice \| times: 1.5 \| plus: 22 }​}` |
| Price floor ($15 minimum) | `{% assign calc = variant.piecePrice \| times: 1.3 %}{% if calc < 15 %}15{% else %}{​{ calc \| round: 1 }​}{% endif %}` |
| Tiered pricing | `{% assign p = variant.piecePrice %}{% if p <= 10 %}{​{ p \| times: 1.5 \| round: 1 }​}{% elsif p <= 30 %}{​{ p \| times: 1.2 \| round: 1 }​}{% else %}{​{ p \| times: 1.1 \| round: 1 }​}{% endif %}` |
| Combine title fields | `{​{ brandName }​} - {​{ styleName }​}` |
| Fallback chain | `{​{ variant.salePrice \| default: variant.customerPrice \| default: variant.piecePrice }​}` |
| Weight fallback | `{% if variant.weight == 0 %}0.35{% else %}{​{ variant.weight }​}{% endif %}` |
| Uppercase brand + SKU prefix | `{​{ brandName \| upcase }​} - {​{ styleName }​}` |

---

## Liquid Syntax Quick Reference

| **Category** | **Available Filters & Operators** |
| --- | --- |
| Math | plus, minus, times, divided\_by, modulo, round, ceil, floor |
| Strings | upcase, downcase, capitalize, append, prepend, replace, remove, strip, truncate |
| Logic | `{% if %}...{% elsif %}...{% else %}...{% endif %}` — operators: ==,!=, <, >, <=, >=, contains, and, or |
| Variables | `{% assign name = value %}` |
| Defaults | `{​{ field \| default: "fallback" }​}` |

---

## Need Help?

For more on mapping fields see our **Mapping Supplier Fields to Shopify** article. For advanced Liquid formulas see our **Customizing Fields with Liquid Formulas** article. If you get stuck at any point, contact support on chat in the bottom-right corner of the app.