---
name: slack-post
description: Post a message to a Slack channel OR send to another person
argument-hint: "<#channel or @person> <message>"
---

## Mission
Post a message to a Slack channel (#channel-name) OR send a direct message to another person (@username). This command is for TEAM communication, not for personal notes.

## Usage

Send messages to:
- Public/private channels (#engineering, #general, etc.)
- Other team members (@john, @sarah, etc.)
- NOT for yourself (use /slack-note for personal notes)

## Format

```
/slack-post #channel-name Your message here
/slack-post @username Your message here
/slack-post @FirstName LastName Your message here
```

## Examples

```
/slack-post #engineering Deployment completed successfully ✅
/slack-post #general Team meeting in 10 minutes
/slack-post #backend-deployments New API version deployed to production
/slack-post @john Can you review the PR when you get a chance?
/slack-post @sarah The bug fix is ready for testing
```

## Execution

Please use the slack-note-taker agent to post this message:

{{arg}}

Agent instructions:
1. Parse the FIRST word to identify the destination:
   - If it starts with #: It's a channel → send to that channel
   - If it starts with @: It's a person → look up their user ID and send DM
2. The REST of the text is the message content
3. If sending to a person (@username):
   - Call slack_get_users to find them
   - Match by display_name, real_name, or username
   - Get their user ID
   - Send the message to that user ID
4. If sending to a channel (#channel-name):
   - Send directly to the channel

Format the message appropriately with emojis and good formatting.

IMPORTANT: If the user tries to send to themselves, remind them to use /slack-note instead.