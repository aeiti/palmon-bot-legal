# palmon-bot-legal

Public policy documents for **Palmon Bot**, an unofficial Discord bot for
*Palmon: Survival* communities.

They live in their own public repository because the bot's source repository is
private, and Discord's application settings and verification review need URLs
that anyone can open.

| Document | Published at |
| --- | --- |
| [Terms of Service](terms-of-service.md) | <https://aeiti.github.io/palmon-bot-legal/terms-of-service/> |
| [Privacy Policy](privacy-policy.md) | <https://aeiti.github.io/palmon-bot-legal/privacy-policy/> |

Those two URLs are the ones registered in the Discord Developer Portal, under
**General Information → Terms of Service URL / Privacy Policy URL**. They are
served by GitHub Pages from `main`, so a push to `main` publishes.

The site root — <https://aeiti.github.io/palmon-bot-legal/> — is also the
business website registered with Buy Me a Coffee and, through it, with Stripe.
It has to keep describing the donation terms in plain sight: a payment
processor's review compares the site against the account, and a site that says
the project takes no money is a reason for an account to be held. The donation
terms themselves are section 10 of the Terms of Service.

## Editing

Both files are Markdown with a small Jekyll front matter block that fixes the
permalink — leave that block in place or the published URL changes, and the
links registered with Discord break.

Change the "Last updated" date in a document whenever its substance changes.
The Privacy Policy describes what the bot actually stores, so if the bot's
database schema gains a column that holds anything about a person, this file
needs the same commit.

Nothing private or sensitive belongs in this repository. No tokens, no IDs, no
database contents, no contact details beyond what is already published here.
