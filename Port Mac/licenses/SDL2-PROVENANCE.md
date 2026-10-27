# SDL2 runtime dependency

The Windows package includes the unmodified 64-bit `SDL2.dll` from the official
SDL2 2.32.10 MinGW development release:

- Project: https://github.com/libsdl-org/SDL
- Release: https://github.com/libsdl-org/SDL/releases/tag/release-2.32.10
- Archive: `SDL2-devel-2.32.10-mingw.tar.gz`
- DLL SHA-256: `53e8fa7e9ed43c30bd650c39396f0d9d2067d2fff0b926c9433b75202592e4aa`

`LICENSE.txt` is copied unchanged from that release. Linux development builds
can link the system SDL2; the Linux release bundles the same source version
rebuilt on Debian 12 (see `launchers/linux/lib/PROVENANCE.md`).

The macOS release builds the official `SDL2-2.32.10.tar.gz` source archive for
both `arm64` and `x86_64`, targeting macOS 11. It embeds
`Contents/Frameworks/libSDL2-2.0.0.dylib` and adjusts the app's install name to
that private library. Only Apple system frameworks and libraries remain external.
The dylib receives an ad-hoc code signature along with the app. Build commands
are in `cpp/tools/build-macos.sh`; archive source and SHA-256:

- https://www.libsdl.org/release/SDL2-2.32.10.tar.gz
- `5f5993c530f084535c65a6879e9b26ad441169b3e25d789d83287040a9ca5165`

SDL2 source is available from the linked official release.
