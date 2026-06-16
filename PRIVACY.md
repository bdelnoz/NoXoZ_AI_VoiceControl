<!--
==============================================================================
Document       : PRIVACY.md
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
Description    : Privacy information for the NoXoZ AI VoiceControl public release.
==============================================================================
-->

# Privacy Policy

## 1. Scope

This privacy document applies to the official **NoXoZ AI VoiceControl v1.0.0** public release distributed from:

`https://github.com/bdelnoz/NoXoZ_AI_VoiceControl`

It describes what the extension itself processes, what it stores locally, what it does not transmit, and which data remains under the responsibility of the AI website and browser used by the user.

## 2. Privacy summary

NoXoZ AI VoiceControl is designed as a local browser-side workflow extension.

The official v1.0.0 release contains:

- no NoXoZ user-account system;
- no NoXoZ cloud backend;
- no analytics service;
- no advertising system;
- no telemetry pipeline;
- no tracking pixel;
- no remote configuration service;
- no extension-owned transcription server;
- no extension-owned audio-upload service;
- no automatic crash-reporting service;
- no payment or subscription system.

The extension does not include `fetch`, `XMLHttpRequest`, WebSocket, EventSource, or beacon-based network communication in its runtime.

## 3. Data processed by the extension

The extension processes only the information needed to control the supported AI web interface.

This may include:

- the current supported website address;
- the current browser tab identifier;
- the visible state of the AI web interface;
- whether voice transcription appears active;
- whether a transcript appears in the message composer;
- whether a send control is available;
- whether the assistant appears to be thinking, writing, or finished;
- whether a Read Aloud control or Stop Read Aloud control is visible;
- the user-selected extension settings;
- microphone amplitude used for silence detection.

The extension reads and interacts with visible page elements in order to automate selected browser actions.

## 4. Message and transcript handling

The extension may inspect the current message composer to determine whether transcribed text is present and stable enough for optional AutoSend.

It may then activate the website's normal Send control when AutoSend is enabled.

The extension does not operate its own message server.

The message, transcript, attachments, and resulting AI response are processed by the selected AI website according to that provider's own terms and privacy policy.

When AutoSend is disabled, the transcript remains in the website composer so that the user can edit, extend, attach files, send manually, or discard it.

## 5. Microphone access

The **New Transcription + TOS** function uses browser microphone access to measure sound amplitude.

The runtime requests:

- one audio channel;
- a nominal sample rate of 16000 Hz;
- no video.

The extension creates a browser audio analyser and uses the measured level to compare current sound with the configured Threshold.

The extension does not contain a MediaRecorder-based audio-recording function.

The extension does not deliberately save microphone audio to a file.

The extension does not deliberately upload microphone audio to a NoXoZ server.

Microphone samples used by the analyser are processed in browser memory for volume and silence detection.

The AI website may separately use microphone access for its own voice-transcription feature. That provider-side recording and transcription process is outside the extension's privacy control.

## 6. Local browser storage

The extension uses `chrome.storage.local` to preserve user settings.

Stored settings may include:

- Full Flow enabled or disabled;
- New Transcription + TOS enabled or disabled;
- Time Of Silence value;
- microphone Threshold value;
- widget horizontal and vertical position;
- Button, Mini, or Maxi display state;
- widget visibility;
- AutoSend enabled or disabled;
- Read Aloud mode command state;
- Trigger ReadAloud enabled or disabled;
- selected ChatGPT or Claude runtime profile;
- internal runtime version used to initialize defaults.

These values are configuration settings.

They are not an extension-owned copy of the user's AI conversation.

The official runtime does not deliberately store complete chat messages, complete transcripts, assistant responses, passwords, access tokens, attached files, or microphone recordings in extension storage.

## 7. First-run defaults

On first initialization of the validated runtime used for public v1.0.0, the extension sets these local defaults:

