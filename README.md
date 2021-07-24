# volumio-snapserver-plugin
 A new version of the SnapServer functionality, totally revamped.

## Files edited by this plugin
/mnt/overlay/dyn/volumio/app/plugins/music_service/airplay_emulation/shairport-sync.conf.tmpl

```
#alsa =
#{
#  output_device = "${device}";
#  ${buffer_size_line}
#};

pipe =
{
  name = "/tmp/snapfifo";
}
```

## Working config
For MPD I use the following:

```
44.1kHz
16 bits
2 channels
```

Subsequently I use the same settings for the outgoing stream, this seems to be working for MPD, Airplay (if and when enabled) and Spotify (all implementations).
Setting stream (and MPD, to prevent resampling) to 48kHz seems to sound slightly accelerated in comparison to 44.1kHz when playing Spotify streams.

Problem arise when you put 44.1kHz into the pipe and have the pipe resample to 48kHz.

### Restore core-files
`volumio updater restorevolumio`