<!--
==============================================================================
Document       : README.md
Project        : NoXoZ AI VoiceControl
Repository     : NoXoZ_AI_VoiceControl
Author         : Bruno DELNOZ
Developer      : @NoXoZ_be
Email          : bruno.delnoz@protonmail.com
Copyright      : © Bruno DELNOZ - NoXoZ_be
Version        : v1.0.0
Date           : 2026-06-16 03:56 CEST
Status         : Public Release
Language       : English
License        : NoXoZ Personal License v1.0
==============================================================================
-->

# NoXoZ AI VoiceControl

**Hands-free voice control for AI web chats.**

NoXoZ AI VoiceControl is a source-available browser extension that automates the repetitive voice workflow around AI web chat interfaces.

It keeps the normal text-chat experience and adds user-controlled automation around voice transcription, transcript validation, optional message sending, response completion, Read Aloud, and the start of a new transcription.

## Public release

**Current public release: v1.0.0**

This is the first public GitHub release.

## Core workflow

The complete workflow can be configured as follows:

1. Start the AI website's normal voice-to-text recording.
2. Speak normally.
3. Let the configurable silence detector decide when speaking has ended.
4. Validate the voice transcription.
5. Automatically send the transcript, or leave it in the composer for manual editing.
6. Wait until the AI response has finished.
7. Automatically start Read Aloud, or leave the response silent.
8. Stop Read Aloud manually when needed.
9. Automatically start a new transcription, or stop and wait for user input.
10. Repeat only while the user keeps the flow active.

The extension does not replace the AI model and does not create a separate conversational voice service.

## Why use it?

Native conversational voice modes are designed mainly for fluid spoken conversation.

That approach is not always suitable for long, technical, contextualized, file-based, or rule-driven work.

NoXoZ AI VoiceControl is designed for users who want to keep:

- the normal AI text-chat interface;
- editable transcripts;
- normal conversation context;
- normal written answers;
- file attachment support;
- precise timing control;
- optional automation instead of forced automation;
- the ability to stop, edit, send, listen, or restart manually.

Read the complete project background in [WHY.md](WHY.md).

## Main features

### Global control

- **ACTIVATED / NOT ACTIVATED** global flow switch.
- Automatic actions stop when the full flow is disabled.
- Manual Read Aloud controls remain available independently.

### Voice transcription workflow

- **New Transcription + TOS** control.
- Configurable **Time Of Silence**, from 0 to 30 seconds.
- Configurable microphone **Threshold**, from 0 to 100.
- Visible microphone volume level.
- Silence detection begins only during the relevant voice-transcription state.
- Background noise can be compensated for by increasing the threshold or silence duration.

### Message control

- Optional **AutoSend** after the transcript appears in the composer.
- AutoSend can be disabled to allow:
  - transcript correction;
  - additional dictation;
  - manual text editing;
  - file attachment;
  - manual sending.

### Read Aloud control

- Optional **Trigger ReadAloud** after the AI response is complete.
- **Set ReadAloud Mode** sends the configured Read Aloud activation or deactivation command to the current chat.
- **ReadAloud Last Message** manually reads the latest assistant response.
- **Stop ReadAloud** stops the current page playback.
- Manual Read Aloud controls can be used even when the full automatic flow is disabled.

### Interface modes

- Button mode.
- Mini mode.
- Maxi mode.
- Draggable on-page widget.
- Visible public version information.
- Developer contact through **@NoXoZ_be**.

### Platform profiles

The runtime contains profiles for:

- ChatGPT;
- Claude.

The first public release is validated primarily for **ChatGPT Web**.

The Claude profile is present for continued adaptation, but full Claude workflow compatibility is not claimed for public v1.0.0.

## Browser compatibility

The extension uses Manifest V3 and targets Chromium-based browsers.

Primary browser targets:

- Brave Browser;
- Google Chrome;
- Chromium.

Firefox is not supported by this release.

Browser interfaces change over time. A future website update may require selector or workflow updates in the extension.

## Supported web addresses

The runtime declares access only to these AI web origins:

- `https://chatgpt.com/*`
- `https://chat.openai.com/*`
- `https://claude.ai/*`
- `https://www.claude.ai/*`

## Required browser permissions

The extension currently requests:

- `storage` — store extension settings locally;
- `tabs` — communicate with the active supported tab;
- `activeTab` — operate only on the current active tab when requested;
- `scripting` — inject the extension runtime and styles when necessary.

## Privacy summary

NoXoZ AI VoiceControl v1.0.0 contains:

- no NoXoZ account system;
- no advertising;
- no analytics;
- no telemetry;
- no tracking code;
- no NoXoZ cloud backend;
- no extension-owned remote API;
- no audio-upload service operated by NoXoZ.

The extension stores configuration values in the browser's local extension storage.

Microphone access is used by the browser-side silence and volume monitor when the related feature is active.

The AI website still processes the content that the user sends to it. Messages, transcripts, attached files, responses, and provider-side voice features remain subject to the terms and privacy policy of the selected AI service.

## Installation

NoXoZ AI VoiceControl is currently distributed through its public GitHub repository for manual installation in Developer mode.

Read [INSTALL.md](INSTALL.md) for the complete installation, first-run, update, and removal procedure.

## Repository

Project repository:

`https://github.com/bdelnoz/NoXoZ_AI_VoiceControl`

The public repository name and the recommended local folder name are both:

`NoXoZ_AI_VoiceControl`

## Feedback and contact

Developer:

**Bruno DELNOZ — @NoXoZ_be**

Primary feedback email used by the extension:

`noxoz_be@proton.me`

Repository metadata email:

`bruno.delnoz@protonmail.com`

When reporting a problem, include:

- operating system;
- browser name and version;
- extension version;
- AI website;
- interface language;
- activated controls;
- Time Of Silence value;
- Threshold value;
- expected behavior;
- observed behavior.

Do not send private conversations, passwords, access tokens, confidential files, or other sensitive data unless they are strictly necessary and have been properly removed or redacted.

## License

NoXoZ AI VoiceControl is proprietary, source-available software.

The official unmodified release may be downloaded, installed, and used for personal, non-commercial purposes under the [NoXoZ Personal License v1.0](LICENSE).

The license does not grant permission to:

- redistribute the extension;
- publish modified versions;
- sell or rent it;
- repackage it;
- upload it to a browser store;
- integrate it into a commercial product or service;
- remove the author's identity or copyright;
- publish it under another name.

## Independent project notice

NoXoZ AI VoiceControl is an independent project.

It is not affiliated with, endorsed by, sponsored by, or officially supported by OpenAI, Anthropic, Google, xAI, Brave, Chromium, Chrome, or any other AI or browser vendor.

ChatGPT, Claude, Brave, Chrome, Chromium, and all other third-party names, products, services, and trademarks belong to their respective owners.

## Author

**Bruno DELNOZ**  
Developer identity: **@NoXoZ_be**  
Belgium

## Firefox WebExtension build

The same runtime can now be loaded in Firefox as a WebExtension from the repository root `manifest.json`. Firefox-specific compatibility is handled by Gecko manifest metadata plus a cross-browser popup bridge that supports both `browser.*` Promise APIs and Chromium/Brave `chrome.*` callback APIs. See [FIREFOX.md](FIREFOX.md) for temporary-install steps and parity notes.
