# Product Library

Use a workspace-level file library so registered products remain available across skill upgrades and future campaigns.

## Location and structure

Default root: `<workspace>/product-library`.

```text
product-library/
├── INDEX.md
└── products/
    └── PV-0001/
        ├── product.md
        └── source-images/
```

Do not store the library inside the skill folder or a temporary download folder.

## Product ID rules

- Use `PV-` plus four digits, allocated sequentially from the highest existing ID.
- Never reuse, rename, or renumber an issued ID.
- Use one record per stable visual/product identity.
- Create a new ID when material, color, construction, dimensions, component count, or silhouette changes. Record relationships such as `variant_of` when useful.

## Register a new product

1. Verify that no existing record represents the same SKU/variant.
2. Allocate the next unused ID.
3. Create `products/<ID>/source-images/`.
4. Copy—not move—the supplied originals into that folder with stable descriptive filenames.
5. Create `product.md` using the schema below.
6. Add one row to `INDEX.md`, including a representative hero thumbnail.
7. Return the assigned ID to the user.

## Load an existing product

When the user names an ID, read its record and use its archived source files. Do not request another upload or repeat the parameter form unless a file is missing, a needed angle is unsupported, or the user says the product changed.

The user may request, for example: `用 PV-0001 做一套都市屋顶夜景的 15 秒视频`.

## Record schema

Each `product.md` must contain:

- ID, name, SKU/variant, category, status, creation/update dates.
- Set contents and dimensions.
- Component-by-component materials, colors, and finishes.
- Confirmed structure, functions, and configuration.
- Selling points with source and evidence status.
- Target market, scenes, people, and forbidden claims.
- Source-image manifest with relative path, angle/role, and limitations.
- Product Identity Lock and unsupported/unknown details.
- Append-only project history with date, direction, and output paths.

Use `unknown` instead of guessing. A user-supplied claim without approved substantiation stays recorded as `evidence required`.

## Index schema

Keep `INDEX.md` as a searchable visual Markdown table:

| 产品编码 | 产品名称 | 产品图 | 快速调用 |
| --- | --- | --- | --- |

Embed one representative hero image using a relative path so the whole library remains movable. Do not remove historical product rows unless the user explicitly requests archival or deletion.

## Campaign history

Do not duplicate generated storyboards and videos into the library. Store absolute paths to their project folders and outputs so the product record remains lightweight. Append new campaigns; never overwrite previous history.
