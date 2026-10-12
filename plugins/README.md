# Plugins

Every plugin on this page needs RGMP 1.9 or newer. RGMP 1.9 lists them under Settings -> Plugins ->
Add-ons and installs them with one button, and once a plugin is installed, it offers the next
version by itself at its update check. So nothing here has to be downloaded by hand any more.

To install one by hand anyway: Settings -> Plugins -> "Install", then pick the file. RGMP copies it
where it belongs:

- AudioUnit effects - a `.component`, into `~/Library/Audio/Plug-Ins/Components`. Most of them come
  as a `.pkg` instead, and that one RGMP doesn't unpack: it opens in the macOS Installer, which
  shows you what the package is going to do.
- VST® 3 effects - a `.vst3`, into `~/Library/Audio/Plug-Ins/VST3`.
- RGMP's own plugins - a `.rgmpplugin`, or a `.zip` with one inside, into
  `~/Library/Audio/Plug-Ins/RGMP`. A double click on a `.rgmpplugin` installs it too.

Effects are added under "DSP Effects" with "Add Effect". They sit on the whole output, so they keep
working across a change of track or of the output device.

An RGMP plugin adds something to the player itself. One installed from Add-ons is on right away; one
installed from a file stays off until you tick it in the list.

YouTube Support and Yandex Music keep the tracks they download in a cache, up to 5 GB each unless you
change it. The "Cache" section at the bottom of a plugin's page shows how much is taken, changes the
limit and clears it.

The MCP Server isn't on this page: it comes with RGMP 1.9 itself.

On RGMP 1.8 the one plugin that runs is Yandex Music 1.0,
[YandexMusic-1.0.zip](https://github.com/gewisser/RGMP-releases/raw/main/plugins/YandexMusic-1.0.zip).
Better to update RGMP first.

## YouTube Support

[YouTube-1.1.zip](https://github.com/gewisser/RGMP-releases/raw/main/plugins/YouTube-1.1.zip)

Videos, playlists and channels from YouTube and YouTube Music, by link.

Once it is installed and ticked, copy a link in the browser and paste it into a playlist with
Cmd+V, add it with Add -> Link, or drag it there. A video turns into a row with the title, the
channel, the length and the cover; a playlist or a channel turns into its videos. A live broadcast
plays like a radio station.

A link to a playlist or a channel is followed: its new videos arrive by themselves, at launch and
every 6 hours, and a video you deleted from the playlist doesn't come back. The plugin's page under
Plugins sets how often, or switches it off. Add to Exclusions in a row's menu keeps a video out for
good; the page lists the followed links and the exclusions, and lets you drop either.

What it runs on your Mac: the first time it is ticked, the plugin downloads two open-source
programs from GitHub into its own folder: yt-dlp, which reads YouTube, and QuickJS, which yt-dlp
needs. That is about 50 MB to download and 125 MB on disk. yt-dlp is checked against the SHA-256
sums its release publishes, QuickJS against sums built into the plugin. The plugin runs them each
time it reads a link or fetches a track, and Update yt-dlp on its page fetches the latest one:
YouTube changes often, and an old yt-dlp is the usual reason a link stops opening.

Two things to know:

- A track starts once it has downloaded in full, and the row shows how far it has got. A
  three-minute track takes a few seconds on a good connection, an hour-long mix about a minute.
- Many links read in a row can make YouTube ask to confirm you are not a bot. The row says so; try
  again a minute later.

## Yandex Music

[YandexMusic-1.4.zip](https://github.com/gewisser/RGMP-releases/raw/main/plugins/YandexMusic-1.4.zip)

Tracks, albums and playlists from music.yandex.ru.

Once it is installed and ticked, it gets a page of its own under Plugins. Press "Sign In": the
plugin shows a code and opens the browser, you type the code in there, and that's it, the sign-in
is remembered. After that, paste a link to a track, an album or a playlist, or drag it from the
browser straight into a playlist. It turns into an ordinary row with the title, the artist and the
cover. "Import from Yandex Music" brings in "Liked" and all of your playlists, each into a tab of its
own.

These tracks play like files do: seeking, crossfading, the waveform. Format and bitrate show up after
a track has played once.

"Quality" on the page picks what is downloaded: "Lossless" (the default) is FLAC where the track has
it and AAC 256 kbps otherwise, "High" is AAC 256 kbps, "Data saver" AAC 64 kbps. With Plus, a track
that has a lossless version plays in FLAC, about 30 MB a track. A few tracks the service keeps only
as MP3, and those come as MP3 whatever is picked.

New since 1.0: the quality choice, the cache, Open in Browser in a track's menu, and the plugin
speaks the player's five languages.

Two things to know:

- After every RGMP update, macOS asks for your keychain password once, when the plugin reads its
  sign-in. RGMP is ad-hoc signed, and for the keychain each new build is a different app.
- The plugin talks to the API the Yandex Music site itself uses, which is not a public one. When
  Yandex updates its web player, the plugin finds the new key by itself; if it can't, tracks come
  as MP3 and the page says so under "Quality", until the plugin gets an update.

## Scrobbler

[Scrobbler-1.0.zip](https://github.com/gewisser/RGMP-releases/raw/main/plugins/Scrobbler-1.0.zip)

Sends what you listen to to Last.fm, ListenBrainz or both.

Its page under Plugins has a section for each service. For Last.fm, press "Connect" and allow
access in the browser that opens. For ListenBrainz, paste the token from
[listenbrainz.org/settings](https://listenbrainz.org/settings/) into "Token" and press "Connect".

While a track plays, your profile shows it as playing now; "Show what is playing now" under General
turns that off. A track counts once half of it or four minutes have been heard, whichever comes
first, and only if it is longer than 30 seconds. Seeking doesn't count, and at another speed it is
the track's seconds that count, not the clock's. Files with artist and title tags are sent, and
Yandex Music tracks. Radio and YouTube are not.

With no connection, listens wait and go out by themselves once it is back, after a restart of the
player too. The page says what went out last and what went wrong, and "Open profile" takes you to
your page on the service.

One thing to know: Last.fm doesn't take a listen older than 14 days, so one that waited longer than
that is dropped. ListenBrainz takes it.

![VST Compatible](../images/vst-compatible.svg)

VST is a registered trademark of Steinberg Media Technologies GmbH.
