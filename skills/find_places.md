# Find Places
Find restaurants, shops, gas stations, or any nearby place using Google Maps.

## Category
navigation

## Trigger
find places

## Steps
1. Get the user's current location using `location.get` for context
2. Launch Google Maps using `app.launch` with app_name="Maps"
3. Use `screen.read` to confirm Maps is open
4. Tap the search bar using `app.automate` action=tap text="Search here"
5. Type the user's query (e.g. "Italian restaurants nearby") using `app.automate` action=type
6. Read the search results using `screen.read`
7. Present the top results with names, ratings, and distances
8. If the user wants directions to one, tap on it and then tap the directions button

## Apps
- Google Maps (com.google.android.apps.maps)
- Waze (com.waze)

## Tools
- location.get
- app.launch
- app.automate
- screen.read
