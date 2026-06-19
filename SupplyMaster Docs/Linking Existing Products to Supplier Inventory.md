---
title: "Linking Existing Products to Supplier Inventory"
source: "https://help.comstack.com/en/articles/13935021-linking-existing-products-to-supplier-inventory"
author:
published: 2026-03-09
created: 2026-06-11
description: "Product Mappings let you manually connect Shopify products that were not created by SupplyMaster to a supplier's catalog."
tags:
  - "clippings"
---
Product Mappings let you manually connect Shopify products that were **not** created by SupplyMaster to a supplier's catalog. This is useful when you already have products in your store — with customized images, titles, or descriptions — and you want SupplyMaster to keep their inventory, pricing, or variant data in sync with a supplier without overwriting your customizations.

---

## When to Use Product Mappings

- You have branded or custom-designed products already in your Shopify store.
- You've customized product images, names, or descriptions and want to preserve them.
- You want SupplyMaster to update only inventory, pricing, or variant-level fields on these products.

Products imported directly by SupplyMaster are automatically linked to the supplier and **do not** need manual mapping.

---

## Enabling the Product Mappings Editor

[![The Advanced Settings tab showing the Product Mappings Editor dropdown with Enable and Disable options](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323281/b38071ce6c40d44fe6007aa9600e/enable-product-mappings-setting.png?expires=1781227800&signature=0a44009f21ae481a2fc05d9cba26ebd11b40c76a5293147d62817181fb12bd2d&req=diEjFcp8noNXWPMW1HO4zbQo9j3zxunzpYdpABNYtsKOJ%2B3J2kw%2BCvlKnsZm%0AtVjCRGJqhc9OQLs%2BbW8%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323281/b38071ce6c40d44fe6007aa9600e/enable-product-mappings-setting.png?expires=1781227800&signature=0a44009f21ae481a2fc05d9cba26ebd11b40c76a5293147d62817181fb12bd2d&req=diEjFcp8noNXWPMW1HO4zbQo9j3zxunzpYdpABNYtsKOJ%2B3J2kw%2BCvlKnsZm%0AtVjCRGJqhc9OQLs%2BbW8%3D%0A)

1. Navigate to **Edit Supplier** > **Advanced Settings**.
2. Set **Product Mappings Editor** to **Enable Product Mapping Editor**.
3. Click **Save Supplier**.

Once enabled, a **Product Mappings** tab appears on the supplier's product view page.

---

## Adding a Product Mapping

[![The Add Product Mapping modal showing the Shopify product search and supplier product search fields](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323300/41244544f45dacebe0d8b76869cc/map-products-step.png?expires=1781227800&signature=a2d62a1d8cecb587d218db94c2eaf4cf75004f1f856cdefff9996251ca96e725&req=diEjFcp8noJfWfMW1HO4zZFcqGdUN5TN%2BzhAgRxVCeqMAMYD5yYIk5Ct1RYQ%0A%2BbinlaBDWeWXyMvZsh0%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323300/41244544f45dacebe0d8b76869cc/map-products-step.png?expires=1781227800&signature=a2d62a1d8cecb587d218db94c2eaf4cf75004f1f856cdefff9996251ca96e725&req=diEjFcp8noJfWfMW1HO4zZFcqGdUN5TN%2BzhAgRxVCeqMAMYD5yYIk5Ct1RYQ%0A%2BbinlaBDWeWXyMvZsh0%3D%0A)

1. Go to the **Product Mappings** tab and click **\+ Add Mapping**.
2. Select the **Shopify product** you want to link. You can search by product title.
3. Select the **supplier product** to link it to. This is the product from the supplier's catalog that matches your Shopify product.

[![The Edit Product Mapping modal showing the variant mapping table with Shopify variants, supplier variant dropdowns, and status indicators](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323332/7d437566a2236ef4543f60a551ba/map-variants-step.png?expires=1781227800&signature=eb000d7eb520a163ff12f92756c602d6e112cd71d9daa9def383c073c071734d&req=diEjFcp8noJcW%2FMW1HO4zXSsdmLxYEqVZv5Qjfem8p%2FJS2gZxO7ulTT8WB7y%0A7l9dCb24yF0yg%2Bc6jms%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323332/7d437566a2236ef4543f60a551ba/map-variants-step.png?expires=1781227800&signature=eb000d7eb520a163ff12f92756c602d6e112cd71d9daa9def383c073c071734d&req=diEjFcp8noJcW%2FMW1HO4zXSsdmLxYEqVZv5Qjfem8p%2FJS2gZxO7ulTT8WB7y%0A7l9dCb24yF0yg%2Bc6jms%3D%0A)

After selecting both products, you'll see a variant mapping table. Each row shows a Shopify variant (e.g., "Red / Medium") with a dropdown to select the corresponding supplier variant.

1. For each Shopify variant, select the matching supplier variant from the dropdown. Supplier variants are shown with their color, size, and ID to help you match correctly.
2. Each Shopify variant can only be linked to **one unique supplier variant**. If you try to map two Shopify variants to the same supplier variant, a warning icon will appear.
3. Select **No Mapping (Preserve)** for any Shopify variant you want to keep as-is, preventing supplier data from updating it during sync.

The status column shows your mapping progress:

- **Green check** — Variant is mapped to a unique supplier variant.
- **Yellow warning** — Variant is mapped but the supplier variant is used by another Shopify variant (duplicate).
- **Grey circle** — Variant is not mapped or set to Preserve.

Click **Save** to confirm the mapping. The product will appear in the Product Mappings table showing the Shopify product, supplier product ID, number of variants mapped, and status.

---

## Editing & Deleting Mappings

[![The Product Mappings table showing mapped products with image, Shopify product name, supplier product ID, variants mapped count, status badges, and edit/delete action buttons](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323360/0b187477cfb39daa3c8816aac4c6/product-mappings-table.png?expires=1781227800&signature=ea8eb73abc7bd77e718cfe202b533edd80c6771c75580a7e7c0400f9c2e5ad07&req=diEjFcp8noJZWfMW1HO4zdsRASh4q3LRS%2BC8XXS7rTFVom2Ry5rXxt2aiayv%0AXwNMrXQVqtbKdYE5B0I%3D%0A)](https://comstack.intercom-attachments-1.com/i/o/eznrauif/2143323360/0b187477cfb39daa3c8816aac4c6/product-mappings-table.png?expires=1781227800&signature=ea8eb73abc7bd77e718cfe202b533edd80c6771c75580a7e7c0400f9c2e5ad07&req=diEjFcp8noJZWfMW1HO4zdsRASh4q3LRS%2BC8XXS7rTFVom2Ry5rXxt2aiayv%0AXwNMrXQVqtbKdYE5B0I%3D%0A)

- To **edit** a mapping, click the edit icon next to the product in the Product Mappings table. You can change variant assignments or switch the supplier product.
- To **delete** a mapping, click the delete icon. This removes the link between the Shopify product and the supplier — the Shopify product itself is not deleted.

---

## How Syncing Works with Mapped Products

Once a product is mapped, it participates in automatic syncs just like products created by SupplyMaster. The behavior depends on your **Auto Sync Settings** (configured in **Edit Supplier** > **Automatic Sync**):

| **Sync Behavior** | **What Happens** |
| --- | --- |
| Import Preserves | Fields are **not changed** during sync. Your customized data stays intact. |
| Import Overwrites | Fields are **replaced with supplier data** on every sync. Custom titles, descriptions, or images may be overwritten. |
| Import Adds | New variants found in the supplier catalog are **created** on the mapped Shopify product. |

To change these behaviors, go to **Edit Supplier** > **Automatic Sync** and adjust the **Update Settings** and **Auto Create** options.

---

If you're using Product Mappings to keep customized products in sync, set your **Update Settings** to one of these options to protect your customizations:

- **Only Variant Fields** — Updates pricing, inventory, weight, and variant attributes but leaves product-level fields (title, description, images) untouched.
- **Only Inventory** — Updates only inventory quantities, preserving all other product and variant data.

Avoid using **All Fields with Images** or **All Fields Except Images** on mapped products unless you want the supplier data to fully replace your custom product content.

---

## Tips

- You don't need to map every variant. Use **No Mapping (Preserve)** for variants that you manage manually or that don't have a supplier equivalent.
- Product Mappings are per-supplier. If you source the same product from multiple suppliers, each supplier mapping is independent.
- Deleting a mapping does not delete the Shopify product — it only removes the supplier link. The product stays in your store.
- After adding or changing mappings, run a manual sync or wait for the next automatic sync to see the updated data in Shopify.