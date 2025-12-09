---
name: slack-post
description: Post a message to a Slack channel
argument-hint: "<channel> <message>"
---

## Mission
Post a message to a specific Slack channel using the slack-note-taker agent.

## Usage

Post messages to Slack channels for team updates, notifications, or announcements.

## Format

```
/slack-post #channel-name Your message here
/slack-post @username Your DM message here
```

## Examples

```
/slack-post #engineering Deployment completed successfully ✅
/slack-post #general Team meeting in 10 minutes
/slack-post #team-updates Sprint planning finished, tickets are ready
/slack-post @john Can you review the PR when you get a chance?
```

## Execution

Please use the slack-note-taker agent to post this message to Slack:

{{arg}}

Parse the channel/user from the first word (starting with # or @) and send the rest as the message.
Format it appropriately with emojis and good formatting.