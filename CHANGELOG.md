# Changelog

Modified from [oldnapalm/GTACoop](https://github.com/oldnapalm/GTACoop), client at commit `f5685d1` ("Update server browser", April 17, 2024).

## 0.9.5 (No Urtle GTA CoOp client)

- Renamed to "No Urtle GTA CoOp client" in the About item and the loaded message.
- Added a **Block urtle in chat** checkbox (on by default).
- Added **Disable Chat** to the settings menu.
- Added a **Chat Filter** setting for comma-separated words. Lines containing them are hidden, and they're also left out of the chat log. Matching ignores case, spaces, punctuation, GTA color codes, accents, and common look-alike characters. The filter never hides your own messages.
- Added a **Crash Log** option (off by default) that writes errors to `GTACoOp-crash.log` in the scripts folder. Errors in incoming packets are caught and logged instead of crashing the client, with a throttled in-game notice.
- Fixed NullReferenceExceptions from missing vehicle and ped position data, ped props, the server game mode, and the server hail message.
- The server browser no longer shows GeoIP2 errors when `GeoLite2.mmdb` is missing. It just skips the country tags.
- Added TekNicolSoppurt to the credits.
- Fixed the "GTACoOp error in StatusChanged (NullReferenceException)" notice when a server disconnects you. Leaving a server tried to delete things the server had spawned even if they were already gone, and crashed on server natives with no arguments. Each part of the disconnect cleanup now runs on its own, so one problem can't stop the rest.
- The error notice only says "Logged to GTACoOp-crash.log" when the Crash Log setting is on and the log was actually written. With it off, it just says something like "GTACoOp error in StatusChanged (NullReferenceException)."
- Leaving a server now removes everything it put on your map and screen: blips (including the next-spot blips in races and courses), checkpoints, pickups, and the vehicles, peds and props it spawned. It also turns the HUD and radar back on, fades the screen back in, clears screen effects, color filters and server cameras, resets the game speed, and clears its GPS routes and waypoint. Your own waypoint and the car you're sitting in are left alone. The same cleanup also runs when you join a new server.
- Fixed screen and HUD flicker on servers that run natives every frame (GTA Online style free roam and courses). Every-frame natives with no arguments (like hiding the HUD) used to crash every frame, which skipped the server's other every-frame natives and posted an error notification every frame. Now each one runs on its own, and errors show a short notice at most every 5 seconds. Screen effects, fades and anything that creates blips or objects no longer restart every frame, and the client no longer resets the game speed every frame once the server has set it.
- Display version 0.9.5 and assembly version 0.9.5.0. The network protocol version is still 0.9.4 for server compatibility.
