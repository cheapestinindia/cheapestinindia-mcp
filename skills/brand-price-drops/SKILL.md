---
name: brand-price-drops
description: Find recent price drops for one brand in India (Samsung, Philips, OnePlus, Havells, …), optionally for one product type, using CheapestInIndia. Use for "Samsung price drops", "what Philips products got cheaper this week", "any deals on LG TVs".
---

# Brand price drops

1. **Brand drops** → `brand_price_drops` with `brand` as the user wrote it (e.g. "Samsung", "One Plus"). Add `keyword` for a product type within the brand ("tv", "refrigerator", "air fryer"), and `days` (1–7, default 7) for a shorter window. Results show as product cards, biggest drop first.
2. **Category instead of brand** ("price drops on ACs") → `top_price_drops` with `category`.
3. **Is the dropped price good?** → `get_price_history` with the product's `id` from the results.

Rules:
- Report drops factually: current price, store, drop amount and when. Don't call anything a "steal" or predict further drops.
- Only the brand's own listings are covered; if nothing is found, check the spelling or use `search_products` with the brand name.
