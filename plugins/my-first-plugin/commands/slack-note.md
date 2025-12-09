---
name: slack-note
description: Send a quick note to your Slack (DM yourself)
argument-hint: "<your note message>"
---

## Mission
Send a quick note to your personal Slack space (DM yourself) using the slack-note-taker agent.

## Usage

Send yourself a reminder or note on Slack.

## Examples

```
/slack-note Remember to review the authentication PR tomorrow
/slack-note TODO: Fix bug in auth middleware, Write tests, Update docs
/slack-note Meeting notes: Discussed API redesign, decided on REST approach
```

## Execution

Please use the slack-note-taker agent to send this note to my Slack:

**Note**: {{arg}}

Format it nicely with appropriate emojis and formatting.