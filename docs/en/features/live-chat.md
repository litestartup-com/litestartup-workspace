---
title: Live Chat
description: Real-time chat widget for customer support on your website powered by LiteStartup.
---

# Live Chat

> Real-time chat widget for customer support on your website.

Live Chat allows you to communicate with website visitors in real-time, providing instant support and improving customer satisfaction.

## Getting Started

1. Go to **Applications > Live Chat** from the sidebar
2. Configure your chat widget settings
3. Add the widget code to your website
4. Start chatting with visitors

## Setting Up Live Chat

### Configure Widget

1. Go to **Applications > Live Chat** → **Settings**
2. Customize appearance:
   - **Widget color** - Button and header color
   - **Widget title** - Chat window title
   - **Welcome message** - Greeting shown when widget opens
   - **Offline message** - Message when no agents available
   - **Require email** - Whether to collect visitor email
3. Click **Save**

### Install Widget

Add the widget code to your website:

1. Go to **Applications > Live Chat** → **Settings**
2. Copy the widget embed code provided
3. Paste the code before the closing `</body>` tag on your website

> **Note**: Each domain has a unique widget key. Make sure to use the correct embed code for your domain.

## Managing Chat Sessions

### View Active Chats

1. Go to **Applications > Live Chat** → **Sessions**
2. See all active and recent chat sessions
3. Filter by status: `active`, `closed`

### Chat with Visitors

1. Click on an active session
2. View conversation history
3. Type your response
4. Send message

### Session Information

Each chat session shows:

- Visitor name (if provided)
- Visitor email (if provided)
- Session status
- Unread message count
- Last message preview
- Session start time

## Chat Features

### Assign Sessions

Assign chats to specific team members:

1. Open a chat session
2. Click **Assign**
3. Select team member
4. Session is transferred

### Close Sessions

End a chat session:

1. Open the chat session
2. Click **Close Session**
3. Session moves to closed status

### Convert to Ticket

Turn a chat into a support ticket for follow-up:

1. Open the chat session
2. Click **Convert to Ticket**
3. A new ticket is created with chat history

## Widget Settings

| Setting | Description |
|---------|-------------|
| Widget Color | Widget button and header color |
| Widget Title | Chat window title text |
| Welcome Message | Greeting shown when widget opens |
| Offline Message | Message shown when no agents are available |
| Require Email | Whether visitors must provide email before chatting |
| Auto-open | Automatically open widget after delay |
| Sound | Play sound for new messages |
| Pre-chat form | Collect visitor info before chat |

## API Access

Manage chat sessions programmatically:

- [List Sessions](api/chat-sessions-list.md)
- [Get Session](api/chat-session-get.md)
- [Send Message](api/chat-send-message.md)
- [Close Session](api/chat-close-session.md)
- [Assign Session](api/chat-assign-session.md)
- [Convert to Ticket](api/chat-convert-to-ticket.md)

## Best Practices

- **Respond quickly** - Aim for under 1 minute response time
- **Be helpful** - Provide clear, actionable answers
- **Use canned responses** - Save time with pre-written replies
- **Follow up** - Convert complex issues to tickets
- **Set expectations** - Use offline message when unavailable