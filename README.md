# Allegedly — installers

*Your media. Allegedly.*

Allegedly is an independent media player for Plex servers. This repository
holds installers only; the app checks here for updates.

Allegedly is not affiliated with or endorsed by Plex.

## Windows

1. Download [Allegedly-Setup.exe](https://raw.githubusercontent.com/fanofsteel2013/allegedly-releases/main/Allegedly-Setup.exe).
2. Run it. Windows may show "Windows protected your PC" because the
   installer is not signed yet: choose **More info**, then **Run anyway**.
3. Sign in with your own Plex account.

Needs 64-bit Windows 10 or 11. Once installed, Allegedly offers newer
versions by itself (Settings > Updates).

## Android TV (Nvidia Shield, Fire TV and similar)

There is no store listing yet, so the app is installed from a file
("sideloaded"):

1. On the TV box, allow apps from outside the store. On most boxes this is
   under Settings > Security or Device Preferences > **Unknown sources**
   (on Fire TV: Settings > My Fire TV > Developer options).
2. Install the free **Downloader** app by AFTVnews from the box's own app
   store (search for "Downloader"). Its pages:
   [Google Play](https://play.google.com/store/apps/details?id=com.esaba.downloader)
   for Shield, Google TV and Android TV, and
   [the maker's site](https://www.aftvnews.com/downloader/), which also
   covers Fire TV.
3. In Downloader's address box, enter the code **9392193** and press Go,
   then install the file it downloads. (The code is a shortcut for this
   address, which works too:
   `https://raw.githubusercontent.com/fanofsteel2013/allegedly-releases/main/Allegedly.apk`)
4. Open Allegedly and sign in: it shows a short code to enter at
   plex.tv/link on your phone.

Needs Android 7 or newer. Once installed, Allegedly offers newer versions
by itself; Android asks you to confirm each install.

So far it has only been tried on an Nvidia Shield TV.

This is an early test build. Expect rough edges.

## Third-party software

Allegedly includes third-party components, among them libmpv and FFmpeg
under the LGPL. See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).
