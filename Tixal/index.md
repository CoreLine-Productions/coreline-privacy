# Privacy Policy — Tixal

**Last updated:** 2026-09-15

Tixal is a Discord bot operated by Coreline Productions. Tixal provides a ticket management system for Discord servers — panels, private ticket channels, staff claims, transcripts, ratings, staff statistics, blacklists, notes, and reminders. This policy explains what data Tixal stores, why, and how it can be removed.

---

## 1. What Tixal Stores

Tixal stores only the data required to run its ticket system. Nothing else.

**Ticket metadata** — For every ticket opened, Tixal records the ticket channel ID, the opener's Discord user ID, the open timestamp, the close timestamp, the current priority level, internal staff notes attached to the ticket, and the full claim history (who claimed, when, and who unclaimed).

**Discord user IDs** — Tixal stores the Discord user IDs of anyone who opens a ticket, claims a ticket, is added to a ticket, interacts with ticket controls, or is mentioned inside a ticket's metadata (staff notes, blacklist entries, rating submissions).

**Staff statistics** — Per staff member, per guild: tickets claimed, tickets closed, tickets opened, and the list of ratings received (each rating is a 1-to-5 score tied to a ticket and a staff user ID).

**Blacklist entries** — Users or roles that admins have blacklisted from opening tickets. Each entry records the target ID, whether it is a user or a role, the reason text if one was provided, the timestamp, the blacklisting admin's ID, and — for temporary blacklists — the expiry timestamp. Blacklist history is kept per target.

**Panel configurations** — Every panel an admin creates: title, description, image URL, thumbnail URL, footer text, embed color, and the list of buttons on that panel. Each button stores its label, emoji, style, the modal question it asks, the target support role, and any per-button embed override.

**Per-user staff notes** — Permanent notes attached to a user ID by staff, including the note text, author user ID, and timestamp. These are shown to staff when the noted user opens a new ticket.

**Reminders** — Reminders set on a ticket, including the target duration, the staff member who set it, and the ticket it is attached to.

**Guild configuration** — Support role IDs, admin role IDs, audit log channel ID, transcript log channel ID, rating channel ID, auto-close on/off state, auto-close duration, per-user ticket limits, and per-user creation cooldowns.

**Transcripts** — When a ticket is closed, Tixal generates an HTML transcript of the channel's messages and uploads it as a file attachment to the configured transcript log channel. Tixal does not store the transcript on its own servers. The file lives only as a Discord attachment.

No message content is stored outside of ticket transcripts, which are generated on close and immediately uploaded to Discord.

---

## 2. What Tixal Does Not Store

- General message content from any channel outside of ticket transcripts
- Presence, activity, or status data
- Direct messages
- Voice data
- Email addresses, IP addresses, or any data collected outside Discord
- User avatars, usernames, or profile data beyond what Discord sends with the interactions Tixal responds to

---

## 3. Message Content

Tixal is slash-command and component driven. It does not receive the `MessageContent` intent and does not read messages in normal channels.

The single exception is ticket channels. Inside a ticket channel, Tixal reads messages **only at the moment the ticket is closed**, to build the transcript. That read is one-shot: the messages are compiled into an HTML file and uploaded as a Discord attachment to the transcript log channel. Tixal does not retain the message content after the transcript is uploaded.

The text an administrator types into a slash-command modal — panel titles, button labels, ticket questions, blacklist reasons, staff notes — is stored because it is required to operate the feature the admin configured.

---

## 4. Why Tixal Needs Each Permission

Tixal is guild-scoped and only responds to members holding configured admin or support roles. It requests the following gateway intents:

- **Guilds** — required to receive slash commands and interaction events, and to read guild channels and roles so they can be shown in dropdowns and used for permission checks.
- **GuildMembers** — required to resolve member roles for admin and support checks, and to apply roles when needed.
- **GuildMessages** — required to read messages inside a ticket channel at the moment the ticket is closed, so the transcript can be built.
- **MessageContent** — **not requested**. Tixal does not receive message content in any channel it is not actively transcribing at close time.
- **Presence** — **not requested**.

The bot's Discord permission set is limited to:

- **View Channels**, **Send Messages**, **Embed Links**, **Read Message History** — for panel rendering, ticket channels, and log channels
- **Manage Channels** — for creating, renaming, locking, unlocking, and deleting ticket channels
- **Manage Roles** — for permission overwrites on ticket channels
- **Manage Messages** — for editing ticket embeds and managing messages inside tickets
- **Mention Everyone** — only if a reminder fires and needs to ping a role

Tixal does not request Administrator, Kick, Ban, or any moderation permission.

---

## 5. Data Retention

Ticket metadata, staff statistics, ratings, staff notes, blacklist entries, panel configurations, reminders, and guild configuration are retained until a server admin removes the bot or requests deletion.

Closed tickets retain their metadata — opener, claim history, priority, notes, close time — for staff statistics and reporting. The ticket channel itself is deleted on close.

Transcripts are retained by Discord, in the transcript log channel, according to that channel's own message retention. Tixal does not keep a copy.

Automatic pruning runs on any expired temporary blacklist entries. Nothing else is pruned automatically.

---

## 6. Data Deletion

Server administrators can delete data directly at any time:

- **Delete ticket metadata** — close the ticket and purge it through the ticket management menu.
- **Delete staff statistics** — remove the bot and re-add it, or request a full wipe via the contact info below.
- **Delete a rating** — ratings are attached to tickets; deleting the associated ticket data removes the rating.
- **Delete a blacklist entry** — use the blacklist management menu in the admin panel.
- **Delete staff notes** — use the notes management menu.
- **Delete a panel** — use the panel editor.
- **Delete a reminder** — cancel it from the ticket.

Full deletion requests are actioned within seven days. Contact:

**hadtoberxr@gmail.com**
**https://discord.com/invite/vEcVsGmmBn**

---

## 7. Third Parties

Tixal does not share data with any third party. It communicates only with the Discord API to receive interactions and respond to them. There is no analytics service, no telemetry, no external database, no outbound webhook, and no data broker involved.

---

## 8. Children

Tixal is intended for use in communities that comply with Discord's Terms of Service. It is not directed at children under 13.

---

## 9. Changes

This policy may be updated. The date at the top of this page reflects the last revision.

---

## 10. Contact

For questions, data access requests, or deletion requests, contact:

**hadtoberxr@gmail.com**
**https://discord.com/invite/vEcVsGmmBn**

---

© Coreline Productions
