# Smart Home
Control smart home devices like lights, thermostat, locks, and cameras through Google Home, Alexa, or other smart home apps.

## Category
smart-home

## Trigger
smart home

## Steps
1. Launch the smart home app using `app.launch` with app_name="Google Home" (or "Alexa" or "SmartThings" based on user preference)
2. Use `screen.read` to see available devices and their current states
3. For simple commands (turn lights on/off, set thermostat), find the device on screen and tap the toggle or control
4. For specific adjustments (dim lights to 50%, set temperature to 72), tap the device to open its controls, then adjust sliders or input values
5. For scenes/routines (e.g. "movie time", "good night"), navigate to the scenes/routines section and activate the desired one
6. Read the screen to confirm the action was executed successfully
7. If the user wants to check security cameras, navigate to the camera device and use `screen.capture` + `vision.analyze` to describe what the camera shows

## Apps
- Google Home (com.google.android.apps.chromecast.app)
- Amazon Alexa (com.amazon.dee.app)
- Samsung SmartThings (com.samsung.android.oneconnect)

## Tools
- app.launch
- app.automate
- screen.read
- screen.capture
- vision.analyze
