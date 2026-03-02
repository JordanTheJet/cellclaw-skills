# Dating Message
Send messages to matches on dating apps, keep conversations going, and steer toward scheduling a date.

## Category
social

## Trigger
message matches

## Steps
1. Launch the dating app using `app.launch` with app_name="Tinder" (or "Bumble" / "Hinge" if user prefers)
2. Navigate to the matches/conversations tab using `app.automate` action=tap
3. Use `screen.read` to list current matches and active conversations
4. Identify conversations that need a response or new matches that haven't been messaged yet
5. For new matches: use `screen.capture` + `vision.analyze` to review their profile, then compose a personalized opening message referencing something specific from their bio or photos
6. For ongoing conversations: use `screen.read` to read the full conversation history, then draft a natural reply that moves the conversation forward
7. Present the drafted message to the user for approval before sending
8. Once approved, type and send the message using `app.automate` action=type then action=tap on the send button
9. If the conversation is going well (3+ exchanges, positive tone), suggest transitioning to scheduling a date — propose a specific day, time, and activity based on shared interests from the conversation
10. If the match agrees to a date, flag the conversation for the scheduling skill to pick up
11. Track which matches are new, in-progress, and date-ready across all conversations

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
