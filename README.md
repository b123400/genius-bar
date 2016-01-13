# genius-bar
API backend for tracking mobile device with slack

- The bot should be in #general.
- All respond should be public in #general
- refs. https://oursky.quip.com/78TbAEKfztza


Commands
--

`/DeviceCheckout [device ID]`

- Respond: “@username checkout device [device ID]”
- Push "Device [device ID] check out by @username" to the oringal channel

`/DeviceList`

- Respond: a list of all Device ID | Device Name | Ownership

`/DeviceReg [device ID]`

- Respond: “[Device ID] / [Device Name] registered and own by @username”

`/DeviceDereg [Device ID] [reason]`

- Respond: “[Device ID] / [Device Name] de-registered by @username”

`/DeviceAudit [Device iD]`

- Respond: Show the list of last 20 register / deregister / own actions
