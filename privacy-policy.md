---
title: Privacy Policy
permalink: /privacy-policy/
---

# Privacy Policy

**Palmon Bot** — a Discord bot for *Palmon: Survival* communities.

Last updated: 25 September 2026

This policy explains what Palmon Bot stores, why, where it lives, and how to
have it removed. The short version: it stores Discord ID numbers and the
settings your server chose, and nothing else about you.

## Who is responsible

Palmon Bot is self-hosted. The person running it — referred to here as "the
operator" — is the data controller for everything described below. How to reach
them is at the end.

## What the bot stores

Everything the bot keeps lives in a single SQLite database file on the machine
the operator runs it on. It consists of:

| What | Why it is kept |
| --- | --- |
| **Discord user IDs** (numeric snowflakes) of whoever added, re-dated or revoked a gift code, and of whoever changed a setting | So the bot can show who did it — `/codes` credits the person who added a code, `/settings` shows who changed a setting |
| **Server (guild) IDs** | To keep each server's settings and announcements separate from every other server's |
| **Channel IDs** you configure | So the bot knows where to post announcements |
| **Setting values** your moderators choose | So your choices survive a restart |
| **Gift codes**, their reward text, expiry dates and timestamps | To list codes that are still live, and to avoid announcing the same code twice |
| **Announcement bookkeeping** — which server has been told about which event or code, and when | So a restart does not repost an announcement your channel has already seen |

That is the complete list.

## What the bot does *not* store

- **Message content.** Nothing anyone types is written to the database.
- **Usernames, nicknames, display names, avatars or profile information.** The
  bot stores numeric IDs only, and asks Discord to render them as a mention at
  the moment it posts. If a stored ID were shown to you as a name, that name
  came from Discord just then, not from the bot's records.
- **Email addresses, IP addresses, or any contact details.**
- **Direct messages.** The bot does not read or store DMs.
- **Command history or analytics.** The bot does not record who ran which
  command, or count usage. There is no tracking of any kind.
- **Payment information.** The bot takes no payments, and donations do not pass
  through it — see *Donations* below.

## About the Message Content intent

The bot uses Discord's **Message Content** privileged intent. It is used for
exactly one thing: reading recent messages in the *one* channel a server
configures as its gift-code source, so that official code announcements can be
picked up automatically.

When it reads such a message it extracts the gift code, its expiry date and its
reward text, and discards everything else. **The message body, its author and
its ID are never written to the database.** Messages in every other channel are
ignored entirely, and if no source channel is configured nothing is read at all.

## Where the data lives, and who can see it

The database file sits on a private volume on the operator's own machine. It is
not hosted with a third-party database provider, not backed up to a cloud
service, and not reachable from the internet — the bot opens no inbound ports.

Only the operator can access it.

Data is **never** sold, rented, traded, or shared with any third party. There
are no analytics providers, no advertising networks, and no external APIs
receiving your data. The only service the bot communicates with is Discord
itself, which is unavoidable — see
[Discord's Privacy Policy](https://discord.com/privacy) for how Discord handles
your data.

## Logs

The bot writes short operational log lines — which command was run, which
server it joined, which gift code was ingested, and errors — to its own console
output, where the host retains them for a limited period before they roll over.
These logs are for debugging only, are visible only to the operator, and are not
analysed, aggregated or shared.

## Donations

Donating is optional and has nothing to do with using the bot. If you do donate,
it happens on **Buy Me a Coffee**, not here and not in Discord:

- **Buy Me a Coffee and its payment processor collect and hold whatever the
  payment requires** — typically your name, your email address and your payment
  details — under their own privacy policies, and they are the parties
  processing it. See
  [Buy Me a Coffee's Privacy Policy](https://buymeacoffee.com/privacy-policy).
- **The operator never sees your card or bank details.** What is visible to them
  is the donation itself, and whatever name or message you chose to attach to it,
  in Buy Me a Coffee's own dashboard.
- **Nothing about a donation is written to the bot's database.** No donor list, no
  flag against your Discord account, no email address. The table above is still
  the complete list.
- **A donation is not linked to your Discord identity** unless you volunteer that
  yourself, and the bot has no way to connect the two.

To see or delete what Buy Me a Coffee holds about your donation, contact
Buy Me a Coffee — those records are in their systems, not the operator's, so the
operator cannot delete them, though they will pass a request on.

## How long data is kept

- **Settings and announcement records** are kept for as long as the bot is in
  your server, so that your configuration survives restarts.
- **Gift codes** are kept indefinitely, since the list is a historical record
  of codes and their expiry.

**Removing the bot from your server does not automatically delete rows that
were already stored.** If you want your server's settings and announcement
records erased after removing the bot, ask — see *Your rights* below. Server
settings are attached to your server's ID and have no effect once the bot has
left.

## Your rights

Because the data stored is minimal, you can have it dealt with by asking
directly. You may request:

- **Access** — a copy of everything stored against your Discord user ID or your
  server ID;
- **Erasure** — deletion of those rows;
- **Correction** — a stored value fixed.

Requests are handled manually by the operator, at no charge, as soon as is
practical. Depending on where you live you may have further rights under the
GDPR, the UK GDPR, or similar laws, including the right to complain to your
local data protection authority.

Where a legal basis is required, the basis for the processing described here is
**legitimate interest**: storing which server chose which channel, and who added
which code, is the minimum needed to run the bot at all.

## Children

Discord requires its users to be at least 13 years old, or older where local law
sets a higher age. Palmon Bot is not directed at children below that age and
does not knowingly store data from them. If you believe it has, contact the
operator and the data will be removed.

## Changes to this policy

This policy may change as the bot does. The "last updated" date above will
change with it, and the current version is always the one at this URL. Material
changes to what is stored will be announced in the servers the bot is in.

## Contact

To ask a question, or to request access or erasure: join the bot's Discord server
at [discord.gg/sQXhtHQeWM](https://discord.gg/sQXhtHQeWM) and ask the operator
there. You can also message a moderator in the server where you found the bot,
and they will pass it on.
