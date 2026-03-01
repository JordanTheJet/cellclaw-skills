# Social Media
Check feeds, post content, or reply on social media apps like Instagram, X (Twitter), or TikTok.

## Category
social

## Trigger
social media

## Steps
1. Launch the requested social media app using `app.launch` (default to Instagram if not specified)
2. Use `screen.read` to see the current screen state
3. For checking feeds: scroll through the feed using `app.automate` action=scroll, read content with `screen.read`, use `screen.capture` + `vision.analyze` for image/video posts
4. For posting: navigate to the post creation screen (tap the + or compose button), type the caption with `app.automate` action=type, attach photos if requested using the camera/gallery picker
5. For replying to DMs or comments: navigate to messages/comments, read the conversation, compose and send a reply
6. For searching profiles or content: tap search, type the query, and browse results
7. Always confirm before posting or sending any content (show draft to user first)

## Apps
- Instagram (com.instagram.android)
- X / Twitter (com.twitter.android)
- TikTok (com.zhiliaoapp.musically)
- Facebook (com.facebook.katana)
- Reddit (com.reddit.frontpage)

## Tools
- app.launch
- app.automate
- screen.read
- screen.capture
- vision.analyze
- camera.snap
