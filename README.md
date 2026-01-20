# Mini Ecommerce Store (Next.js, in-memory)

This project implements a minimal ecommerce store with in-memory storage.

Features:
- Add items to cart
- Checkout with optional discount code
- Every Nth order generates a 10% coupon for the user
- Admin APIs to generate discount (when condition met) and view stats

Run:

1. Install dependencies

```bash
npm install
```

2. Run dev server

```bash
npm run dev
```

3. Run tests

```bash
npm test
```

APIs:
- POST /api/cart/add -> { userId, item }
- POST /api/cart/checkout -> { userId, couponCode? }
- POST /api/admin/generate-discount -> create coupon if orderCount % N == 0
- GET /api/admin/stats -> returns order and coupon stats

Notes:
- Uses an in-memory store in `lib/store.js`. Set `ORDER_N` env var to change every-nth behaviour (default 3).
