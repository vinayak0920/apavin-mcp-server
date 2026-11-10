# Apavin MCP tools

Every tool Apavin MCP exposes, as your agent sees it. Input and output schemas: [apavin.com/developers#tools](https://apavin.com/developers#tools).

Tools that send or publish never act on their own: the result is `pending_approval` until a person approves it in Apavin.


## Daily workflow

| Tool | What it does |
|---|---|
| `get_reply_queue` | Every open email and WhatsApp conversation where the customer wrote last and nobody has answered, oldest first. |
| `get_reply_guidelines` | The workspace's own instructions for replies (tone, sign-off, what to always or never say), its public details, and the titles of its knowledge documents. |
| `add_customer_note` | Write a note on the customer's record in Apavin, visible to the team: what they asked for, what was promised, what the team owes them. |
| `create_follow_up_task` | Create a task in Apavin for the team, such as "send the revised quote" or "call back after the demo", optionally tied to a customer and a due time. |
| `get_sent_email_samples` | Recent emails the team sent from a connected mailbox (their own words, quoted replies removed, recipients masked), for learning how they write. |
| `save_voice_profile` | Save the voice profile you wrote from get_sent_email_samples. |

## Email

| Tool | What it does |
|---|---|
| `search_emails` | Search email synced into Apavin from the workspace's connected inboxes. |
| `get_email_thread` | Read every message in one email conversation, oldest first, with the customer it belongs to and the inbox it arrived on. |
| `get_email_message` | Read a single email message in full: headers and body. |
| `summarize_email_thread` | Summarize one email conversation: who is involved, what the customer asked, whether they are waiting on a reply, and the open questions in their last message. |
| `create_email_draft` | Save an email draft. |
| `update_email_draft` | Change the recipient, subject or body of a draft that has not been submitted yet. |
| `send_email` | Submit an email to send from a connected inbox. |
| `schedule_email_follow_up` | Schedule a follow-up email in an existing thread for a future time (5 minutes to 90 days ahead). |
| `get_email_delivery_status` | Status of an email submitted through send_email or schedule_email_follow_up: pending_approval, scheduled, accepted (the mail server took it), failed, denied or cancelled. |

## WhatsApp

| Tool | What it does |
|---|---|
| `search_whatsapp_conversations` | Find WhatsApp conversations by customer name, phone number or words in the messages. |
| `get_whatsapp_conversation` | Read the messages in one WhatsApp conversation, oldest first, with the customer, the number it is on, the reply window and opt-out state. |
| `get_whatsapp_message` | Read a single WhatsApp message and its delivery status. |
| `create_whatsapp_reply_draft` | Save a draft reply for a WhatsApp conversation. |
| `send_whatsapp_reply` | Submit a free-form reply in a WhatsApp conversation. |
| `send_whatsapp_template` | Submit an approved WhatsApp template message, the only kind Meta allows outside the 24 hour window or as a first message. |
| `schedule_whatsapp_follow_up` | Schedule a WhatsApp follow-up for a future time (5 minutes to 90 days ahead). |
| `cancel_scheduled_message` | Cancel an email or WhatsApp message that is waiting for approval or scheduled for later. |
| `get_whatsapp_delivery_status` | Status of a WhatsApp message submitted through Apavin MCP: pending_approval, scheduled, accepted, delivered, read, failed, denied or cancelled, from WhatsApp's own delivery receipts. |

## LinkedIn

| Tool | What it does |
|---|---|
| `get_linkedin_profile` | The connected member's LinkedIn author profile in Apavin: name, the background, business, audience, topics, goals and tone they wrote, their past posts with any results they logged, and the writing playbook. |
| `check_linkedin_post` | Checks a post against Apavin's writing rules: em dashes, machine-sounding phrases, hook length, length, paragraph size, hashtags, links, emojis, specifics and first person. |
| `create_linkedin_post_draft` | Save a LinkedIn post as a draft in Apavin. |
| `publish_linkedin_post` | Submit an original post to publish on the author's own LinkedIn profile. |
| `create_linkedin_image` | Make an image for a LinkedIn post draft from a description, sized for LinkedIn (1200 x 627) and stripped of metadata. |
| `record_linkedin_post_stats` | Save the numbers the author reports for a published post (impressions, reactions, comments, reposts, new followers). |

## Customer context and control

| Tool | What it does |
|---|---|
| `get_customer_context` | Everything Apavin knows about one customer that an agent may see: profile, channels, recent email and WhatsApp conversations, open deals, team notes and remembered facts. |
| `search_customer_conversations` | Search customer conversations on the channels this agent can read (email and WhatsApp), by customer name or message text. |
| `get_business_knowledge` | Find passages in the workspace's approved knowledge base (product information, prices, policies, FAQs uploaded to Apavin). |
| `list_connected_accounts` | The email inboxes and WhatsApp numbers this agent can use, with their connection health. |
| `get_action_permissions` | The permissions this connection has right now, and for each one that is unavailable, why: not granted to this client, switched off by the admin, not in the plan, or the member's role. |
| `get_usage_summary` | Calls used and remaining this month, by tool. |
| `get_recent_action_logs` | Recent outbound actions requested through Apavin MCP and their outcomes: who asked, which account, approval status and result. |

## Background agents

| Tool | What it does |
|---|---|
| `list_background_agents` | The background agents this workspace set up in Apavin (inbox replies, follow-ups, LinkedIn posts, custom jobs), each with its schedule, where it runs, and when it last ran. |
| `start_agent_run` | Start one run of an Apavin background agent. |
| `finish_agent_run` | Record how a run started with start_agent_run went: a report of at most three short lines on what was done and anything a person must do. |
