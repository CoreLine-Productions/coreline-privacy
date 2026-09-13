# Privacy Policy — Setuper

**Last updated:** 2026-09-13

Setuper is a Discord bot operated by Coreline Productions. Setuper provides server administration tools — bulk channel and role creation, deletion, category moves, prebuilt layouts, server snapshots, and permission templates — to server administrators who install it. This policy explains what data Setuper stores, why, and how it can be removed.

---

## 1. What Setuper Stores

Server states

Snapshots — full JSON records of a guild's channels and roles, captured only when an administrator runs `/snapshot`. Includes channel names, types, parents, positions, topics, slowmode, NSFW flags, voice limits, bitrates, and role names, colors, hoist and mentionable flags, permission bitfields, and positions.

Creation batches — small JSON records of the IDs and names of channels or roles created in a single bulk action. Used by the Delete by ID panel feature.

Layout exports — JSON files of the guild's current layout, written only when an administrator runs `/export`.

Permission templates — custom templates created with `/template`, stored as JSON on disk. Built-in templates ship with the bot and are not per-guild.

Per-guild configuration — the log channel ID selected with `/setlog`, stored in a small per-guild config file.

No message content is stored, ever.

---

## 2. What Setuper Does Not Store

- General message content from your server
- Presence, activity, or status data
- Direct messages
- Voice data
- Member join or leave history
- User avatars, usernames, or profile data beyond what Discord sends with the interactions Setuper responds to

---

## 3. Message Content

Setuper does not read message content. All functionality is exposed through Discord slash commands and interactive components — buttons, dropdowns, and modals. Setuper never receives the `MessageContent` intent, never listens to message events, and never logs what users type in channels. The only text Setuper sees is what an administrator types into a slash-command modal field, which is used immediately to perform the requested action and is not stored beyond what that action writes to disk (channel names, role names, and similar).

---

## 4. Why Setuper Needs Each Permission

Setuper is guild-scoped and only responds to members holding the Administrator permission. It requests the following gateway intents:

- **Guilds** — required to receive slash commands and interaction events, and to read the guild's channels and roles so they can be displayed in dropdowns and audited.
- **GuildMembers** — required for Discord's interaction permission checks and to verify the caller holds Administrator.
- **GuildMessages** — required only so Setuper can post into the log channel an administrator explicitly selects with `/setlog`.

Setuper does not request and never receives `MessageContent`, `GuildPresences`, `GuildVoiceStates`, or any intent outside the three listed.

The bot's Discord permission set is limited to Manage Channels, Manage Roles, Manage Messages, Send Messages, Embed Links, Read Message History, and View Channels. Setuper does not request Administrator, Kick, Ban, or Mention Everyone.

---

## 5. Data Retention

Snapshots stay on disk until the operator deletes them or the guild's data is wiped. They are not pruned automatically.

Creation batches are deleted immediately after a successful Delete by ID run, or remain on disk indefinitely if never used.

Exports stay on disk until the operator deletes them.

Per-guild configuration is overwritten on every change and removed when the guild's data is wiped.

Log entries live only in the log channel's message history, governed by Discord's own retention.

All data is stored locally on the bot's host machine. Nothing is stored in a cloud service, external database, or third-party system.

---

## 6. Data Deletion

To request deletion of a guild's data, contact **hadtoberxr@gmail.com** or join the support server at **https://discord.com/invite/vEcVsGmmBn**.

Server administrators can also delete data directly at any time by removing the relevant files under `backups/snapshots/`, `backups/exports/`, `backups/creations/`, or `backups/templates/`, or by running `/clearlog` to remove the log channel config. A full guild wipe removes all files prefixed with the guild's ID under `backups/`. Requests made via email or the support server are actioned within seven days.

---

## 7. Third Parties

Setuper does not share data with any third party. It communicates only with the Discord API to receive interactions and respond to them. There is no analytics service, no telemetry, no external database, no outbound webhook, and no data broker involved.

If a third-party service is added in the future, this section will be updated before that service is enabled.

---

## 8. Children

Setuper is intended for use in communities that comply with Discord's Terms of Service. It is not directed at children under 13.

---

## 9. Changes

This policy may be updated. The date at the top of this page reflects the last revision.

---

## 10. Contact

For questions, data access requests, or deletion requests, contact:

**hadtoberxr@gmail.com** ||
**https://discord.com/invite/vEcVsGmmBn**

---

© Coreline Productions
