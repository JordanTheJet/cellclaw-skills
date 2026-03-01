# Food Ordering
Order food delivery from DoorDash, UberEats, or other food delivery apps.

## Category
food

## Trigger
order food

## Steps
1. Get the user's current location using `location.get` to ensure delivery address is correct
2. Launch the food delivery app using `app.launch` with app_name="DoorDash" (or "Uber Eats" if user prefers)
3. Use `screen.read` to see the current app state (home screen, restaurants list)
4. If the user wants a specific restaurant or cuisine, use the search function: tap search, type the query with `app.automate` action=type
5. Read the search results with `screen.read` and present options to the user
6. When the user picks a restaurant, tap it to open the menu
7. Read the menu items with `screen.read`, scroll if needed with `app.automate` action=scroll direction=down
8. Add items the user wants by tapping on them
9. Navigate to cart/checkout and read the order summary with `screen.read`
10. Present the total price and estimated delivery time to the user for confirmation before placing the order

## Apps
- DoorDash (com.dd.doordash)
- Uber Eats (com.ubercab.eats)
- Grubhub (com.grubhub.android)

## Tools
- location.get
- app.launch
- app.automate
- screen.read
- screen.capture
- vision.analyze
