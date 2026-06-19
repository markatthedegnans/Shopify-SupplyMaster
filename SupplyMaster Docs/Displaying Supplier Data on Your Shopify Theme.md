---
title: "Displaying Supplier Data on Your Shopify Theme"
source: "https://help.comstack.com/en/articles/13940836-displaying-supplier-data-on-your-shopify-theme"
author:
published: 2026-03-09
created: 2026-06-11
description: "SupplyMaster can import supplier data like product images, specifications, and category names into Shopify metafields."
tags:
  - "clippings"
---
SupplyMaster can import supplier data like product images, specifications, and category names into Shopify metafields. This article walks you through displaying that metafield data on your product pages using Shopify's **Custom Liquid** theme sections. Each walkthrough covers the SupplyMaster mapping setup and the Shopify theme editor steps.

**Prerequisites:** You should already have a supplier connected and mapped to metafields. If not, see our **Using Metafields with SupplyMaster** article for setup instructions.

---

## Walkthrough 1: Product Side & Back Images

S&S Activewear provides relative image paths for side, back, and on-model product photos. SupplyMaster imports these as variant metafield URLs, and you can display them alongside the main product image on your storefront.

1. Open SupplyMaster → **Manage Suppliers** → click **Edit** on your S&S Activewear supplier.
2. Go to **Product Settings** → **Match Fields**.
3. Click **Add Field** and create the mappings shown in the table below.

| **Source Field** | **Destination** | **Metafield Key** | **Modifier** |
| --- | --- | --- | --- |
| variant.colorSideImage | variant.metafields | `custom.side_image` | `https://www.ssactivewear.com/{​{ variant.colorSideImage }​}` |
| variant.colorBackImage | variant.metafields | `custom.back_image` | `https://www.ssactivewear.com/{​{ variant.colorBackImage }​}` |
| variant.colorOnModelFrontImage | variant.metafields | `custom.on_model_front` | `https://www.ssactivewear.com/{​{ variant.colorOnModelFrontImage }​}` |

1. For each field, click **Modify** and paste the URL prefix shown above. The modifier prepends the S&S base URL to the relative image path.
2. Click **Save Supplier**, then run an import or wait for the next sync to populate the metafields.

You can also map **variant.colorOnModelSideImage** and **variant.colorOnModelBackImage** if you want the full set of on-model images.

1. In Shopify Admin, go to **Online Store** → **Themes**.
2. Click **Customize** on your active theme.
3. Navigate to a product page template (or choose **Products** → **Default product** from the page selector).
4. In the template sidebar, click **Add section** → choose **Custom Liquid**.
5. Paste the following Liquid code into the **Liquid code** text area:

```
{% if product.selected_or_first_available_variant.metafields.custom.side_image != blank %}
  <div class="supplier-extra-images">
    <h3>Additional Views</h3>
    <div class="extra-images-grid">
      {% if product.selected_or_first_available_variant.metafields.custom.side_image != blank %}
        <img src="{​{ product.selected_or_first_available_variant.metafields.custom.side_image }​}"
             alt="{​{ product.title }​} - Side View"
             loading="lazy" />
      {% endif %}
      {% if product.selected_or_first_available_variant.metafields.custom.back_image != blank %}
        <img src="{​{ product.selected_or_first_available_variant.metafields.custom.back_image }​}"
             alt="{​{ product.title }​} - Back View"
             loading="lazy" />
      {% endif %}
      {% if product.selected_or_first_available_variant.metafields.custom.on_model_front != blank %}
        <img src="{​{ product.selected_or_first_available_variant.metafields.custom.on_model_front }​}"
             alt="{​{ product.title }​} - On Model"
             loading="lazy" />
      {% endif %}
    </div>
  </div>
{% endif %}
```

1. Paste the following CSS into the **Custom CSS** text area:

```
.supplier-extra-images {
  margin-top: 20px;
}
.extra-images-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
  gap: 12px;
  margin-top: 10px;
}
.extra-images-grid img {
  width: 100%;
  height: auto;
  border-radius: 4px;
  object-fit: cover;
}
```

1. Click **Save** in the theme editor.
2. Preview a product page that has been synced with S&S Activewear to verify the images appear.

**Tip:** The images update automatically when a variant is selected if your theme supports dynamic variant rendering. If the images don't change per variant, your theme may need a small JavaScript snippet to listen for variant changes and swap the metafield URLs.

---

## Walkthrough 2: Product Specifications Table

Many suppliers (including S&S Activewear) provide product specifications — fabric weight, material composition, features, and more. SupplyMaster imports this data as a text string in a metafield, and you can display it as a formatted table on your product page.

