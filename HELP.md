<!--
==============================================================================
Document       : HELP.md
Project        : NoXoZ AI VoiceControl
Repository     : NoXoZ_AI_VoiceControl
Author         : Bruno DELNOZ
Developer      : @NoXoZ_be
Email          : bruno.delnoz@protonmail.com
Copyright      : © Bruno DELNOZ - NoXoZ_be
Version        : v1.0.0
Date           : 2026-06-16 04:01 CEST
Status         : Public Release
Language       : English
License        : NoXoZ Personal License v1.0
Description    : User help, quick reference, operating guidance and troubleshooting.
==============================================================================
-->

# Help

## 1. Quick start

1. Install the extension as described in [INSTALL.md](INSTALL.md).
2. Open ChatGPT Web.
3. Reload the tab once after installation.
4. Click the **AI Voice Control** toolbar icon.
5. Open Maxi mode.
6. Check the current platform profile.
7. Set Time Of Silence.
8. Set Threshold while watching the volume meter.
9. Choose whether AutoSend is enabled.
10. Choose whether Trigger ReadAloud is enabled.
11. Activate Full Flow.
12. Start the website's normal voice transcription.
13. Speak a short test request.
14. Stop speaking and observe the cycle.

## 2. Button reference

### ACTIVATED / NOT ACTIVATED

Controls the complete automatic workflow.

- **ACTIVATED**: enabled modules can run.
- **NOT ACTIVATED**: the automatic workflow is stopped.

Manual Read Aloud controls remain available.

### New Transcription + TOS

Controls:

- microphone level monitoring;
- Time Of Silence;
- automatic transcription validation;
- optional new-transcription restart.

### AutoSend

Controls automatic sending after a transcript appears.

Disable it when you need to:

- correct the transcript;
- add text;
- attach a file;
- continue dictating;
- send manually.

### Trigger ReadAloud

Controls automatic Read Aloud after the assistant response is complete.

### Set ReadAloud Mode

Sends a mode command into the current chat:

- activation: `activation mode Read Aloud`
- deactivation: `désactivation mode Read Aloud`

This changes the chat only if the AI understands or has rules for those commands.

### ReadAloud Last Message

Manually starts Read Aloud for the latest assistant message.

### Stop ReadAloud

Stops current page playback.

### TOS Sec

Changes Time Of Silence in one-second steps.

Range:

- 0 to 30 seconds.

### Threshold

Changes microphone Threshold in five-point steps.

Range:

- 0 to 100.

### Vol

Displays current microphone analyser level.

### Reload Ext

Reloads the extension runtime and refreshes the current tab.

### Mode: ChatGPT / Claude

Switches the runtime profile.

Public v1.0.0 is primarily validated on ChatGPT.

### Plus and minus controls

- plus opens or keeps Maxi mode;
- minus changes from Maxi to Mini, then toward compact Button mode;
- double-click behavior may restore the compact interface.

## 3. Suggested settings

### Fast short prompts

- TOS: 2 to 3 seconds;
- Threshold: start at 35;
- AutoSend: enabled;
- Trigger ReadAloud: enabled or disabled according to preference.

### Long technical dictation

- TOS: 5 to 10 seconds;
- Threshold: adjusted to room noise;
- AutoSend: disabled until the transcript is verified;
- Trigger ReadAloud: optional.

### Noisy room

- TOS: 4 to 8 seconds;
- Threshold: increase until background noise stays mostly below it;
- check that normal speech still rises above it.

### File-based request

- AutoSend: disabled;
- dictate the request;
- wait for the transcript;
- attach the file;
- review the composer;
- send manually.

## 4. Reading the volume meter

The volume meter shows a value from the local analyser.

When speaking:

- the level should rise above Threshold.

When silent:

- the level should remain below Threshold.

The silence timer begins only after meaningful sound has been detected.

If the level never falls below Threshold, silence cannot complete.

If normal speech never rises above Threshold, voice may not be recognized by the extension's silence logic.

## 5. Common status meanings

### Mic ready

Microphone access and the local analyser are ready.

### Mic denied

The browser denied microphone access or no usable input was available.

### No getUserMedia

The browser does not expose the required microphone API in the current context.

### No AudioContext

The required Web Audio API is unavailable.

### Sound VOL greater than THR

The current analyser level is above Threshold.

The extension treats the input as sound rather than silence.

### Waiting transcript

The extension has requested transcription completion and is waiting for text.

### Draft ready / waiting user

AutoSend is disabled and the transcript is available for manual action.

### Waiting response

A message was sent and the extension is waiting for the assistant.

### ReadAloud active

The page appears to be reading an assistant response.

### Waiting user input

The current automated path has completed and no automatic next action is enabled.

### Runtime error

A local browser or page interaction failed.

Open the browser console for technical detail when needed.

## 6. Troubleshooting

## 6.1 The extension icon does nothing

Check:

- current tab uses a supported URL;
- the extension is enabled;
- the correct unpacked directory is loaded;
- `manifest.json` is at the selected directory root;
- the AI tab was reloaded after installation.

