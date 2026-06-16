<!--
==============================================================================
Document       : INSTALL.md
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

# Installing NoXoZ AI VoiceControl

This document explains how to install the public v1.0.0 release manually from GitHub in a Chromium-based browser.

No browser-store purchase or subscription is required.

## Supported installation targets

The public release is intended for:

- Brave Browser;
- Google Chrome;
- Chromium.

The extension uses Manifest V3.

Firefox installation is not supported by this release.

## Before installation

You need:

- a supported Chromium-based browser;
- access to the public GitHub repository;
- permission to install unpacked extensions;
- microphone access for silence and volume monitoring;
- an AI web account for the service you use.

The primary validated AI target for public v1.0.0 is ChatGPT Web.

A Claude profile is included in the runtime for continued adaptation, but full Claude workflow compatibility is not claimed for this release.

## Official repository

Repository:

`https://github.com/bdelnoz/NoXoZ_AI_VoiceControl`

Use the official repository as the source of the extension.

Do not install repackaged copies from unknown websites, mirrors, browser stores, file-sharing services, or third-party repositories.

## Method 1 — Download the repository ZIP

### Step 1 — Download

1. Open the official GitHub repository.
2. Click the green **Code** button.
3. Click **Download ZIP**.
4. Save the ZIP file locally.

### Step 2 — Extract

1. Extract the downloaded ZIP.
2. Move the extracted directory to a permanent location.
3. Keep the directory name clear, for example:

`NoXoZ_AI_VoiceControl`

The selected extension directory must contain `manifest.json`.

Do not select the parent directory if `manifest.json` is inside a nested folder.

Do not delete or move the extension directory after installation unless you intend to reinstall it.

## Open the extensions page

### Brave Browser

Open:

`brave://extensions`

### Google Chrome

Open:

`chrome://extensions`

### Chromium

Open:

`chrome://extensions`

## Enable Developer mode

On the browser extensions page:

1. Locate the **Developer mode** switch.
2. Enable it.
3. Additional extension-management buttons will appear.

Manual GitHub installation requires Developer mode because the extension is not being installed from the Chrome Web Store.

## Load the unpacked extension

1. Click **Load unpacked**.
2. Browse to the permanent extension directory.
3. Select the directory containing `manifest.json`.
4. Confirm the selection.

The browser should display:

- extension name: **AI Voice Control**;
- public project: **NoXoZ AI VoiceControl**;
- extension icon;
- version information;
- requested permissions.

## Pin the extension

To keep the extension accessible:

1. Open the browser extensions menu in the toolbar.
2. Find **AI Voice Control**.
3. Pin it to the toolbar.

The toolbar icon opens or toggles the on-page extension interface on supported AI websites.

## Supported websites

The runtime declares access to:

- `https://chatgpt.com/*`
- `https://chat.openai.com/*`
- `https://claude.ai/*`
- `https://www.claude.ai/*`

The primary validated public target is ChatGPT Web.

## First start

1. Open a supported AI website.
2. Reload the AI tab once after installation if it was already open.
3. Click the **AI Voice Control** toolbar icon.
4. The extension widget should appear on the page.
5. Choose Mini or Maxi mode as needed.
6. Review the workflow controls before activation.

## Main controls

The current interface includes controls for:

- Full Flow activation;
- New Transcription + TOS;
- AutoSend;
- Trigger ReadAloud;
- Time Of Silence;
- microphone Threshold;
- Set ReadAloud Mode;
- ReadAloud Last Message;
- Stop ReadAloud;
- ChatGPT / Claude profile selection;
- Mini / Maxi / Button display modes.

## Recommended first test

Use a short test before starting a long dictation.

1. Keep Full Flow disabled.
2. Open Maxi mode.
3. Confirm that the platform profile matches the current website.
4. Set Time Of Silence to approximately 3 to 5 seconds.
5. Set the Threshold according to the visible microphone level.
6. Enable New Transcription + TOS.
7. Decide whether AutoSend should be active.
8. Decide whether Trigger ReadAloud should be active.
9. Activate Full Flow.
10. Start the website's normal voice transcription.
11. Speak a short test message.
12. Stop speaking and observe the workflow.

## Microphone permission

The silence and volume monitor uses the browser's microphone permission.

The first time the feature starts, the browser may ask for microphone access.

