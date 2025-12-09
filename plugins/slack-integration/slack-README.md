# Slack Integration Plugin

Full Slack workspace integration for Claude Code via the official MCP server.

## Features

- 📨 **Send Messages**: Post to any channel or DM
- 📖 **Read Messages**: Access channel history
- 👥 **List Users**: Get workspace members
- 📋 **List Channels**: See all channels
- 💬 **Reply to Threads**: Maintain conversation context
- 😄 **Add Reactions**: React to messages with emojis

## Setup

### 1. Create Slack App

1. Go to https://api.slack.com/apps
2. Click **"Create New App"** → **"From scratch"**
3. Name: `Claude Bot` (or any name)
4. Select your workspace
5. Click **"Create App"**

### 2. Add Bot Token Scopes

In your app settings:
1. Go to **"OAuth & Permissions"**
2. Under **"Bot Token Scopes"**, add:
   - `chat:write` - Send messages
   - `channels:read` - List channels
   - `channels:history` - Read messages
   - `users:read` - See users
   - `im:write` - Send DMs
   - `im:history` - Read DMs

### 3. Install to Workspace

1. Click **"Install to Workspace"**
2. Click **"Allow"**
3. Copy the **Bot User OAuth Token** (starts with `xoxb-`)

### 4. Get Team ID

From your Slack workspace URL:
- Example: `https://app.slack.com/client/T06FS8A20HZ/...`
- Team ID: `T06FS8A20HZ` (the part starting with T)

### 5. Configure Environment Variables

Set these environment variables:

```bash
export SLACK_BOT_TOKEN="xoxb-your-token-here"
export SLACK_TEAM_ID="T06FS8A20HZ"
```

Or add to your shell profile (`~/.zshrc` or `~/.bashrc`):

```bash
echo 'export SLACK_BOT_TOKEN="xoxb-your-token-here"' >> ~/.zshrc
echo 'export SLACK_TEAM_ID="T06FS8A20HZ"' >> ~/.zshrc
source ~/.zshrc
```

### 6. Install the Plugin

```bash
/plugin marketplace update nxg-gg-marketplace
/plugin install slack-integration
```

### 7. Restart Claude Code

The Slack MCP server will be available!

## Usage

Once installed, you can:

### Send Messages

```
"Send a message to #general: Hello team!"
"Post to #engineering: Deployment completed successfully"
```

### Send Direct Messages

```
"Send a DM to myself: Remember to review the PR"
"Message @john: Can you check the auth service?"
```

### Read Messages

```
"Show me the last 10 messages from #engineering"
"What's the latest discussion in #team-updates?"
```

### List Channels

```
"List all Slack channels"
"What channels are available?"
```

### List Users

```
"Show me all users in the workspace"
"Who is in the Slack workspace?"
```

### Reply to Threads

```
"Reply to the latest message in #general with: Great work!"
```

### Add Reactions

```
"Add a 👍 reaction to the last message in #standup"
```

## Combine with Agents

This plugin works great with the `slack-note-taker` agent:

```
"Note to self: Check the database migration status"
```

The agent will automatically use the Slack MCP to send the note!

## Troubleshooting

### "No MCP servers configured"
- Make sure environment variables are set
- Restart Claude Code after setting variables

### "channel_not_found"
- Invite the bot to the channel first
- Use channel ID instead of name

### "not_authed"
- Check your bot token is correct
- Make sure token starts with `xoxb-`

## Security

⚠️ **Keep your bot token secure!**
- Never commit tokens to git
- Use environment variables
- Rotate tokens if compromised

## Available MCP Tools

This plugin provides access to these Slack MCP tools:

- `slack_list_channels` - List all channels
- `slack_post_message` - Send a message to a channel
- `slack_reply_to_thread` - Reply to a message thread
- `slack_add_reaction` - Add emoji reaction
- `slack_get_channel_history` - Read channel messages
- `slack_get_thread_replies` - Read thread messages
- `slack_get_users` - List workspace users
- `slack_get_user_profile` - Get user details

## License

Unlicense