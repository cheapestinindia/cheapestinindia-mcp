---
name: price-drops
description: Find products whose prices recently dropped in India, overall, within a category, or during a current store sale, using CheapestInIndia. Use for "what dropped in price today", "price drops on phones", or "what's on sale right now".
---

# Find recent price drops

1. **Category drops** → `top_price_drops` with `category` as a plain name (e.g. "air conditioners", "mobile phones") and `hours` (24 by default; 1–72). Use `browse_categories` only if that name isn't found.
2. **Overall drops** → `top_price_drops` without a category ranks by percentage drop. Prefer a category whenever the user names a product type.
3. **Store sales** → `sale_events` to list current sales, then `sale_events` with a `slug` for the price drops in that sale.
4. `top_price_drops` and `sale_events` (with a slug) show their products as cards automatically; use `render_product_results` only for a hand-picked subset.

Rules:
- Report drops factually: current price, store and drop amount. Don't call anything a "steal" or predict further drops.
- Check `get_price_history` before saying a dropped price is the lowest ever.
