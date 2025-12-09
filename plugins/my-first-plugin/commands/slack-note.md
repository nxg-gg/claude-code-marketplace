---
name: slack-note
description: Send a quick note to YOURSELF on Slack (always goes to YOUR DMs only)
argument-hint: "<your note message>"
---

## Mission
Send a personal note or reminder to YOURSELF on Slack. This command ALWAYS sends to YOUR OWN Slack DMs, never to anyone else or any channel.

## Usage

Quick personal notes, reminders, and task lists that go directly to YOUR Slack DMs.

## Examples

```
/slack-note Remember to review the authentication PR tomorrow
/slack-note TODO: Fix bug in auth middleware, Write tests, Update docs
/slack-note Meeting notes: Discussed API redesign, decided on REST approach
/slack-note Don't forget to check the deployment logs before EOD
```

## Execution

IMPORTANT: This note must ONLY go to the current user (Issa Al-Halabi).

Steps for the slack-note-taker agent:
1. Call slack_get_users to get all workspace users
2. Find the user "Issa Al-Halabi" (or username "issa.alhalabi")
3. Extract the user ID (should be U09QUCHGYR3)
4. Send the message ONLY to this user ID as a DM

Message content:

📝 **Note**: {{arg}}

Do NOT ask where to send - always send to Issa Al-Halabi's DMs.