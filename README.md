# No Urtle GTA CoOp client

A modified client for [GTA Coop](https://github.com/oldnapalm/GTACoop), the multiplayer modification for Grand Theft Auto V that uses none of Rockstar's online code.

This repo contains **only the client** (`GTACoOp.dll`). It's built to work with the existing GTA Coop servers from [oldnapalm/GTACoop](https://github.com/oldnapalm/GTACoop). It still reports network version 0.9.4, so it can join the same servers.

## Main features

- **Block urtle in chat.** On by default. One checkbox hides every chat line containing "urtle", including spaced-out, punctuated, color-coded, or look-alike spellings.
- **Disable chat.** Turn chat off completely from the settings menu.

## Other changes

- **Chat filter.** Add your own words, separated by commas, to hide any chat line containing them. It only applies to other players, never to your own messages.
- **Crash log.** Optional (off by default). Errors are written to `GTACoOp-crash.log` next to `ClientSettings.xml` in your `scripts` folder, and a short in-game notice says which packet caused the error.
- **Crash fixes.** Null checks for missing vehicle and ped position data, ped props, game mode name, and server hail message, which used to crash the client.

See [CHANGELOG.md](CHANGELOG.md) for the full list, and [THIRD-PARTY-NOTICES.txt](THIRD-PARTY-NOTICES.txt) for the licenses of the bundled libraries.

## Install

1. Install [ScriptHookV](http://www.dev-c.com/gtav/scripthookv/) and [ScriptHookVDotNet 3](https://github.com/scripthookvdotnet/scripthookvdotnet).
2. Copy `GTACoOp.dll` and its dependency DLLs (LemonUI.SHVDN3, Lidgren.Network.MultiTarget, MaxMind.Db, MaxMind.GeoIP2, Newtonsoft.Json, protobuf-net) into your GTA V `scripts` folder.
3. Start the game and open the GTA Coop menu.

The GeoLite2 database (`GeoLite2.mmdb`) used for the server browser country lookup isn't included. Download it from [MaxMind](https://www.maxmind.com/en/geolite2/signup) under their license if you want it.

## Build

Open `Client/GTACoOp.csproj` in Visual Studio (targets .NET Framework 4.8, x64) and build in Release. The NuGet packages restore automatically.

## Credits

GTA Coop by Guad, Bluscream, wolfmitchell, TheIndra, oldnapalm, EntenKoeniq and BsCaBl. No Urtle modifications by [TekNicolSoppurt](https://github.com/teknicolsoppurt).

## License

GNU General Public License v3.0, the same as the original project. See [LICENSE.md](LICENSE.md). This is a modified version of GTA Coop, and the changes are listed in [CHANGELOG.md](CHANGELOG.md).
