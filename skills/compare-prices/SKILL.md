---
name: compare-prices
description: Compare prices for a product across Indian online stores, or compare 2–4 shortlisted products, using CheapestInIndia. Use when the user asks where a product costs least, wants prices across stores, or asks to compare specific products.
---

# Compare prices across stores or products

1. **Search** → `search_products` with a specific query (brand + product, e.g. "prestige induction cooktop"). Narrow with `min_price` / `max_price`, `stores` or `category_ids` when the user gives them; `sort: "price_asc"` for lowest price first.
2. **Pick 2–4 genuine matches** — same model and variant, in stock (`outOfStock: false`); skip cases, covers and other accessories unless asked.
3. **Compare** → `compare_products` with their ids. It adds rating, discount from MRP and how close each is to its own lowest recorded price.
4. **Show cards for the shortlist** → the search results already appear as cards; to show only the 2–4 compared products, call `render_product_results` with their `ids`, a short `title` and `search_query` (the search you ran) so the cards link to all results on CheapestInIndia (e.g. "Prestige induction cooktops across stores").

Rules:
- Never invent products, prices or links; pass tool output through unchanged.
- Cards show recent price changes (↑/↓) and "Lowest ever" — you may mention them; they describe the past, not the future.
- Buy links (`productUrl`) go through CheapestInIndia to the store's product page; cite `productPageUrl` for price history.
