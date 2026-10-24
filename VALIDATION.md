# Validation summary

Kick Air 0.3.1 beta, October 24, 2026.

## Audio and plugin checks

- DSP regression suite: 1,426,710 assertions passed.
- Official VST3 validator: 47 passed, 0 failed on each platform build.
- macOS AU: strict native validation passed. Intel AU validation also passed
  using Rosetta on Apple Silicon.
- Native macOS VST3 test host: 79,631 checks passed.
- Windows VST3 test host: 79,516 checks passed using Wine 11.0 on macOS.

The plugin hosts exercise the real binaries, main and sidechain inputs, mono and
stereo, 32-bit and 64-bit buffers, automation, MIDI, latency, tempo and saved state.

## GUI and installers

- Windows native controls, curve dragging, numeric input and Details passed
  runtime checks at 100, 150 and 200 percent scaling.
- Windows installation, installed-plugin runtime, app registration, uninstall and
  preservation of an unrelated test file passed using Wine.
- The English macOS package installed successfully for the current user. Its AU
  and VST3 binaries match the validated builds.
- Public installer payloads contain English guides. The audio binaries are
  unchanged from the tested 0.3.1 builds.

## Limits

Wine tests are not a substitute for testing in a DAW on a physical Windows PC.
Physical Intel Mac testing and compatibility with every DAW are not confirmed.
These are unsigned beta installers. The macOS package is not notarized.

The release includes SHA256SUMS.txt for checking downloaded files.
