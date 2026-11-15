# CheapestInIndia MCP connector

Shopping search and price tracker for India, packaged as a remote [Model Context Protocol](https://modelcontextprotocol.io) server.

Search 50M+ products with live prices from Amazon, Flipkart, Croma, Reliance Digital, Myntra, Nykaa and other Indian stores. See recent price drops, check price history, compare prices across stores, and research what a product category costs in India.

This repository contains the connector package — the MCP configuration, skills and listing metadata. The server itself is hosted at `https://mcp.cheapestinindia.com/mcp`.

## Connection

| | |
|---|---|
| Endpoint | `https://mcp.cheapestinindia.com/mcp` |
| Transport | Streamable HTTP |
| Authentication | None — read-only and anonymous |
| Documentation | https://mcp.cheapestinindia.com/ |
| Website | https://www.cheapestinindia.com |

Minimal client configuration:

```json
{
  "mcpServers": {
    "cheapestinindia": {
      "url": "https://mcp.cheapestinindia.com/mcp"
    }
  }
}
```

## Tools

| Tool | What it does |
|---|---|
| `search_products` | Search products with live prices, store/category/brand filters and price facets. Returns product cards with price, MRP, discount, store, image and links. |
| `get_product` | Full details for a product id, including available variants. |
| `lookup_product_by_url` | Find a tracked product from a store URL (Amazon, Flipkart, etc.). |
| `browse_categories` | List category groups and sub-categories to browse. |
| `get_price_history` | Price history for a product id or a product name: lowest and highest recorded price, dates, 30-day low, change count. |
| `top_price_drops` | Largest recent price drops overall or in a category, ranked by percentage. |
| `brand_price_drops` | A brand's biggest recent drops, with an optional keyword filter. |
| `sale_events` | Price drops during current store sale events. |
| `market_snapshot` | Price range, median price, and budget / mid-range / premium tiers for a product type. |
| `compare_products` | Compare 2–4 shortlisted products side by side: price, store, discount, rating, distance from lowest recorded price. |
| `render_product_results` | Re-render product cards for a list of product ids. |

## Skills

- `shopping-research` — plan a purchase and shortlist products.
- `check-price-history` — judge whether a price is high or low for the product.
- `compare-prices` — compare the same product across stores.
- `price-drops` — find recent drops overall or in a category.
- `brand-price-drops` — track a brand's recent drops.

## Notes

- The server is read-only: it does not sell products, place orders, or take payments. No account or sign-in is required.
- Prices come from tracked listings and change frequently; check the store before buying.
- Price history and price trends describe past prices only. They are not forecasts.
- Every product links to its price-history page on CheapestInIndia and to the store's product page.

## Links

- Documentation: https://mcp.cheapestinindia.com/
- Privacy: https://www.cheapestinindia.com/privacy-policy
- Terms: https://www.cheapestinindia.com/terms
- Support: https://www.cheapestinindia.com/contact · support@cheapestinindia.com

## License

Connector package and listing metadata: all rights reserved. The hosted service is operated by CheapestInIndia.
