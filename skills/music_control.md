# Music Control
Play, pause, skip, or search for music on Spotify, YouTube Music, or other music apps.

## Category
entertainment

## Trigger
play music

## Steps
1. If the user asked for a specific song/artist/playlist, launch the music app using `app.launch` with app_name="Spotify" (or "YouTube Music" based on what's installed)
2. Use `screen.read` to see the current state of the music app
3. If a specific song/artist was requested, tap the search icon, type the query with `app.automate` action=type, then tap the first result
4. For play/pause/skip commands, use `app.automate` to tap the corresponding button visible on screen
5. If no music app is in the foreground, use `notification.listen` to check if music is playing in the background and control it via notification media controls
6. Confirm the action was successful by reading the screen again

## Apps
- Spotify (com.spotify.music)
- YouTube Music (com.google.android.apps.youtube.music)
- Apple Music (com.apple.android.music)

## Tools
- app.launch
- app.automate
- screen.read
- notification.listen
