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

`/AuthToken`

- Respond: Return an UUID that can be used in the client

APIs
--

`/DeviceList` GET

- Request:

        { "auth_token": "1234" }

- Respond: List of devices with name and serial number (optional)

        [
            {"id": "aaa", "serial_number":"bbb"},
            {"id": "aaa", "serial_number":null},
        ]

`/DeviceEdit` POST

- Request

        {
            "id": 1,
            "serial_number": "aabbcc",
            "auth_token": "1234"
        }


`/DeviceReg`

- Request

        {
            "id": 1,
            "auth_token": "1234"
        }
