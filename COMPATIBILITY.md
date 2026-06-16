<!--
==============================================================================
Document       : COMPATIBILITY.md
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
Description    : Compatibility status for browsers, AI websites, interfaces and operating environments.
==============================================================================
-->

# Compatibility

## 1. Release identification

This document describes compatibility for the first public release:

**NoXoZ AI VoiceControl v1.0.0**

The public v1.0.0 package is based on the internally validated runtime identified as **v8.0.0**.

The public release number and internal development runtime number serve different purposes:

- public project release: `v1.0.0`;
- validated internal runtime baseline: `v8.0.0`.

Public documentation, GitHub release information, and public support references should use **v1.0.0**.

## 2. Primary validated environment

The primary development and validation environment is:

- operating system: Kali Linux rolling;
- desktop browser: Brave Browser;
- primary AI website: ChatGPT Web;
- extension format: Chromium Manifest V3;
- installation method: unpacked extension in Developer mode.

This is the strongest compatibility target for public v1.0.0.

## 3. Browser compatibility

### Brave Browser

**Status: primary supported target**

The extension was developed and validated primarily with Brave.

Expected features include:

- toolbar popup bridge;
- on-page widget injection;
- local setting storage;
- microphone level analysis;
- Time Of Silence;
- AutoSend;
- Read Aloud controls;
- Mini, Maxi, and Button modes;
- widget position persistence.

### Google Chrome

**Status: supported Chromium target**

The extension uses standard Manifest V3 APIs available in Chrome:

- `chrome.storage.local`;
- `chrome.tabs`;
- `chrome.activeTab`;
- `chrome.scripting`;
- content scripts;
- unpacked-extension installation.

Full compatibility may still depend on the current ChatGPT interface and the installed Chrome version.

### Chromium

**Status: supported Chromium target**

The same Manifest V3 architecture is intended to work in Chromium builds that provide the required extension APIs.

Distribution-specific Chromium builds may differ in:

- microphone permission behavior;
- extension Developer mode;
- codec or audio support;
- enterprise policies;
- disabled Google components.

### Microsoft Edge

**Status: not officially validated for v1.0.0**

Edge is Chromium-based and may support the required APIs, but this public release does not claim validated Edge compatibility.

### Vivaldi

**Status: not officially validated for v1.0.0**

Vivaldi is Chromium-based, but toolbar, page layout, permission, and extension behavior may differ.

### Opera

**Status: not officially validated for v1.0.0**

Opera is not part of the validated release target.

### Firefox

**Status: not supported**

The public v1.0.0 release is not packaged or adapted for Firefox.

A future Firefox adaptation would require separate validation and may require code, manifest, permission, and browser-action changes.

### Mobile browsers

**Status: not supported**

The release is intended for desktop Chromium-based browsers that allow unpacked extensions.

Mobile Chrome, mobile Brave, iOS browsers, and standard Android browsers generally do not provide the required unpacked desktop-extension workflow.

## 4. AI website compatibility

### ChatGPT Web

**Status: primary validated AI target**

Supported origins declared by the runtime:

- `https://chatgpt.com/*`
- `https://chat.openai.com/*`

The extension relies on the visible ChatGPT web interface for:

- voice transcription;
- message composition;
- Send;
- assistant response completion;
- Read Aloud;
- Stop Read Aloud;
- new transcription.

Website-interface changes can affect selectors and workflow detection.

### Claude Web

**Status: profile present, full public compatibility not claimed**

Supported origins declared by the runtime:

- `https://claude.ai/*`
- `https://www.claude.ai/*`

The runtime includes a ChatGPT/Claude profile selector and hostname-based default selection.

The Claude profile is currently retained as a clone profile for later adaptation.

Public v1.0.0 does not claim that the complete ChatGPT workflow is validated on Claude.

### Other AI websites

**Status: not supported**

The current manifest does not declare access to Gemini, Grok, Copilot, Le Chat, Perplexity, or other AI web services.