1. Open SupplyMaster → **Edit Supplier** → **Product Settings** → **Match Fields**.
2. Click **Add Field** and create a mapping:
	- Source: **specs**
	- Destination: **Metafield**
	- Metafield key: `custom.specs`
3. Click **Save Supplier** and run an import. The specs data is stored as a comma-separated text value in the `custom.specs` metafield.

1. In Shopify Admin, go to **Online Store** → **Themes** → **Customize**.
2. Navigate to your product page template.
3. Click **Add section** → **Custom Liquid**.
4. Paste the following Liquid code:

```
{% if product.metafields.custom.specs != blank %}
  <div class="product-specs">
    <h3>Product Specifications</h3>
    <table class="specs-table">
      <tbody>
        {% assign specs_list = product.metafields.custom.specs | split: ',' %}
        {% for spec in specs_list %}
          {% assign spec_parts = spec | strip | split: ':' %}
          {% if spec_parts.size >= 2 %}
            <tr>
              <td><strong>{​{ spec_parts[0] | strip }​}</strong></td>
              <td>{​{ spec_parts[1] | strip }​}</td>
            </tr>
          {% else %}
            <tr>
              <td colspan="2">{​{ spec | strip }​}</td>
            </tr>
          {% endif %}
        {% endfor %}
      </tbody>
    </table>
  </div>
{% endif %}
```

1. Paste the following CSS into the **Custom CSS** text area:

```
.product-specs {
  margin-top: 24px;
}
.specs-table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 10px;
}
.specs-table td {
  padding: 8px 12px;
  border-bottom: 1px solid #e5e5e5;
  vertical-align: top;
}
.specs-table tr:last-child td {
  border-bottom: none;
}
.specs-table td:first-child {
  width: 40%;
  font-weight: 600;
}
```

1. Click **Save**.
2. Preview a product page to verify the specifications table displays correctly. Test with several products to confirm the table adjusts to different spec formats.

---

## Walkthrough 3: Category Names on Product Pages

Suppliers like S&S Activewear provide category names (e.g., "T-Shirts", "Outerwear", "Fleece") for each product. You can import these into a metafield and display them as labels or breadcrumbs on your product pages, or use them to build Shopify collections.

1. Open SupplyMaster → **Edit Supplier** → **Product Settings** → **Match Fields**.
2. Click **Add Field** and create a mapping:
	- Source: **categoryNames** (or **categories**)
	- Destination: **Metafield**
	- Metafield key: `custom.categories`
3. **Optional prefix modifier:** If you want to add a prefix to each category name (useful for building automated collections), click **Modify** and enter:
	```
	{% assign categories_names = categoryNames | split: ',' %}{% for category in categories_names %}sub_cat_{​{ category | strip }​},{% endfor %}
	```
	This transforms "T-Shirts, Outerwear" into "sub\_cat\_T-Shirts, sub\_cat\_Outerwear".
4. Click **Save Supplier** and run an import.

You can also map **categoryNames** to **Tags** instead of a metafield if you prefer to use Shopify tags for collections. Note that mapping to Tags will overwrite existing tags on every sync.

1. In Shopify Admin, go to **Online Store** → **Themes** → **Customize**.
2. Navigate to your product page template.
3. Click **Add section** → **Custom Liquid**.
4. Paste the following Liquid code:

```
{% if product.metafields.custom.categories != blank %}
  <div class="product-categories">
    <span class="categories-label">Categories:</span>
    {% assign cats = product.metafields.custom.categories | split: ',' %}
    {% for cat in cats %}
      <span class="category-badge">{​{ cat | strip }​}</span>
    {% endfor %}
  </div>
{% endif %}
```

1. Paste the following CSS into the **Custom CSS** text area:

```
.product-categories {
  margin-top: 16px;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  gap: 8px;
}
.categories-label {
  font-weight: 600;
  margin-right: 4px;
}
.category-badge {
  display: inline-block;
  padding: 4px 10px;
  background: #f4f4f4;
  border-radius: 12px;
  font-size: 13px;
}
```

1. Click **Save**.
2. Preview a product page to verify the category badges appear below the product details.

---

## General Tips

- All three walkthroughs use Shopify's **Custom Liquid** section, available in most Shopify 2.0 themes (Dawn and similar). If your theme doesn't have this option, you may need to edit the theme code directly under **Online Store** → **Themes** → **Edit code**.
- Metafield data must be populated before it can display. After mapping fields in SupplyMaster, run an import or wait for the next automatic sync.
- The CSS examples above are starting points. Adjust colors, spacing, and sizing to match your theme's design.
- For metafield setup details (namespace formatting, product vs. variant metafields, supported types), see our **Using Metafields with SupplyMaster** article.
- For field mapping basics and Liquid modifier syntax, see our **Mapping Supplier Fields to Shopify** and **Customizing Fields with Liquid Formulas** articles.