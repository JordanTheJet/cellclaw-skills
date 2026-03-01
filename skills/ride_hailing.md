# Ride Hailing
Book a ride using Uber, Lyft, or other ride-hailing apps.

## Category
transportation

## Trigger
book a ride

## Steps
1. Get the user's current location using `location.get` for context
2. Launch the ride-hailing app using `app.launch` with app_name="Uber" (or "Lyft" if user prefers)
3. Use `screen.read` to see the current app state
4. If a destination was specified, tap the "Where to?" field and type the destination using `app.automate` action=type
5. Read the screen to see available ride options and prices using `screen.read`
6. Present the options to the user (ride type, estimated time, price)
7. If the user confirms, tap the ride option they want, then tap the confirm/request button
8. Monitor the ride status using heartbeat — set context with `heartbeat.context` to track the ride
9. Use `screen.read` periodically to report driver arrival time and status updates

## Apps
- Uber (com.ubercab)
- Lyft (me.lyft.android)

## Tools
- location.get
- app.launch
- app.automate
- screen.read
- heartbeat.context
