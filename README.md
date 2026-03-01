# CellClaw Skills Registry

Community-contributed skills for [CellClaw](https://github.com/cellclaw/cellclaw), the autonomous AI agent for Android.

Skills are reusable workflows that guide CellClaw's AI agent through multi-step tasks on your phone. They work by providing step-by-step instructions that the agent follows using its built-in tools (app automation, screen reading, browser, etc.).

## Installing Skills

1. Open CellClaw on your phone
2. Go to **My Skills** > tap the **Store** icon
3. Browse skills by category
4. Tap **Install** on any skill you want

Installed skills appear in your **My Skills** list and are immediately available to the agent.

## How Skills Work

Skills are markdown files with a simple format. When you say something that matches a skill's trigger phrase, the agent reads the full skill instructions and follows the steps.

For example, saying "book a ride to the airport" triggers the **Ride Hailing** skill, which tells the agent to launch Uber, enter the destination, show you price options, and monitor the ride with the heartbeat system.

The agent uses CellClaw's tools to execute each step:
- `app.launch` / `app.automate` — Open and interact with any Android app
- `screen.read` — Read text and UI elements on screen
- `screen.capture` + `vision.analyze` — Understand visual content (images, charts, photos)
- `browser.search` / `browser.open` — Web search and browsing
- `location.get` — GPS location
- `heartbeat.context` — Monitor long-running tasks in the background

## Skill Format

```markdown
# Skill Name
Description of what this skill does.

## Category
category-tag

## Trigger
trigger phrase

## Steps
1. First step using `tool.name`
2. Second step
3. Continue until done

## Apps
- App Name (com.package.name)

## Tools
- tool.name
- other.tool
```

### Sections

| Section | Required | Description |
|---------|----------|-------------|
| `# Name` | Yes | Skill name (shown in the store) |
| Description | Yes | What the skill does (1-2 sentences) |
| `## Category` | No | Category tag for filtering (e.g. utilities, navigation, entertainment) |
| `## Trigger` | Yes | Phrase that activates the skill (e.g. "weather", "play music") |
| `## Steps` | Yes | Numbered steps the agent follows. Reference tools with backtick syntax. |
| `## Apps` | No | Android apps used, with package names in parentheses |
| `## Tools` | No | CellClaw tools referenced in the steps |

### Available Tools

| Tool | Description |
|------|-------------|
| `sms.read` / `sms.send` | Read and send SMS messages |
| `phone.call` / `phone.log` | Make calls, read call history |
| `contacts.search` / `contacts.add` | Search and add contacts |
| `calendar.query` / `calendar.create` | Read and create calendar events |
| `screen.read` | Read text and UI elements from the screen |
| `screen.capture` | Take a screenshot |
| `vision.analyze` | Analyze an image using AI vision |
| `camera.snap` / `camera.record` | Take photos or record video |
| `file.read` / `file.write` / `file.list` | File operations |
| `clipboard.read` / `clipboard.write` | Clipboard operations |
| `location.get` | Get GPS location with optional geocoding |
| `sensor.read` | Read device sensors |
| `notification.send` / `notification.listen` | Send and monitor notifications |
| `browser.open` / `browser.search` | Open URLs and search the web |
| `email.send` | Send email |
| `settings.get` | Read device settings (battery, wifi, etc.) |
| `script.exec` | Run shell scripts |
| `app.launch` | Launch any Android app |
| `app.automate` | Tap, type, scroll, swipe in any app |
| `app.install` | Install apps from Play Store |
| `heartbeat.context` | Monitor long-running background tasks |
| `schedule.manage` | Create scheduled/recurring tasks |
| `skill.read` | Read full skill instructions (used internally) |

## Contributing

1. Fork this repo
2. Create your skill as a `.md` file in the `skills/` directory
3. Add an entry to `index.json`
4. Submit a pull request

### Guidelines

- Keep skills focused on a single task or workflow
- Write clear, numbered steps that reference specific CellClaw tools
- Include the Android package names for any apps your skill uses
- Test your skill by adding it manually in CellClaw before submitting
- Don't include skills that require root access or ADB

### Categories

Use one of these categories, or propose a new one:

`utilities` `productivity` `navigation` `entertainment` `transportation` `food` `social` `shopping` `health` `smart-home` `communication` `finance` `education` `gaming`

## License

MIT
