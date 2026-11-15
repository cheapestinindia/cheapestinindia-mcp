---
name: check-price-history
description: Judge whether a product's current price in India is good, using CheapestInIndia's recorded price history. Use when the user asks "is this a good price", "was it cheaper before", "what is the lowest price", or pastes an Amazon, Flipkart or other Indian store product link.
---

# Check a price against its history

1. **Get the history in one step.**
   - User pasted a store link → `lookup_product_by_url` with the link (it includes the history).
   - Otherwise → `get_price_history` with `query` set to the product name (model numbers help, e.g. "jbl flip 6"). It picks the best-matching listing and returns `otherListings`.
2. **Check the match.** If the matched listing isn't the exact product or store the user means, call `get_price_history` again with the right `id` from `otherListings`, or ask the user which one. For a broad request ("samsung tv"), show the options and ask which model.
3. **Answer factually** from the result: current price, lowest and highest recorded price with dates, the 30-day low, and how today's price compares (the tool's verdict, e.g. "within 2.6% of the lowest recorded price").
4. Link the `productPageUrl` (CheapestInIndia price-history page with the full chart) and the `productUrl` to buy.

Rules:
- Never predict future prices or say "wait, it will drop". History describes the past only; say so if asked to forecast.
- Only use numbers the tools returned. Prices are INR and can change quickly; mention the store.
- If `lookup_product_by_url` says the product is not tracked, search by name instead.
