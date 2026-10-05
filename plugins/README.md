# Plugins

Plugins need RGMP 1.8 or newer. Earlier versions don't know about them at all.

Everything below is installed the same way: Settings -> Plugins -> "Install", then pick the file.
RGMP copies it where it belongs:

- AudioUnit effects - a `.component`, into `~/Library/Audio/Plug-Ins/Components`. Most of them come
  as a `.pkg` instead, and that one RGMP doesn't unpack: it opens in the macOS Installer, which
  shows you what the package is going to do.
- VST® 3 effects - a `.vst3`, into `~/Library/Audio/Plug-Ins/VST3`.
- RGMP's own plugins - a `.rgmpplugin`, or a `.zip` with one inside, into
  `~/Library/Audio/Plug-Ins/RGMP`. A double click on a `.rgmpplugin` installs it too.

Effects are added under "DSP Effects" with "Add Effect". They sit on the whole output, so they keep
working across a change of track or of the output device.

An RGMP plugin adds something to the player itself, and a new one stays off until you tick it in the
list.

## Yandex Music

[YandexMusic-1.0.zip](https://github.com/gewisser/RGMP-releases/raw/main/plugins/YandexMusic-1.0.zip)

Tracks, albums and playlists from music.yandex.ru.

Once it is installed and ticked, it gets a page of its own under Plugins. Press "Sign In": the
plugin shows a code and opens the browser, you type the code in there, and that's it, the sign-in
is remembered. After that, paste a link to a track, an album or a playlist, or drag it from the
browser straight into a playlist. It turns into an ordinary row with the title, the artist and the
cover. "Import from Yandex Music" brings in "Liked" and all of your playlists, each into a tab of its
own.

These tracks play like files do: seeking, crossfading, the waveform. Format and bitrate show up after
a track has played once.

Two things to know:

- After every RGMP update, macOS asks for your keychain password once, when the plugin reads its
  sign-in. RGMP is ad-hoc signed, and for the keychain each new build is a different app.
- The plugin talks to the API the Yandex Music site itself uses, which is not a public one. If
  Yandex changes it, the plugin can stop working until it gets an update.

![VST Compatible](../images/vst-compatible.svg)

VST is a registered trademark of Steinberg Media Technologies GmbH.
