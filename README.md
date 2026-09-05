# RGMP downloads

A music player for macOS. This repository carries the releases and the update feed; there is no
source code here.

## Getting it

1. Download the `.dmg` from [Releases](https://github.com/gewisser/RGMP-releases/releases).
2. Double-click it. A window opens with RGMP in it, next to your Applications folder.
3. Drag RGMP across, then eject the disk image.

The `.zip` next to the image is what an installed copy downloads when it updates itself, so there
is no reason to take that one by hand.

macOS 26 or newer. Universal build: Apple Silicon and Intel.

## The first launch

RGMP is ad-hoc signed and is **not** notarized, so macOS refuses to open it the first time. That is
expected, and it happens once:

1. Double-click RGMP and dismiss the warning.
2. System Settings -> Privacy & Security -> "Open Anyway".
3. Confirm, and open RGMP again.

The same thing in one Terminal command:

```
xattr -dr com.apple.quarantine /Applications/RGMP.app
```

## Updating

RGMP checks this repository for a new version once a day, and you can ask it to check at any time:
"Check for Updates..." in the application menu, or the Updates pane in its settings.

Every update is verified against a signing key built into the copy you already have, so an archive
that has been altered on the way will not install. That check is not Apple's, and it does not make
the build notarized; what it does mean is that an update can only come from whoever holds the key
this build was published with.

Test versions go to a channel of their own. They are off by default, and the same settings pane is
where you turn them on.
