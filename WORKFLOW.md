<!--
==============================================================================
Document       : WORKFLOW.md
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
Description    : Complete operational workflow and state behavior of NoXoZ AI VoiceControl.
==============================================================================
-->

# Workflow

## 1. Purpose

NoXoZ AI VoiceControl adds a configurable voice workflow around a normal AI web chat.

The extension does not replace the AI model or the website's own text composer.

It coordinates selected actions in this order:

1. voice transcription;
2. silence detection;
3. transcript validation;
4. optional AutoSend;
5. assistant-response monitoring;
6. optional Read Aloud;
7. optional new transcription;
8. waiting or repeating.

## 2. Public and internal versioning

The first public GitHub release is:

`v1.0.0`

The validated internal runtime used for this release displays:

`v8.0.0`

The widget shows the internal runtime version because it identifies the exact JavaScript workflow baseline.

Public support and GitHub release references should use `v1.0.0`.

## 3. First-run state

On first initialization of the validated runtime, the default state is:

- Full Flow: **NOT ACTIVATED**;
- New Transcription + TOS: enabled;
- AutoSend: enabled;
- Trigger ReadAloud: enabled;
- Set ReadAloud Mode state: disabled;
- Time Of Silence: 3 seconds;
- Threshold: 35;
- interface: Maxi mode;
- widget: visible;
- platform: selected from the current hostname.

The global Full Flow remains disabled by default so that installation does not immediately start an automatic cycle.

## 4. Main controls

## 4.1 ACTIVATED / NOT ACTIVATED

This is the global Full Flow control.

When **NOT ACTIVATED**:

- the complete automatic voice loop does not run;
- automatic silence processing does not control the full cycle;
- automatic sending is not triggered as part of the full loop;
- automatic post-response Read Aloud does not start as part of the full loop;
- automatic new transcription does not start as part of the full loop.

Manual Read Aloud controls remain available.

When **ACTIVATED**:

- each enabled workflow module may participate in the cycle;
- disabled modules remain disabled;
- the extension follows the current combination of New Transcription + TOS, AutoSend, and Trigger ReadAloud.

## 4.2 New Transcription + TOS

This control combines:

- automatic new transcription;
- microphone monitoring;
- Time Of Silence;
- transcript-finish validation.

When enabled, the extension can:

- prepare the next voice-transcription cycle;
- monitor microphone level;
- detect meaningful sound;
- detect silence after speech;
- activate the website's finish-transcription control;
- start another transcription after the previous response cycle, when allowed.

When disabled:

- the extension does not run the automatic TOS-based transcription workflow;
- the user may still operate the website's voice-transcription controls manually;
- manual transcript validation may still be followed by AutoSend when the relevant state is detected.

## 4.3 AutoSend

When enabled:

- the extension waits for transcript text to appear in the composer;
- it waits for the composer text to become stable;
- it activates the website's normal Send action;
- duplicate immediate sends are guarded by runtime cooldown and message-state checks.

When disabled:

- the transcript remains unsent in the composer;
- the user can correct it;
- the user can append text;
- the user can continue dictating;
- the user can attach files;
- the user can send manually;
- the full cycle waits for a user action rather than forcing the message to send.

## 4.4 Trigger ReadAloud

When enabled:

- the extension waits until the assistant response appears complete;
- it looks for the website's normal Read Aloud action;
- it starts Read Aloud when the action becomes available;
- it monitors for the corresponding Stop Read Aloud state;
- after playback ends, it may continue to the next enabled workflow step.

When disabled:

- no automatic Read Aloud is started after the response;
- the extension may continue to a new transcription if that module is enabled;
- otherwise it waits for user input.

## 4.5 Set ReadAloud Mode

This manual control sends one of these literal messages to the current chat:

- `activation mode Read Aloud`
- `désactivation mode Read Aloud`

The control alternates between activation and deactivation.

This feature is intended for chats that understand user-defined Read Aloud response rules.

The extension does not itself control how the AI interprets those messages.

The action is blocked while active voice recording is detected, preventing the mode command from interfering with the current recording.

## 4.6 ReadAloud Last Message

This manual control attempts to activate the website's Read Aloud action for the latest assistant message.

It works independently from the global Full Flow state.

It is useful when:

- automatic Trigger ReadAloud is disabled;
- the user wants to replay the latest answer;
- the full workflow has been stopped;
- the user wants only reading, not transcription or sending.

## 4.7 Stop ReadAloud

This manual control activates the website's visible Stop Read Aloud action.

It applies to:

- automatically triggered playback;
- manually started playback.

It remains available when Full Flow is disabled.

## 4.8 Time Of Silence

Time Of Silence defines how long the microphone level must remain below the Threshold after meaningful sound has been detected.

Supported range:

- minimum: 0 seconds;
- maximum: 30 seconds;
- default: 3 seconds;
- step: 1 second.

The timer does not represent total recording time.

It represents continuous detected silence after speech.

## 4.9 Threshold

Threshold defines the microphone level that separates meaningful sound from silence for the extension's analyser.

Supported range:

- minimum: 0;
- maximum: 100;
- default: 35;
- step: 5.

A higher Threshold ignores more background noise.

A Threshold that is too high may ignore quiet speech.

A Threshold that is too low may allow television, fans, music, or room noise to prevent silence detection.

## 4.10 Volume meter

The visible volume meter shows the current analyser level.

It helps compare:

- current room noise;
- current voice level;
- selected Threshold.

The meter is a local visual aid.

It is not an audio recorder.

## 4.11 Reload Ext

This control requests an extension runtime reload and refreshes the current tab.