The extension will not automatically operate on undeclared websites.

## 5. Interface-language compatibility

The runtime contains recognition patterns for several English and French interface labels, including common Send, finish-transcription, Stop, and Read Aloud wording.

This improves tolerance for English and French interfaces.

It does not guarantee complete compatibility with:

- every translation;
- every regional variation;
- experimental interface labels;
- A/B-tested interface changes;
- accessibility-label changes;
- custom browser translation;
- future AI website redesigns.

The most reliable configuration is the interface language used during validation.

## 6. Required browser capabilities

The browser must support:

- Manifest V3 extensions;
- unpacked extension loading;
- `chrome.storage.local`;
- `chrome.tabs`;
- `chrome.scripting`;
- content-script execution;
- microphone permission through `navigator.mediaDevices.getUserMedia`;
- Web Audio API through `AudioContext` or `webkitAudioContext`;
- modern JavaScript;
- DOM mutation and event observation.

## 7. Required website capabilities

For the full workflow, the selected AI website must provide:

- a normal text composer;
- a visible Send action;
- voice transcription;
- a finish or validation action for transcription;
- a detectable assistant-response state;
- a Read Aloud action;
- a Stop Read Aloud action;
- a new-transcription action.

A missing website feature cannot be created by the extension.

## 8. Permissions compatibility

The runtime requests:

- `storage`;
- `tabs`;
- `activeTab`;
- `scripting`.

Enterprise browser policies, hardened browser profiles, extension restrictions, microphone restrictions, or disabled site permissions may prevent one or more features from working.

## 9. Microphone compatibility

Time Of Silence and Threshold monitoring require:

- a working microphone;
- browser permission for microphone access;
- an available audio input device;
- Web Audio API support.

The extension was designed to work with ordinary headsets and gaming-headset microphones.

A professional audio interface is not required.

Results depend on:

- microphone level;
- headset gain;
- room noise;
- television or music;
- browser automatic gain control;
- operating-system input settings;
- selected Threshold;
- selected Time Of Silence.

## 10. Display compatibility

The widget supports:

- Maxi mode;
- Mini mode;
- compact Button mode;
- drag-and-drop positioning;
- persisted screen position.

Very small windows, high browser zoom, unusual page scaling, mobile layouts, or major website CSS changes may affect placement.

The runtime includes viewport-correction logic, but no layout can be guaranteed against every future website redesign.

## 11. Known compatibility limits

The extension depends on the live structure of third-party websites.

Compatibility may break when a provider changes:

- button labels;
- accessibility labels;
- DOM structure;
- composer implementation;
- voice-transcription controls;
- response state indicators;
- Read Aloud menus;
- icon structure;
- streaming behavior;
- account-specific experiments.

A failure after a website update does not necessarily mean the local extension files are damaged.

## 12. Unsupported configurations

Public v1.0.0 does not claim support for:

- Firefox;
- Safari;
- mobile browsers;
- browser-store installation;
- native ChatGPT desktop applications;
- native Claude desktop applications;
- operating-system-wide voice control;
- browser automation outside declared AI origins;
- unofficial AI front ends;
- embedded AI widgets in other websites;
- multiple active AI tabs controlled simultaneously as one synchronized workflow.

## 13. Compatibility reporting

When reporting compatibility, provide:

- public extension version: `v1.0.0`;
- internal runtime shown in the widget;
- operating system;
- browser name;
- browser version;
- AI website;
- website URL domain;
- interface language;
- account interface variant, when known;
- microphone type;
- Time Of Silence;
- Threshold;
- active extension controls;
- expected behavior;
- observed behavior.

See [FEEDBACK.md](FEEDBACK.md) for the complete reporting format.

## 14. Compatibility policy

Compatibility statements apply only to the documented public release.

Future browser and AI website updates may require a new extension release.

NoXoZ AI VoiceControl does not control third-party interface changes and cannot guarantee permanent compatibility.
