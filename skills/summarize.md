# Summarize
Summarize the content currently on screen, a web page, or text provided by the user.

## Category
productivity

## Trigger
summarize

## Steps
1. If the user provided a URL, open it with `browser.open` then wait briefly and use `screen.read` to get the page content
2. If no URL was provided, use `screen.read` to capture whatever is currently on screen
3. If screen.read returns insufficient text (e.g. image-heavy content), use `screen.capture` + `vision.analyze` to understand the visual content
4. Analyze the content and produce a concise summary with key points
5. If the content is very long (multiple screens), scroll down with `app.automate` action=scroll direction=down, read again, and incorporate additional content before summarizing

## Tools
- screen.read
- screen.capture
- vision.analyze
- browser.open
- app.automate