- Full Flow: disabled;
- New Transcription + TOS: enabled;
- Time Of Silence: 3 seconds;
- Threshold: 35;
- AutoSend: enabled;
- Set ReadAloud Mode state: disabled;
- Trigger ReadAloud: enabled;
- interface: visible in Maxi mode;
- platform profile: selected from the current supported hostname.

These values remain local to the browser profile unless the user changes or removes them.

## 8. Browser permissions

The extension requests the following Manifest V3 permissions.

### `storage`

Used to save extension settings locally.

### `tabs`

Used to identify and communicate with the active supported browser tab.

### `activeTab`

Used to operate on the active supported tab when the user invokes the extension.

### `scripting`

Used to inject or restore the extension content script and stylesheet when the supported page is already open or when the toolbar bridge must recover the widget.

## 9. Website access

The official runtime declares host access only for:

- `https://chatgpt.com/*`
- `https://chat.openai.com/*`
- `https://claude.ai/*`
- `https://www.claude.ai/*`

The extension does not declare general access to every website.

## 10. External communications

The extension does not automatically send feedback, diagnostics, settings, chat content, or usage statistics to Bruno DELNOZ or NoXoZ.

Clicking the visible **@NoXoZ_be** contact link opens a normal `mailto:` link in the user's configured email application.

No email is sent automatically.

The user decides whether to compose and send that email and which information to include.

## 11. Console logging

The runtime may write technical status and error information to the browser developer console.

These logs are intended for local diagnosis.

The official runtime does not include an automatic mechanism that uploads console logs to NoXoZ.

Users should review and redact any copied diagnostic information before sharing it.

## 12. Third-party AI services

NoXoZ AI VoiceControl automates browser actions around third-party AI services.

Those services may process:

- account information;
- messages;
- voice input;
- transcripts;
- files;
- AI responses;
- usage metadata;
- billing or subscription information;
- provider-side logs and safety data.

That processing is controlled by the relevant provider, not by NoXoZ AI VoiceControl.

Users must review the terms and privacy policy of the service they use.

## 13. Browser and operating-system processing

The browser and operating system may independently process:

- extension installation metadata;
- microphone permissions;
- browser synchronization data;
- browsing history;
- crash data;
- security events;
- extension developer-mode warnings;
- local files selected by the user.

Those activities are governed by the browser and operating-system providers.

## 14. Data retention and deletion

Extension configuration remains in the local browser profile until it is:

- changed by the user;
- cleared through browser extension storage;
- removed when the browser profile is deleted;
- removed when the browser clears extension data;
- removed when the extension is uninstalled, depending on browser behavior.

To remove the extension:

1. open the browser extensions page;
2. remove **AI Voice Control**;
3. optionally delete the local unpacked extension directory.

Conversation data stored by an AI provider must be managed through that provider's own account and privacy controls.

## 15. Sensitive information

Do not include sensitive information in feedback unless it is strictly necessary.

Before sharing a screenshot, console log, transcript, or copied page content, remove or redact:

- passwords;
- API keys;
- authentication tokens;
- personal identifiers;
- private conversations;
- confidential documents;
- medical information;
- legal information;
- financial information;
- client data;
- private repository content.

## 16. Children

The extension is not specifically designed or marketed as a service for children.

Use of the extension and connected AI services must follow applicable age requirements, parental rules, and provider terms.

## 17. Changes to this policy

A future public release may update this document if the extension's permissions, storage, network behavior, supported websites, or workflow change.

The version and date in the document header identify the policy associated with the public release.

## 18. Contact

Privacy questions may be sent to:

**Bruno DELNOZ — @NoXoZ_be**

Email:

`bruno.delnoz@protonmail.com`

The extension's visible feedback link may use:

`noxoz_be@proton.me`

## 19. Independent project notice

NoXoZ AI VoiceControl is an independent project.

It is not affiliated with, endorsed by, sponsored by, or officially supported by OpenAI, Anthropic, Brave, Google, Chromium, Chrome, or any other AI or browser vendor.
