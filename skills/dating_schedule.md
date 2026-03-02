# Dating Schedule
Schedule confirmed dates into the calendar with time, location, and details from the conversation.

## Category
social

## Trigger
schedule date

## Steps
1. Check for date-ready conversations flagged by the messaging skill, or ask the user which match to schedule with
2. Launch the dating app using `app.launch` and navigate to the relevant conversation
3. Use `screen.read` to review the conversation and extract the agreed-upon details — day, time, activity, and any location mentioned
4. If details are incomplete, draft a message to confirm specifics (e.g., "How about 7pm at that Italian place you mentioned?") and present to user for approval before sending via `app.automate`
5. Once date details are confirmed, use `location.get` and `browser.search` to look up the venue — get the address, hours, and any reservation info
6. If the venue takes reservations, ask the user if they want to book one via `browser.open` or by calling with `phone.call`
7. Create a calendar event using `calendar.create` with the date, time, location, match name, and activity as the description
8. Set a reminder notification 2 hours before the date using `notification.send`
9. Send a confirmation message to the match in the dating app — e.g., "We're all set for Friday at 7!" — after user approval via `app.automate`
10. Use `calendar.query` to check for conflicts before finalizing, and suggest alternatives if there's a clash

## Apps
- Tinder (com.tinder)
- Bumble (com.bumble.app)
- Hinge (co.hinge.app)
- Google Calendar (com.google.android.calendar)

## Tools
- app.launch
- app.automate
- screen.read
- calendar.create
- calendar.query
- location.get
- browser.search
- browser.open
- phone.call
- notification.send
