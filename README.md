# LyricsFlow — Fabric 1.20.1 Port

This repository is the workspace for porting LyricsFlow from Minecraft 1.21.4 to Fabric 1.20.1.

## Status

This is a porting workspace, not yet a completed or verified port. The original mod JAR is compiled for Java 21 / Minecraft 1.21.4. Porting requires source decompilation and adapting Minecraft/Fabric APIs and mixins to 1.20.1.

## Build

The GitHub Actions workflow will prepare a decompiled inspection artifact. It does not produce a working 1.20.1 mod JAR until the ported source and build configuration are implemented.
