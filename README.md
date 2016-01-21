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

- Respond: Return an Auth Token that can be used in the API

APIs
--

## Authentication:
All API requests require authenticate with the following header:

    X-GENIUS-BAR-AUTH: uuid4

## Endpoints:

`/DeviceList` GET

- Request

    No query parameter at all.

- Respond

    List of device with name and serial number (optional)

        [
            {"id": "iphone6-pink", "serial_number":"bbb"},
            {"id": "iphone6s-black", "serial_number":null},
        ]

`/DeviceEdit` POST

- Request

    Set the serial number of a device

        {
            "id": "iphone6-pink",
            "serial_number": "aabbcc",
        }


`/DeviceReg`

- Request

    Send a list of device that to be registered

        [{
            "id": "iphone6-gold"
        }]

- Response

    A list of affected devices.
    
        [{
            "id": "iphone6-gold",
            "serial_number": "aabbcc"
        }]

----

## Serial number:
Device's serial number can be checked with the following command on Mac:

    system_profiler SPUSBDataType
