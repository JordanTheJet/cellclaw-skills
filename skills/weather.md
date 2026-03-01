# Weather Check
Get the current weather and forecast for your location or any city.

## Category
utilities

## Trigger
weather

## Steps
1. Get the user's current location using `location.get` with geocoding enabled
2. Use `browser.search` to search for weather at that location (e.g. "weather in [city]")
3. Parse the search results for current temperature, conditions, and forecast
4. If the user asked about a specific city, search for that city instead
5. Present a concise weather summary with current conditions and today's forecast

## Apps
- Weather (com.google.android.apps.weather)

## Tools
- location.get
- browser.search
