# Fitness Tracking
Track workouts, check step counts, log exercises, or start fitness timers using health apps.

## Category
health

## Trigger
fitness

## Steps
1. If checking steps or activity data, launch the health app using `app.launch` with app_name="Google Fit" (or "Samsung Health" based on device)
2. Use `screen.read` to see today's activity summary (steps, calories, distance)
3. If the user wants to start a workout, navigate to the workout section and select the exercise type
4. For logging a manual exercise, find the log/add button and enter the workout details
5. If the user wants sensor data (heart rate via compatible devices), use `sensor.read` to check available sensors
6. Present a summary of the fitness data in a clear format
7. For setting fitness reminders or recurring workout schedules, use `schedule.manage` to create a scheduled prompt

## Apps
- Google Fit (com.google.android.apps.fitness)
- Samsung Health (com.sec.android.app.shealth)
- Strava (com.strava)
- Nike Run Club (com.nike.plusgps)

## Tools
- app.launch
- app.automate
- screen.read
- sensor.read
- schedule.manage
