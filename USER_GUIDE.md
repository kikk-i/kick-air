# Kick Air user guide

Version 0.3.1 beta

Kick Air lowers the volume of a bass or another track when a sound arrives at its
external sidechain input. The sidechain source can be a kick, snare or any other
sound. The plugin processes the main input and leaves the sidechain audio alone.

## Requirements

- Windows 10 or 11 with a 64-bit DAW that supports VST3.
- macOS 11 or later on Apple Silicon or Intel, with an AU or VST3 host.

AAX, VST2, Linux and 32-bit Windows hosts are not included.

## Install on Windows

1. Save your project and close your DAW.
2. Run `KickAir-0.3.1-Windows-x64.exe` and complete the setup.
3. Open your DAW and rescan VST3 plugins if Kick Air does not appear.

The installer needs administrator permission and places the plugin in:

    C:\Program Files\Common Files\VST3\KickAir.vst3

The user guide, testing notes and uninstaller are in:

    C:\Program Files\Kick Air

To remove the plugin, open Windows Settings, find Kick Air in Apps and choose
Uninstall. Your DAW projects are kept.

## Install on macOS

1. Save your project and close your DAW.
2. Open `KickAir-0.3.1-macOS.pkg` and install for your current user account.
3. Open your DAW and rescan plugins if Kick Air does not appear.

The installer includes universal AU and VST3 plugins:

    ~/Library/Audio/Plug-Ins/Components/KickAir.component
    ~/Library/Audio/Plug-Ins/VST3/KickAir.vst3

The user guide and testing notes are in:

    ~/Library/Application Support/KickAir

To uninstall, close your DAW and remove these two Kick Air plugin bundles.

## Unsigned beta installers

The Windows installer has no Authenticode signature. The macOS installer has no
Developer ID signature or Apple notarization. Your system may show a warning.
Download from the official GitHub release and compare the file with SHA256SUMS.txt.

