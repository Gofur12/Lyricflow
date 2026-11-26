# Lyrics Zymu Mobile

Workspace for the mobile-focused Lyrics Zymu project.

## Build order

1. **Original target first:** inspect and restore the supplied Lyrics Zymu Mobile 1.3 build for its original Minecraft target (Fabric, Minecraft 1.21.11).
2. Add the requested YouTube and YouTube-account/playlist features to that original-target build.
3. Only after the original-target build is verified, create a separate Fabric 1.20.1 port.

## Source input

Upload the original file to:

`original/LyricsZymu-Mobile-1.3_1.21.11.jar`

Then run **Actions → Prepare Lyrics Zymu source inspection → Run workflow**.

The first workflow only decompiles and inspects the supplied binary. It does not claim to produce a modified or working mod. The actual source changes and build will follow after the decompiled code and dependencies are reviewed.

## Feature goals

- Keep existing Lyrics Zymu features and UI.
- Keep YouTube Music as its own source.
- Add ordinary YouTube as a separate source.
- Add accurate, timestamp-based synced lyrics where timing data is available.
- Add Google OAuth sign-in and read-only access to the user's YouTube playlists.
- Never collect or store Google passwords in the mod.

## Important API constraints

Use official Google OAuth and YouTube Data API for account and playlist access. Playback behavior must follow YouTube's developer policies; do not implement audio extraction, ad removal, or unsupported background playback.

## Runtime/build distinction

The original target and the 1.20.1 port are separate outputs. Minecraft 1.20.1 generally runs on Java 17, even if a newer JDK is used for some build tooling. The exact Gradle, Loom, loader, and API versions will be pinned after source inspection.
