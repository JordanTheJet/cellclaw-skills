# Shopping
Search for products, compare prices, and make purchases on Amazon or other shopping apps.

## Category
shopping

## Trigger
shop for

## Steps
1. Launch the shopping app using `app.launch` with app_name="Amazon" (or another app if specified)
2. Use `screen.read` to confirm the app is open
3. Tap the search bar and type the product query using `app.automate` action=type
4. Read the search results with `screen.read` — extract product names, prices, ratings, and Prime eligibility
5. If the user wants to compare options, scroll through results with `app.automate` action=scroll direction=down
6. When the user picks a product, tap it to view details
7. Read the product page with `screen.read` for full details (price, reviews, delivery date)
8. Use `screen.capture` + `vision.analyze` if the user wants to see product images
9. If the user wants to buy, guide them through add-to-cart and checkout, confirming before final purchase

## Apps
- Amazon (com.amazon.mShop.android.shopping)
- Walmart (com.walmart.android)
- Target (com.target.ui)
- eBay (com.ebay.mobile)

## Tools
- app.launch
- app.automate
- screen.read
- screen.capture
- vision.analyze
