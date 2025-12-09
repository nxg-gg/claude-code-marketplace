---
name: slack
description: Send a message to Slack (to yourself, others, or channels)
argument-hint: "<destination> <message>"
---

## Mission
Send messages to Slack via Claude Bot. Messages can go to yourself, other users, or channels.

## Usage

Simple format: destination then message

```
/slack <where> <message>
```

## Destination Options

- **me** or **myself** = Send to yourself (Issa Al-Halabi)
- **@username** = Send to another user
- **#channel** = Send to a channel
- **FirstName** or **Full Name** = Send to that person

## Examples

### Send to Yourself
```
/slack me Check the deployment logs
/slack myself Don't forget to review the PR
/slack me TODO: Fix auth bug, Write tests, Deploy
```

### Send to Channels
```
/slack #engineering Deployment completed successfully ✅
/slack #general Team meeting in 10 minutes
/slack #backend-deployments New API version live
```

### Send to Other Users
```
/slack @john Can you review my PR?
/slack John Can you help with this bug?
/slack Sarah The feature is ready for testing
```

## Execution

Use the slack-messenger agent to send this message:

{{arg}}

Agent instructions:
1. Parse the destination from the first word(s)
2. The rest is the message content
3. If destination is "me" or "myself": send to Issa Al-Halabi (U09QUCHGYR3)
4. If destination starts with @: look up that user and send to them
5. If destination starts with #: send to that channel
6. If destination is a name: look up that user and send to them

Keep it simple and send the message!