# UNSAFE EXPERIMENT — DO NOT INSTALL

The 2026-11-01 diagnostic build from commit `bae23e2` caused severe Android 17
regression: applications would not launch while the experimental Vector/LSPosed
FuseHide module was active. The user had to uninstall it to recover.

**DO NOT install or enable the artifact produced by run 41358993316.**
The parent-directory FUSE-BPF/backing modification was system-wide, affected
`Android/data` and `Android/obb`, and was not an acceptable implementation.
This does not confirm that BPF bypass was the root cause of Duck Detector results.

This branch has had the unsafe native patch reverted, and its workflow is
intentionally disabled. The incident is kept as a diagnostic record only.
Do not turn this into a distributable module without independent testing
of Android storage, MediaProvider and cross-UID isolation in an emulator first.
