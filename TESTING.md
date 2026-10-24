# Testing Kick Air

Version 0.3.1 beta. No activation or time limit.

Please use a saved copy of a project for your first test.

## What to check

1. Install the plugin and confirm it appears in your DAW.
2. Put it on a bass track and route a separate kick to its external sidechain.
3. In Audio mode, confirm that each kick triggers ducking. Try a few irregular
   hits and a change from quarter notes to eighth notes.
4. Stop the kick. The bass should return to full level after the current response.
5. Check Depth at 0, 50 and 100 percent. With a curve that reaches zero, 100 percent
   should fully duck the bass at the bottom of that curve.
6. Adjust Flow, move the curve and reset its position. Listen for clicks.
7. Check Auto tempo, a project tempo change and a manual BPM value.
8. Save and reopen the project. Check that the settings return correctly.
9. Try offline export, different buffer sizes and several plugin instances.
10. Check the red kick, blue bass output and the GUI at your usual display scaling.

## Report a bug

Open an issue at https://github.com/kikk-i/kick-air/issues and include:

- Kick Air version and plugin format, AU or VST3.
- Operating system version and CPU.
- DAW name and version.
- Sample rate and audio buffer size.
- What you expected and what happened.
- Steps to reproduce, including the routing and trigger mode.
- A screenshot if the problem involves routing or the display.

Successful compatibility reports are useful too. Please include the DAW version,
OS, plugin format and anything you tested.

## Current test coverage

The macOS AU and VST3 builds passed native validation and test-host checks.
The Intel AU was also checked using Rosetta on Apple Silicon.

The Windows VST3 build passed runtime, GUI, installer and uninstaller checks using
Wine 11.0 on macOS. It has not yet been tested in a DAW on a physical Windows PC.
Compatibility with every DAW is not confirmed.

Both installers are unsigned beta builds. The macOS package is not notarized.
See USER_GUIDE.md for installation and routing.

created by Krystian Modzelan
