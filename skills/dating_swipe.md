# Dating Swipe
Swipe through profiles on dating apps like Tinder, Bumble, or Hinge based on user preferences.

## Category
social

## Trigger
swipe dating

## Steps
1. Ask the user which dating app to use and any preferences (age range, distance, deal-breakers)
2. Launch the dating app using `app.launch` with app_name="Tinder" (or "Bumble" / "Hinge" if user prefers)
3. Use `screen.read` to check the current app state and navigate to the swipe/discover screen
4. Use `screen.capture` + `vision.analyze` to see the current profile — read photos, bio, prompts, and key details
5. Evaluate the profile against user preferences and present a quick summary (name, age, bio highlights, photo impression)
6. If the user has set auto-preferences, swipe right using `app.automate` action=swipe direction=right for matches or left to pass
7. If manual mode, ask the user before each swipe and wait for their decision
8. After swiping, use `screen.read` to check for a match notification
9. If a match is detected, notify the user and ask if they want to send an opening message immediately
10. Continue cycling through profiles, keeping count of swipes, matches, and passes

## Apps
- Tinder (com.tinder)
- Bumble (com.bumble.app)
- Hinge (co.hinge.app)

## Tools
- app.launch
- app.automate
- screen.read
- screen.capture
- vision.analyze