Choose the microphone used for dictation and allow access for the AI website when you want Time Of Silence monitoring to work.

If permission is denied:

- the extension cannot measure microphone volume;
- threshold monitoring cannot work;
- automatic silence-triggered transcription completion may not work.

The extension does not operate a NoXoZ audio-upload server.

## Choosing Time Of Silence

Time Of Silence controls how long the detected sound level must remain below the threshold before the extension requests transcription completion.

The runtime supports:

- minimum: 0 seconds;
- maximum: 30 seconds;
- default: 3 seconds.

Suggested starting values:

- 3 seconds for short direct prompts;
- 5 seconds for normal technical dictation;
- 8 to 12 seconds when you pause frequently to think.

These are starting suggestions, not mandatory values.

## Choosing the Threshold

Threshold controls which microphone level is treated as meaningful sound.

The runtime supports:

- minimum: 0;
- maximum: 100;
- default: 35.

Use the visible microphone level as a guide.

If background television or room noise prevents the silence timer from completing, increase the threshold carefully.

If the extension treats quiet speech as silence, lower the threshold.

## AutoSend behavior

When AutoSend is enabled:

- the extension waits for transcript text to appear;
- it sends the transcript through the normal AI web composer.

When AutoSend is disabled:

- the transcript remains in the composer;
- you can edit it;
- you can continue dictating;
- you can attach files;
- you can send manually.

## Read Aloud behavior

When Trigger ReadAloud is enabled:

- the extension waits for the assistant response to finish;
- it attempts to start the page's normal Read Aloud action.

Use **Stop ReadAloud** to stop current playback.

Use **ReadAloud Last Message** to manually read the latest assistant response.

Use **Set ReadAloud Mode** to send the configured Read Aloud mode command to the current chat.

The AI's reaction to that command depends on the chat's own instructions and the AI service.

## Updating the unpacked extension

When a new public release is available:

1. Download the new official release.
2. Extract it to a permanent directory.
3. Keep a backup of your previous official release if needed.
4. Replace the old runtime files with the new official files, or load the new extracted directory.
5. Open the browser extensions page.
6. Locate **AI Voice Control**.
7. Click **Reload**.
8. Reload all open supported AI tabs.

If you changed the extension directory, use **Load unpacked** and select the new directory containing `manifest.json`.

## Removing the extension

1. Open the browser extensions page.
2. Locate **AI Voice Control**.
3. Click **Remove**.
4. Confirm removal.
5. Delete the local extension directory only after the browser has removed the extension.

## Troubleshooting

### The toolbar icon does nothing

- Confirm that the current tab is a supported AI website.
- Reload the AI tab.
- Reload the extension from the extensions page.
- Click the toolbar icon again.

### The widget is not visible

- Click the toolbar icon.
- Check whether Button mode or Mini mode is active.
- Reload the AI tab.
- Confirm that the content script is allowed on the current website.

### The silence timer never completes

- Check microphone permission.
- Check the visible microphone volume.
- Increase the threshold if constant background noise remains above it.
- Increase the Time Of Silence if pauses are too short.

### The message sends too early

- Increase Time Of Silence.
- Lower the threshold if quiet speech is being ignored.
- Disable AutoSend while testing.

### The transcript appears but is not sent

- Confirm that AutoSend is enabled.
- Confirm that Full Flow is activated.
- Check whether the AI website changed its composer or Send button interface.

### Read Aloud does not start

- Confirm that Trigger ReadAloud is enabled.
- Confirm that the AI response has fully completed.
- Check whether the AI website currently provides a Read Aloud action.
- Try **ReadAloud Last Message** manually.
- A website-interface update may require an extension update.

### New transcription does not start

- Confirm that New Transcription + TOS is enabled.
- Confirm that Full Flow is activated.
- Confirm that Read Aloud has ended or has been stopped.
- Confirm that the AI website's voice-transcription control is available.

## Security note

Only install the extension from the official repository or an official release published by Bruno DELNOZ / @NoXoZ_be.

Review the source before installation when desired.

Do not install modified copies that claim to be official.

## License

Installation and use are subject to the [NoXoZ Personal License v1.0](LICENSE).

The official unmodified extension may be installed and used for personal, non-commercial purposes.

Redistribution, resale, repackaging, browser-store publication, and distribution of modified versions require prior written authorization.