It is intended for development, recovery, and selector-update testing.

The operation can interrupt an active workflow.

Do not use it during an important unsent transcription.

## 4.12 Mode: ChatGPT / Claude

This control switches between the two runtime profiles.

The current hostname selects an initial profile on first run:

- ChatGPT hosts select ChatGPT;
- Claude hosts select Claude.

The public v1.0.0 workflow is validated primarily for ChatGPT.

The Claude profile exists for continued adaptation and does not represent full validated Claude compatibility.

## 5. Interface modes

## 5.1 Maxi mode

Maxi mode displays the complete control set, including:

- full labels;
- TOS controls;
- Threshold controls;
- volume meter;
- status;
- manual Read Aloud group;
- developer contact;
- runtime version;
- Reload Ext;
- platform profile.

## 5.2 Mini mode

Mini mode keeps the main controls in a compact layout.

Labels may be shortened.

The core state remains unchanged.

## 5.3 Button mode

Button mode reduces the widget to a compact restore control.

The workflow state may continue according to active settings.

Button mode changes presentation, not the configured workflow.

## 5.4 Dragging and position

The widget can be moved by dragging its header.

The horizontal and vertical position are stored locally.

Viewport-correction logic attempts to keep the widget accessible after resizing or reloading.

## 6. Full automatic cycle

A normal fully enabled cycle is:

1. Full Flow is ACTIVATED.
2. New Transcription + TOS is enabled.
3. AutoSend is enabled.
4. Trigger ReadAloud is enabled.
5. The extension starts or detects voice transcription.
6. The microphone analyser waits for meaningful sound.
7. The user speaks.
8. The analyser records that voice has been seen.
9. The microphone level remains below Threshold.
10. The Time Of Silence expires.
11. The extension activates the website's finish-transcription control.
12. The website places the transcript in the composer.
13. The extension waits for stable non-empty composer text.
14. The extension activates Send.
15. The extension waits while the assistant thinks and writes.
16. The extension waits until response completion is detected.
17. The extension starts Read Aloud.
18. Voice recording remains blocked during active Read Aloud.
19. The extension waits for Read Aloud to finish or be stopped.
20. The next transcription starts when enabled and safe.
21. The cycle repeats.

## 7. AutoSend disabled workflow

With AutoSend disabled:

1. speech is transcribed;
2. Time Of Silence may validate transcription;
3. transcript text appears in the composer;
4. the extension does not send it;
5. the user edits, adds files, continues dictating, sends manually, or discards the draft;
6. the post-send workflow begins only after a real message is sent.

This mode is recommended for requests requiring file attachment or transcript correction.

## 8. Trigger ReadAloud disabled workflow

With Trigger ReadAloud disabled:

1. the message is sent manually or automatically;
2. the extension waits for the response to complete;
3. no automatic reading begins;
4. a new transcription may start if New Transcription + TOS is enabled;
5. otherwise the extension waits for user input.

The latest message can still be read manually with **ReadAloud Last Message**.

## 9. New Transcription + TOS disabled workflow

With New Transcription + TOS disabled:

- the user controls voice-transcription start and finish manually;
- the extension does not run automatic silence validation;
- AutoSend may still send a completed manually validated transcript when enabled;
- Trigger ReadAloud may still read the resulting assistant response when enabled;
- no automatic next transcription is started.

## 10. Full Flow disabled workflow

With Full Flow disabled:

- automatic orchestration stops;
- the user continues using the AI website normally;
- manual Read Aloud controls remain available;
- settings can still be changed;
- widget display modes can still be changed;
- the extension can be reactivated later.

## 11. Voice and Read Aloud interlock

Voice recording and Read Aloud are intentionally treated as mutually exclusive.

The extension avoids starting real microphone activity while Read Aloud is active.

A next-transcription request may be pre-armed while the assistant is thinking or writing, but actual voice recording waits until the pending Read Aloud cycle is complete.

This prevents the page's spoken response from being captured as the user's next dictation.

## 12. Status behavior

The widget status field reports the current operational state.

Examples may include:

- Full Flow disabled;
- microphone ready;
- microphone denied;
- sound above Threshold;
- silence timing;
- transcript validation;
- waiting for transcript;
- waiting for response;
- Read Aloud active;
- waiting for user input;
- runtime error.

Status text is diagnostic and may change between runtime versions.

## 13. Stored state

The extension stores current settings locally so that the interface can restore:

- module states;
- TOS;
- Threshold;
- display mode;
- position;
- visibility;
- platform profile.

A new internal runtime version may deliberately reinitialize defaults for that version.

## 14. Recovery workflow

When the website interface or extension context becomes stale:

1. stop or preserve any important unsent draft;
2. click **Reload Ext** or reload the extension from the browser extensions page;
3. reload the AI website tab;
4. reopen the widget from the toolbar icon;
5. verify current controls;
6. perform a short test before a long dictation.

## 15. Workflow limits

The extension cannot guarantee a cycle when:

- the AI website changes its interface;
- required controls are missing;
- microphone permission is denied;
- browser extension APIs are restricted;
- the page is not on a supported origin;
- the response never reaches a detectable complete state;
- Read Aloud is unavailable for the response;
- the browser suspends or reloads the tab;
- another extension changes the same page controls.

## 16. User responsibility

Before enabling AutoSend for important content:

- confirm the correct chat is open;
- confirm the correct platform profile;
- confirm attached files are present;
- confirm TOS and Threshold are suitable;
- confirm that automatic sending is appropriate;
- avoid speaking confidential information into the wrong chat;
- stop Full Flow before changing critical account or page state.
