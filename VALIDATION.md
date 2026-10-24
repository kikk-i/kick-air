# Validation summary

Kick Air 0.3.2 beta, October 24, 2026.

## Checks on this build

- Universal macOS AU and VST3 builds completed for Apple Silicon and Intel.
- Native Windows x64 VST3 build completed.
- DSP regression suite: 1,426,710 assertions passed on macOS and under Wine.
- Official VST3 validator: 47 passed, 0 failed on each platform build.
- Native macOS VST3 test host: 79,631 checks passed.
- Windows VST3 test host: 79,516 checks passed using Wine 11.0 on macOS, including native controls and 100/150/200 percent DPI.
- macOS bundle signatures verified during packaging. These are ad-hoc signatures, not Developer ID signatures.
- Windows packaging verified the exact current binary and runtime evidence.
- Preset thumbnail drawing was removed from both native menus. All factory curves use the new library.

## Limits

This update was not manually retested in DAWs or installed on physical Windows or Intel Mac hardware. AU host validation and installer install/uninstall checks from 0.3.1 were not repeated for 0.3.2. Automated host checks do not establish compatibility with every DAW.

The installers are unsigned, and the macOS package is not notarized. Antivirus detections for an earlier Windows installer remain unresolved. A changed hash is not proof of safety or a fix for those detections.

SHA256SUMS.txt identifies the exact release downloads.