If macOS blocks the installer and you trust this download, try opening it once,
then open System Settings, Privacy & Security and use Open Anyway for that
installer. Confirm the next prompt. See [Apple's per-file approval instructions](https://support.apple.com/en-us/102445).

## Quick setup

1. Insert Kick Air on the bass or other track you want to lower.
2. Send the kick or another trigger to the plugin's external sidechain input.
3. Keep the trigger mode set to Audio and start playback.
4. Adjust Depth for the amount of ducking, then Flow and the note division for
   the return of the bass.

Keep the kick's normal route to the master. Use a separate sidechain send to the
bass track. A normal audio send mixes the kick into the bass track, so the plugin
would lower both sounds together.

## FL Studio routing

1. Put the kick and bass on separate mixer tracks.
2. Insert Kick Air VST3 on the bass track.
3. Select the kick track. Right-click the routing arrow under the bass track and
   choose Sidechain to this track.
4. Open the Kick Air wrapper settings, then Processing, then Connections.
5. Leave Signal assigned to the main bass input. Assign the kick send to the
   auxiliary input whose label starts with Side Chain.
6. Play the project with Audio selected in Kick Air.

Create the sidechain send first, then assign it in Processing. Creating a send
alone may not connect it to the plugin's auxiliary input. Depending on the FL
Studio version, the source is shown as a send index or a track name. Choose the
actual kick send. A send index is not necessarily the mixer track number.

## Logic Pro routing

1. Add Kick Air to the bass track from Audio FX, Audio Units, Kick Air, Kick Air.
2. In the Side Chain menu at the top of the plugin window, select the kick track
   or its bus.
3. Start playback and keep Audio selected inside Kick Air.

Logic Pro uses the AU version.

## Other DAWs

Insert Kick Air on the track being ducked. Enable the effect's external sidechain
and select the trigger track or send. The exact routing controls depend on the
DAW. The main input receives the bass; the auxiliary input receives the trigger.

## Main controls

- Depth: amount of volume reduction from 0 to 100 percent. At 0 percent the bass
  is not ducked. At 100 percent, a curve value of zero silences the bass. Right-click
  the knob for 10 percent steps or type an exact value. Double-click resets to 100.
- Flow: character of the return. Lower values return later and more steeply;
  higher values return earlier and more gently. Double-click resets to 50.
- Shape: choose one of 16 starting curves or edit a Custom curve.
- Note division: choose 1/8, 1/4, 1/2 or one bar. This changes the response duration.
  In Audio mode, each detected hit can trigger the curve, including faster hits.
- Auto: follows the project tempo. Type a BPM value to use a manual tempo, or
  choose Auto again to follow the project. Manual BPM changes the plugin's timing,
  not the tempo of the DAW project.
- Audio: triggers from the external sidechain. After the last hit, the bass returns
  to full level when the current response ends. It does not repeat in silence.
- Clock (manual): repeats from a clock, without requiring sidechain hits.
- MIDI trigger: triggers from MIDI notes routed to the effect by your DAW.

## Move or edit the curve

Drag the graph left or right to move the response relative to the kick. Hold Shift
for finer movement. Click the graph and use the left and right arrow keys as an
alternative. The return-arrow button or a double-click resets the offset.

Open Details with the three-dot button for an exact Shift value. Option-drag on
macOS, or Alt-drag on Windows, changes Slope instead of moving the whole curve.

In Details, enable Edit curve to move the eight control points. Drag a point or
enter Point X and Point Y values. Arrow keys move the selected point. Option with
left or right on macOS, or Alt with left or right on Windows, selects another
point. Shift gives a finer step. Decimal commas and decimal points are accepted.

## Waveform display

Red is the external kick. Blue is the actual processed bass output. Both use the
same captured time window. The kick attack anchors the left side of the display.
The last complete capture stays visible between hits.

Kick and Bass out show sample peak levels in dBFS from the visible window, before
display normalization. They are signal levels, not gain reduction readings. A held
or frozen capture keeps the same numbers until a new capture is shown.

Dry adds the unprocessed bass trace. Freeze holds the picture without stopping
audio processing. Display normalization changes the drawing, not the sound.

## Details

- Shift moves the response in time. Slope changes the position of its rising part.
- Bend is the internal curvature range corresponding to Flow.
- Trigger dB sets the audio detection threshold.
- Length changes the response duration relative to the selected note division.
- End sets the end of the response in one-shot modes.
- Loop repeats the response between MIDI triggers. It is available in MIDI mode.
- Low band limits ducking to the low frequencies. The crossover range is 20 to
  5120 Hz. Solo low lets you listen to that processed band.
- More options contains smoothing, retrigger spacing, Anti-click and reset.

Anti-click is enabled by default. Audio mode reports 16 ms of latency with it
on, or 10 ms with it off. MIDI mode reports 6 ms or 0 ms. Clock mode reports 0 ms.
Your DAW should compensate for the reported latency. Some hosts need playback
stopped and restarted after a latency setting changes.

## Troubleshooting

No kick input: check the external sidechain assignment in the DAW or wrapper.

Kick input is silent: check that the trigger track is playing and its send is active.

Kick input matches bass: the two inputs contain nearly identical audio. Check
that the auxiliary input receives the kick and Signal receives the bass.

The kick is also ducked: check for a normal audio send from kick to bass. The kick
may already be mixed into the plugin's main input. Use a sidechain-only send.

The bass keeps pulsing without a kick: choose Audio rather than Clock (manual).

No plugin after installation: close and reopen the DAW, then rescan the appropriate
format. On Windows use the 64-bit VST3 version. In Logic Pro use AU.

For a bug report, include your OS, CPU, DAW and version, plugin format, sample rate,
buffer size and steps to reproduce. Include routing screenshots when relevant.
See TESTING.md in the GitHub repository for the feedback checklist.

created by Krystian Modzelan
