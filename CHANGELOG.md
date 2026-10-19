# Changelog

Modified from [oldnapalm/GTACoop](https://github.com/oldnapalm/GTACoop), client at commit `f5685d1` ("Update server browser", April 17, 2024).

## 0.9.5 (No Urtle GTA CoOp client)

- Renamed to "No Urtle GTA CoOp client" in the About item and the loaded message.
- Added a **Block urtle in chat** checkbox (on by default).
- Added **Disable Chat** to the settings menu.
- Added a **Chat Filter** setting for comma-separated words. Lines containing them are hidden, and they're also left out of the chat log. Matching ignores case, spaces, punctuation, GTA color codes, accents, and common look-alike characters. The filter never hides your own messages.
- Added a **Crash Log** option (off by default) that writes errors to `GTACoOp-crash.log` in the scripts folder. Errors in incoming packets are caught and logged instead of crashing the client, with a throttled in-game notice.
- Fixed NullReferenceExceptions from missing vehicle and ped position data, ped props, the server game mode, and the server hail message.
- Added TekNicolSoppurt to the credits.
- Display version 0.9.5 and assembly version 0.9.5.0. The network protocol version is still 0.9.4 for server compatibility.
