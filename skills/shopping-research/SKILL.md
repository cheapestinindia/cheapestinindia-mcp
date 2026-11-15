---
name: shopping-research
description: Research what a product type costs in India before buying — price range, median, budget/mid-range/premium tiers and brands — then shortlist options with CheapestInIndia. Use for "how much should I spend on X", "what's a good budget for X", or "show me X under ₹N".
---

# Research a purchase

1. **Get the market picture** → `market_snapshot` with the product type (e.g. "air fryer", "washing machine"). Report the range, median, middle half and the brands in each tier.
2. **Shortlist** → `search_products` with the user's budget as `max_price` (and `min_price` for a tier). Use `browse_categories` first if the user names a broad category, then pass its id in `category_ids`.
3. **Show options** → the `search_products` results already appear as product cards. To show only a hand-picked 4–6, call `render_product_results` with those products' `ids` and a short `title`.
4. If the user narrows to 2–4 items, use `compare_products`; for "is this price good", use `get_price_history`.

Rules:
- Prices are current INR listings and change often; say so.
- Don't rank brands by quality or make claims the data doesn't support — describe prices, stores and recorded price history.
