# Privacy Policy — PrivateTickets

**Last updated:** 2026-09-13

PrivateTickets is a private Discord bot operated by Coreline Productions. It provides ticket support, staff management, and Roblox rank verification for the KTTG and DVNR communities. This policy explains what data PrivateTickets stores, why, and how it can be removed.

---

## 1. What PrivateTickets Stores

PrivateTickets stores the following data on its host server, keyed by Discord guild ID:

- Discord user IDs of users who open, claim, interact with, or are mentioned in tickets
- Ticket channel IDs and ticket metadata — open time, close time, priority, internal notes, claim history
- Staff statistics — claimed ticket counts, closed ticket counts, opened ticket counts, ratings received
- Blacklist entries — user IDs or role IDs explicitly blacklisted by server admins
- Panel configurations — ticket panel titles, descriptions, buttons, and channel targets created by admins
- Roblox usernames and user IDs submitted through rank requests, along with the outcome of each request
- Guild configuration — support roles, admin roles, log channel, rating channel, quota roles, and other admin-set values

## 2. What PrivateTickets Does Not Store

- General message content from your server
- Presence, activity, or status data
- Direct messages
- Voice data
- Email addresses, IP addresses, or any data collected outside Discord

## 3. Message Content

PrivateTickets reads message content only for optional legacy prefix commands — messages that begin with the configured prefix (`!` by default). These messages are processed in memory to determine which command was invoked and are then discarded. They are never written to disk.

When a ticket is closed (manually or by the auto-close timer), PrivateTickets generates a transcript of the last 100 messages in that specific ticket channel and posts it to a staff log channel configured by the server admin. The transcript exists only as a Discord attachment in that log channel. PrivateTickets does not retain the transcript on its host outside of Discord.

Users who use slash commands exclusively never have their message content read.

## 4. Why PrivateTickets Needs Each Permission

- **Server Members Intent** — to resolve roles when checking whether a user can claim a ticket, apply a rank role, or interact with the quota system.
- **Message Content Intent** — to support optional legacy prefix commands. All primary functionality uses slash commands and does not require this intent.
- **Presence Intent** — not used.

## 5. Roblox API

PrivateTickets communicates with the Roblox API for rank verification. When a rank request is submitted, PrivateTickets sends the supplied Roblox username to Roblox to look up the user's ID, group membership, and current rank. No Discord user data is sent to Roblox beyond the username being verified.

PrivateTickets does not share data with any other third party.

## 6. Data Retention

- Ticket metadata and staff statistics are retained until a server admin removes the bot or requests deletion.
- Blacklist entries are retained until removed by a server admin.
- Rating data is retained indefinitely unless removed on request.
- Quota data is retained until the quota completes, fails, or is deleted by an admin.

## 7. Data Deletion

Server admins can remove data by:

- Closing individual tickets via the ticket close button
- Running `/purgetickets` to bulk-close inactive tickets
- Running `/deletequota` to remove quota records
- Running `/ticketblacklist action:Remove` to un-blacklist a user or role

To request full deletion of a guild's data, contact [YOUR CONTACT EMAIL OR DISCORD TAG]. Requests are processed within 30 days.

## 8. Children

PrivateTickets is intended for use in communities that comply with Discord's Terms of Service. It is not directed at children under 13.

## 9. Changes

This policy may be updated. The date at the top of this page reflects the last revision. Continued use of PrivateTickets after an update constitutes acceptance of the updated policy.

## 10. Contact

For questions, data access requests, or deletion requests, contact:

hadtoberxr@gmail.com ||
https://discord.com/invite/vEcVsGmmBn

---

© Coreline Productions
