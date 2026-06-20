# Firefox version

This repository now ships the same AI Voice Control runtime as a Firefox-compatible WebExtension.

## What changed for Firefox

- The main `manifest.json` remains Manifest V3 and declares Firefox Gecko metadata through `browser_specific_settings`.
- The Chromium-only `version_name` field was removed because Firefox does not accept it for add-on loading.
- The toolbar popup bridge now supports both extension API styles:
  - Firefox `browser.*` Promise APIs;
  - Chromium/Brave `chrome.*` callback APIs.
- The content script now reads extension storage, receives toolbar toggle messages, and reloads the extension through the available `browser.*` or `chrome.*` namespace.

## Installation in Firefox Developer Edition / Nightly / temporary install

1. Open `about:debugging#/runtime/this-firefox`.
2. Click **Load Temporary Add-on…**.
3. Select this repository's `manifest.json` file.
4. Open `https://chatgpt.com/`, `https://chat.openai.com/`, or `https://claude.ai/`.
5. Click the AI Voice Control toolbar icon to show, hide, or reinject the widget.

## Runtime parity

The Firefox build keeps the same content script, CSS, popup UI, ChatGPT DOM controllers, Claude clone profile, storage keys, widget modes, ReadAloud controls, AutoSend flow, and toolbar show/hide behavior as the Chromium/Brave build.
