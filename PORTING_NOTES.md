# Porting notes: Minecraft 1.21.4 → Fabric 1.20.1

## Confirmed from the supplied 2.2+1.21.4 JAR

- Mod id: `lyricsflow`
- Display name: LyricsFlow
- Entrypoints:
  - Client: `dev.lyricsflow.LyricsFlowClient`
  - Mod Menu: `dev.lyricsflow.compat.ModMenuEntry`
- Current declared target: Minecraft `~1.21.4`
- Current declared Java requirement: `>=21`
- Mixin package: `dev.lyricsflow.mixin`
- Mixin config: `lyricsflow.mixins.json`
- Declared mixins:
  1. `GameRendererMixin`
  2. `GuiHotbarMixin`
  3. `ShaderProgramKeysMixin`
  4. `KeyboardHandlerMixin`
  5. `LevelRendererMixin`
  6. `PackRepositoryMixin`
  7. `DeathHideMixin`
  8. `FogRendererMixin`
  9. `CustomCrosshairCompatMixin`
  10. `ClientPacketListenerAccessor`
  11. `PingDebugMonitorMixin`

## Required target changes

- Change Fabric metadata's Minecraft dependency from 1.21.4 to 1.20.1.
- Verify each Minecraft/Yarn symbol and method descriptor against 1.20.1 mappings.
- Rework mixins whose target classes, methods, fields, or injection points changed.
- Regenerate the refmap for the 1.20.1 build; do not reuse the 1.21.4 refmap.
- Check shader/post-effect JSON and rendering APIs against 1.20.1.
- Confirm third-party dependencies and Mod Menu compatibility.

## Important

This is an analysis/porting workspace, not a finished port. No decompiled source has been reviewed or adapted yet. A successful decompile is only the first step; the resulting code must be ported and compiled against Fabric 1.20.1, then tested in-game.
