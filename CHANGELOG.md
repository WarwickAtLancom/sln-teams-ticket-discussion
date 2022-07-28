## v0.0.0.4 2021-11-12

## Added

- AllowNewThreads configuration setting. Controls whether new threads can be created for tickets with a pre-existing thread
- DeskDirector connector check in config flow

## v0.0.0.3 2021-11-12

## Changed

- Ticket created flow
  - Renamed to Ticket tagged
  - Trigger changed from ticket created, to ticket tag added ('teams' tag)

## v0.0.0.2 2021-09-13

## Added

- Config flow: all the setup required to set up solution
- Config table: stores domain, Teams: group, channel info

## Changed

- Ticket created, note, time entry flows
  - Retrieve Teams group and channel from Config table and use in Teams actions

## v0.0.0.1 2021-09-10

### Added

- Initial version
