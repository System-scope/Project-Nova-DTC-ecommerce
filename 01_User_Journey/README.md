## User Journey Overview

This section outlines the end-to-end customer journey across the platform, covering discovery, purchase, and post-purchase lifecycle.

---

## Journey Flow

Homepage → Product Listing → Product Detail → Cart → Authentication → Checkout → Payment → Confirmation → Order Tracking → Returns

---

## 1. Homepage (Landing Page)

### Overview

The homepage serves as the primary entry point for users, enabling product discovery, category navigation, and promotional engagement.

---

### Wireframe

![Homepage](homepage.png)
---

### UI Components

- Top navigation bar:
  - Logo (NOVA)
  - Category links (Men, Women, Apparel, Footwear, Accessories)
  - Search
  - Wishlist icon
  - Cart icon
  - Login / Signup

- Hero banner (carousel)

- Featured section
  - Highlighted categories/products
  - "Shop All" CTA

- Shop by Sport section
  - Category navigation (Running, Training, Badminton)

- Best Sellers section
  - Popular products with pricing

- Newsletter signup

- Footer (policies, returns, contact)

---

### System Behavior

- Navigation redirects to respective listing pages
- Search enables keyword-based discovery
- Product clicks navigate to PDP
- Wishlist and cart icons reflect real-time counts
- Carousel supports manual/auto navigation

---

### Business Logic

- Featured and Best Sellers are driven by:
  - Sales performance
  - Merchandising rules
- Categories map to predefined taxonomy
- Newsletter captures user emails

---

### Edge Cases

- No featured products → fallback content
- Search returns no results → empty state page
- Broken product links → fallback handling
- Cart/wishlist sync issues
- Slow banner load → static fallback

---

### Product Thinking

- Drives discovery and engagement
- Uses visual hierarchy to guide users
- Highlights high-performing products to boost conversion
- Reduces friction via quick navigation
- ---

## 2. Product Listing Page (PLP)

### Overview

The Product Listing Page (PLP) displays a collection of products based on selected category, search query, or applied filters. It enables users to browse, refine, and compare products efficiently before proceeding to product detail.

---

### Wireframe

![PLP](plp.png)

---

### UI Components

**Top Section:**
- Category title (e.g., NOVA Sportswear)
- Product count (e.g., Showing 1003 products)
- Sort dropdown (Popular, Price Low to High, Price High to Low, Newest)

**Filter Panel (Left):**
- Gender
- Size
- Rating
- Brand
- Price range
- Availability
- Clear filters option

**Product Grid:**
- Product image
- Product name
- Price
- Ratings
- Wishlist icon

**Pagination / Load More:**
- "Load more products" CTA

---

### System Behavior

- Default sorting applied (e.g., Popular)
- Filters dynamically update product list
- Multiple filters can be applied simultaneously
- Filter state persists during session
- Wishlist updates in real-time
- Clicking product navigates to PDP
- Load more fetches next set of products

---

### Business Logic

- Product listing is driven by:
  - Category taxonomy
  - Search query
  - Filter conditions
- Sorting logic:
  - Popular → based on sales/engagement
  - Price → ascending/descending
- Inventory-aware display:
  - Out-of-stock items may be hidden or deprioritized
- Ratings aggregated from user reviews

---

### Key Validations

- Filter combinations should return valid product sets
- Invalid filter combinations → show empty state
- Sorting should not break filter logic
- Price filters must respect min/max constraints

---

### Edge Cases

- No products available → show empty state with suggestions
- Filters result in zero products
- Network delay → loading skeleton UI
- Product image fails → fallback image
- Wishlist sync delay
- Large product sets → performance handling (pagination/lazy load)

---

### Product Thinking

- Enables efficient product discovery and comparison
- Reduces cognitive load using filters and sorting
- Drives conversion by surfacing relevant products
- Prevents drop-offs through clear navigation and feedback
- Supports scalability with large product catalogs
