# Third-party notices

Allegedly uses third-party software. This file lists every third-party
component that ships with (or is linked into) the app, with its license.
Maintain it from day one: add an entry in the same commit that adds a
dependency.

> Status: Milestone 0 skeleton. The "Planned" list is not a notice; it
> records what `docs/ARCHITECTURE.md` expects so licence review happens
> before adoption. Dev-only tools (lints, test) are not shipped and not listed.

## Included components

| Component | Version | License | Used in | Source |
| --- | --- | --- | --- | --- |
| Flutter SDK (framework, engine) and Dart SDK | 3.47.7 / 3.13.5 | BSD-3-Clause (engine bundles further notices; the app's licence page lists them) | app, allegedly_player, allegedly_ui | <https://github.com/flutter/flutter> |
| cupertino_icons | 1.0.9 | MIT | app | <https://pub.dev/packages/cupertino_icons> |
| http (and its transitive deps: async, collection, http_parser, meta, path, source_span, string_scanner, term_glyph, typed_data, web) | 1.x | BSD-3-Clause | plex_api | <https://pub.dev/packages/http> |
| flutter_riverpod / riverpod | 3.4.3 | MIT | app | <https://pub.dev/packages/flutter_riverpod> |
| flutter_secure_storage (and platform implementations) | 11.2.0 | BSD-3-Clause | app | <https://pub.dev/packages/flutter_secure_storage> |
| url_launcher (and platform implementations) | 6.3.3 | BSD-3-Clause | app | <https://pub.dev/packages/url_launcher> |
| shared_preferences (and platform implementations) | 2.5.6 | BSD-3-Clause | app | <https://pub.dev/packages/shared_preferences> |
| file_selector (and platform implementations) | 1.1.0 | BSD-3-Clause | app | <https://pub.dev/packages/file_selector> |
| ffi | 2.x | BSD-3-Clause | app (reading game controllers through Windows XInput) | <https://pub.dev/packages/ffi> |
| window_manager (with screen_retriever) | 0.5.2 / 0.2.2 | MIT | app (full screen) | <https://pub.dev/packages/window_manager> |
| crypto | 3.x | BSD-3-Clause | allegedly_core (PIN hashing) | <https://pub.dev/packages/crypto> |
| media_kit, media_kit_video | 1.2.6 / 2.0.1 | MIT | allegedly_player | <https://pub.dev/packages/media_kit> |
| media_kit_libs_android_video (prebuilt libmpv + FFmpeg for Android, fetched at build time) | 1.3.8 | Wrapper MIT. Bundled `libmpv.so` (v1.1.7 from <https://github.com/media-kit/libmpv-android-video-build>): mpv built with `-Dgpl=false`, FFmpeg with `--disable-gpl --enable-version3`, so **LGPL version 3 or later** (read from the build strings inside the library, 2026-10-12) | allegedly_player (Android) | <https://pub.dev/packages/media_kit_libs_android_video> |
| media_kit_libs_windows_video (prebuilt libmpv + FFmpeg DLLs fetched at build time) | 1.0.11 | Wrapper MIT. Bundled `libmpv-2.dll` (archive `mpv-dev-x86_64-20230924-git-652a1dd` from <https://github.com/media-kit/libmpv-win32-video-build>): mpv built with `-Dgpl=false`, FFmpeg with `--disable-gpl --enable-version3`, so **LGPL version 3 or later** (read from the build strings inside the DLL, 2026-10-10) | allegedly_player (Windows) | <https://pub.dev/packages/media_kit_libs_windows_video> |

**libmpv/FFmpeg (LGPL-3.0-or-later):** the library ships as a separate DLL
beside the app and is loaded at run time, so anyone may replace it with their
own build. Its source and build scripts are published by the media-kit project
at the address above (tag `2023-09-24`). The installer puts this file in the
app folder. This is our reading of the build flags, not legal advice; get it
reviewed before selling the app.

Licences above are as declared by each package; transitive dependencies in
`pubspec.lock` still need a full audit before any public release.

## Planned (not yet included)

| Component | Expected license | Notes |
| --- | --- | --- |
| media_kit | MIT | libmpv wrapper (Milestone 1) |
| libmpv / mpv | LGPL-2.1-or-later **only when built without GPL components** | See ARCHITECTURE §8: dynamic linking, publish corresponding source and build scripts |
| FFmpeg | LGPL-2.1-or-later **only when built without GPL/nonfree components** | Same obligations as libmpv; codec patent review before paid distribution |
| Riverpod, go_router, Drift, freezed, json_serializable, slang | MIT / BSD-3-Clause (verify per package on adoption) | |

## Rules

- Verify the licence of each package (and its transitive native binaries) at
  the version actually pinned, not from memory.
- No GPL-licensed code. Plezy (GPL-3.0) must never be copied; see `CLAUDE.md`.
- "Plex" is a trademark of Plex, Inc. Allegedly is not affiliated with or
  endorsed by Plex, Inc.