Then:

1. open the browser extensions page;
2. click Reload for **AI Voice Control**;
3. reload the AI tab;
4. click the toolbar icon again.

## 6.2 The widget does not appear

Possible causes:

- current page is unsupported;
- content script did not load;
- widget is in compact Button mode;
- widget position was restored outside the currently visible layout;
- the AI page was open before the extension loaded.

Actions:

- reload the AI page;
- click the toolbar icon;
- use Reload Ext;
- reset browser zoom temporarily;
- maximize the browser window.

## 6.3 Microphone permission was denied

Open the site's browser permissions and allow microphone access.

Confirm that:

- the correct input device is selected;
- no operating-system privacy rule blocks the browser;
- another application is not exclusively locking the microphone;
- the page is using HTTPS.

After correcting permission, reload the AI tab.

## 6.4 Volume always shows zero

Check:

- microphone permission;
- system input selection;
- headset mute switch;
- browser input selection;
- operating-system recording level;
- whether another application has the device;
- whether New Transcription + TOS is active in the relevant workflow state.

## 6.5 The silence timer never finishes

Likely causes:

- background sound remains above Threshold;
- Threshold is too low;
- television or music is active;
- microphone automatic gain keeps raising room noise;
- the user continues making small sounds;
- TOS is longer than expected.

Actions:

- increase Threshold by 5;
- observe Vol while silent;
- reduce environmental noise;
- use a closer microphone;
- retest with a short phrase.

## 6.6 The message finishes too early

Likely causes:

- TOS is too short;
- Threshold is too high and quiet speech is treated as silence;
- the user pauses for longer than TOS while thinking.

Actions:

- increase TOS;
- lower Threshold carefully;
- disable AutoSend while adjusting;
- use manual validation for very long prompts.

## 6.7 Transcript appears but is not sent

Check:

- Full Flow is ACTIVATED;
- AutoSend is enabled;
- the composer contains non-empty text;
- the website Send button is available;
- the website is not still processing transcription;
- the website did not redesign the composer.

When AutoSend is intentionally disabled, this is expected behavior.

## 6.8 Transcript is sent to the wrong chat

The extension acts on the active supported tab.

Before activating Full Flow:

- open the intended chat;
- verify the page title and conversation;
- avoid switching active AI tabs during critical send transitions.

## 6.9 Read Aloud does not start automatically

Check:

- Trigger ReadAloud is enabled;
- Full Flow is ACTIVATED;
- the response is fully finished;
- the page provides Read Aloud for that response;
- no voice recording is active;
- the website interface has not changed.

Try **ReadAloud Last Message** manually.

## 6.10 ReadAloud Last Message does not work

Possible causes:

- no assistant response exists;
- the page has no Read Aloud action;
- the action is hidden in a changed menu;
- the website changed labels or DOM structure;
- playback is already active.

Reload the page and try again.

## 6.11 Stop ReadAloud does not work

Check whether the website currently shows its Stop Read Aloud control.

A website update may have changed the relevant button or label.

Use the website's own playback control as a fallback.

## 6.12 A new transcription starts at the wrong time

Voice recording and Read Aloud are designed to be mutually exclusive.

Check:

- Trigger ReadAloud state;
- whether playback actually stopped;
- whether the page still exposes a Stop Read Aloud state;
- whether New Transcription + TOS was pre-armed during response generation.

Disable Full Flow before manual recovery.

## 6.13 Reload Ext interrupts the workflow

This is expected.

Reload Ext refreshes runtime context and the current page.

Do not use it while:

- a long transcript is unsent;
- an important file selection is pending;
- the assistant is generating a response you do not want interrupted.

## 6.14 Claude mode does not complete the workflow

The Claude profile is present for adaptation but full Claude support is not claimed for public v1.0.0.

Switching the label to Claude does not guarantee that all Claude selectors and states match ChatGPT behavior.

## 6.15 The browser shows a Developer mode warning

Manual unpacked extensions may produce a browser warning.

This is normal for Developer mode installation.

Install only from the official repository and review the source when desired.

## 7. Safe recovery procedure

When the workflow becomes confused:

1. copy any important unsent transcript;
2. click NOT ACTIVATED;
3. stop Read Aloud manually;
4. close any active website voice recording;
5. reload the AI tab;
6. reopen the widget;
7. confirm platform, TOS, Threshold, AutoSend, and Trigger ReadAloud;
8. perform a short test;
9. reactivate the full workflow.

## 8. Reporting a problem

Use [FEEDBACK.md](FEEDBACK.md).

Include:

- public version `v1.0.0`;
- internal runtime version shown in the widget;
- browser and version;
- operating system;
- AI website;
- interface language;
- active controls;
- TOS;
- Threshold;
- exact step that failed;
- expected result;
- actual result.

Do not send private conversation content unless it has been redacted.

## 9. Privacy and license

Read:

- [PRIVACY.md](PRIVACY.md)
- [LICENSE](LICENSE)
