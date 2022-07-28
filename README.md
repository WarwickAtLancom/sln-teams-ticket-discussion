# Solution - Teams Ticket Discussion

[Click here for a complete setup guide on our Knowledge Base](https://help.deskdirector.com/article/a9qrgoynxk-featured-solution-teams-ticket-discussion)

This solution comprises of three flows:

- Ticket Tagged: will post a teams message to a channel (or reply to existing message) when a ticket is tagged with `teams`
- Ticket Note Added: will reply to the initial teams message when a ticket note is added
- Time Entry Added: will reply to the initial teams message when a time entry is added

## Connectors Used

- DeskDirector
- Microsoft Dataverse
- Microsoft Teams

## Setup

- Teams Ticket Discussion - Config flow
  - `Config` action
    - `domain` (string): Enter the domain to your DeskDirector instance in the form of `subdomain.deskdirector.com`
    - `allowNewThreads` (boolean): controls whether new threads can be created for tickets with a pre-existing thread. Recommend false. See usage section.
  - `Post message in a chat or channel` action
    - `Post as`
    - `Post in`: input value must be `Channel`
    - `Team`
    - `Channel`

## Optional Setup

- All flows
  - Specify additional filters in the flow triggers
  - Edit the Teams message content
- Teams Ticket Discussion - Ticket Tagged flow
  - The `teams` tag can be changed to something else in the trigger

## Usage

- In the Tech portal, tag a ticket with `teams`. Depending on your `allowNewThreads` setting, one of the following will occur:

  | allowNewThreads | Ticket has existing thread |      Outcome      |
  | :-------------: | :------------------------: | :---------------: |
  |      true       |            yes             |    New thread     |
  |      true       |             no             |    New thread     |
  |      false      |            yes             | Reply to existing |
  |      false      |             no             |    New thread     |

- When a new thread is created, any updates to the ticket thereafter will only be posted as replies to the new thread. Any previous threads will not receive ticket updates.
