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

1. Double-click RGMP. macOS shows a window saying "RGMP.app Not Opened", with two buttons. Click
   "Done". The blue "Move to Trash" is the default button: Return presses it, and RGMP goes to the
   Trash.
2. System Settings -> Privacy & Security, the Security section -> "Open Anyway". The button stays
   there for about an hour after the attempt to open RGMP.
3. Confirm with your account password. If macOS asks "Open RGMP.app?", click "Open".

The same thing in one Terminal command:

```
xattr -dr com.apple.quarantine /Applications/RGMP.app
```

## Updating

The second time RGMP is opened, it asks whether it may check for new versions by itself. If you
agree, it checks this repository once a day. You can also ask it to check at any time: "Check for
Updates..." in the application menu, or the Updates pane in its settings.

Every update is verified against a signing key built into the copy you already have, so an archive
that has been altered on the way will not install. That check is not Apple's, and it does not make
the build notarized; what it does mean is that an update can only come from whoever holds the key
this build was published with.

Test versions go to a channel of their own. A copy installed from a test version is offered the
test versions that follow as well; any other copy only gets released versions. "Update to" in the
same settings pane switches between the two.

## Reporting a problem

Open an [issue](https://github.com/gewisser/RGMP-releases/issues/new/choose) and pick the form that
fits. The About RGMP window, the first item of the RGMP menu, shows the version, the Mac and the
macOS line a bug report asks for, and they can be copied from there.

The log is at `~/Library/Application Support/gewisser.rgmp/Logs/RGMP.log`. Attaching it to a bug
report usually saves a round of questions.
