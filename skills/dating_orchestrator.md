# Dating Orchestrator
Autonomous dating assistant that rotates between swiping, messaging, and scheduling using heartbeat to keep all conversations moving forward.

## Category
social

## Trigger
dating autopilot

## Steps
1. Ask the user for their dating preferences: which apps to use, swipe preferences, conversation style, and availability for dates
2. Initialize the orchestrator loop by setting context with `heartbeat.context` — store the current phase (swipe, message, or schedule), active app, match statuses, and conversation states
3. **SWIPE PHASE**: Load the dating swipe skill using `skill.read` with skill="dating_swipe" — spend a rotation swiping through profiles, tracking new matches
4. After the swipe rotation (roughly 10-15 profiles or a set time), use `heartbeat.context` to log new matches found and transition to the next phase
5. **MESSAGE PHASE**: Load the dating message skill using `skill.read` with skill="dating_message" — cycle through all active conversations, prioritizing: (a) new matches needing an opener, (b) conversations waiting for a reply, (c) warm conversations ready to propose a date
6. After messaging, use `heartbeat.context` to update conversation statuses — mark which are new, active, stale, or date-ready — then transition to the next phase
7. **SCHEDULE PHASE**: Load the dating schedule skill using `skill.read` with skill="dating_schedule" — for any conversations where a date has been agreed upon, create calendar events, look up venues, and send confirmations
8. After scheduling, use `heartbeat.context` to log completed dates and clear them from the active queue
9. Use `calendar.query` to check the user's availability before proposing any new dates in future message rotations
10. **ROTATE**: Return to step 3 and continue the swipe → message → schedule loop — `heartbeat.context` persists state across rotations so no context is lost
11. At each phase transition, use `notification.send` to give the user a brief status update: "3 new matches, 2 conversations replied, 1 date scheduled for Friday"
12. If the user interrupts or sends a command, pause the loop, handle the request, then resume from the current phase using the state stored in `heartbeat.context`
13. Use `schedule.manage` to set up recurring runs if the user wants the orchestrator to activate on a schedule (e.g., every evening at 8pm)

## Apps
- Tinder (com.tinder)
- Bumble (com.bumble.app)
- Hinge (co.hinge.app)
- Google Calendar (com.google.android.calendar)

## Tools
- heartbeat.context
- skill.read
- app.launch
- app.automate
- screen.read
- screen.capture
- vision.analyze
- calendar.create
- calendar.query
- notification.send
- schedule.manage
- location.get
- browser.search
