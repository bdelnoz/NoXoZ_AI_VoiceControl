<!--
==============================================================================
Document       : ROADMAP.md
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
Description    : Public project direction and non-binding future development roadmap.
==============================================================================
-->

# Roadmap

## 1. Roadmap status

This roadmap describes possible future directions for NoXoZ AI VoiceControl.

It is not a contractual commitment.

It does not guarantee:

- implementation;
- release dates;
- browser-store publication;
- compatibility with a specific future website version;
- acceptance of every feature request;
- development of every listed target.

The author controls priorities and may change, postpone, reject, or remove planned items.

## 2. Current public baseline

### Public v1.0.0

The first public release establishes:

- public GitHub repository;
- manual Chromium-based installation;
- Brave as the primary browser target;
- ChatGPT Web as the primary validated AI target;
- Manifest V3 runtime;
- Full Flow control;
- New Transcription + TOS;
- configurable silence duration;
- configurable microphone Threshold;
- volume meter;
- optional AutoSend;
- optional Trigger ReadAloud;
- manual Read Aloud mode command;
- manual ReadAloud Last Message;
- manual Stop ReadAloud;
- Mini, Maxi, and Button modes;
- local setting persistence;
- developer contact;
- proprietary source-available personal-use license.

## 3. Immediate maintenance priorities

### 3.1 Preserve the validated ChatGPT baseline

Priority:

- avoid regressions;
- preserve existing controls;
- preserve selectors unless a website change requires correction;
- keep voice recording and Read Aloud mutually exclusive;
- preserve manual Read Aloud independence from Full Flow;
- preserve AutoSend-off draft behavior;
- preserve local-only workflow control.

### 3.2 Website selector maintenance

ChatGPT may change:

- voice controls;
- composer;
- Send button;
- response state;
- Read Aloud menu;
- Stop Read Aloud control.

Maintenance releases may update only the selectors or state detection required to restore existing behavior.

### 3.3 Public documentation

Maintain synchronization between:

- README;
- WHY;
- INSTALL;
- PRIVACY;
- COMPATIBILITY;
- WORKFLOW;
- HELP;
- FEEDBACK;
- ROADMAP;
- CONTRIBUTING;
- LICENSE.

### 3.4 Release packaging

Improve public-release packaging while preserving:

- clear folder naming;
- clear public version;
- clean runtime archive;
- no internal `.old` content;
- no development ZIP directory;
- no private changelog;
- no governance files in public packages unless deliberately included by the author.

## 4. Planned compatibility work

## 4.1 Claude Web adaptation

The runtime already includes:

- Claude host permissions;
- Claude content-script matching;
- a ChatGPT/Claude profile selector;
- hostname-based profile selection.

A future Claude release requires real adaptation and validation of:

- voice-transcription controls;
- transcript completion;
- composer detection;
- Send;
- response completion;
- Read Aloud availability;
- Stop Read Aloud;
- new-transcription restart;
- Claude-specific interface states.

The current clone profile must not be presented as full support until validated.

## 4.2 Firefox evaluation

A future Firefox version may be evaluated separately.

Possible work includes:

- manifest review;
- browser API compatibility;
- action/popup behavior;
- storage behavior;
- scripting permission behavior;
- microphone behavior;
- packaging;
- installation documentation;
- independent testing.

Firefox support will not be claimed before a validated Firefox package exists.

## 4.3 Additional Chromium browsers

Possible evaluation targets:

- Microsoft Edge;
- Vivaldi;
- Opera.

Support claims will require actual testing.

Chromium base alone is not sufficient evidence for full compatibility.

## 5. Language and documentation roadmap

## 5.1 French project edition

A future French edition may include:

- French README;
- French WHY;
- French INSTALL;
- French HELP;
- French PRIVACY;
- French COMPATIBILITY;
- French WORKFLOW;
- French FEEDBACK;
- French ROADMAP;
- French CONTRIBUTING;
- legally reviewed French license companion text when appropriate;
- French interface adaptation if separately validated.

The English public repository remains the reference unless the author establishes a separate official French repository or release.

## 5.2 Community translations

Community translations may be accepted only through the controlled contribution process.

A translation must:

- target an exact public version;
- preserve technical meaning;
- preserve license meaning;
- preserve project name and author identity;
- avoid unsupported compatibility claims;
- be validated by Bruno DELNOZ before official publication.

## 6. Workflow improvements under consideration

Possible future improvements include:

- clearer status diagnostics;
- stronger detection of website-interface changes;
- improved recovery after tab or extension reload;
- more explicit first-run guidance;
- user-selectable Read Aloud mode command text;
- safer export and import of non-sensitive extension settings;
- clearer per-module state visualization;
- controlled debug mode without telemetry;
- better compatibility reporting from local diagnostics;
- improved handling of long AI responses;
- additional safeguards against duplicate sends;
- additional safeguards against accidental cross-tab operation.

These items are ideas, not commitments.

## 7. Privacy direction

The intended privacy direction is to preserve:

- no NoXoZ account;
- no analytics;
- no advertising;
- no telemetry;
- no NoXoZ cloud backend;
- no remote configuration;
- no NoXoZ audio upload;
- local storage for settings only;
- user-controlled feedback.

Any future feature that changes network or data behavior must require:

- explicit documentation;
- privacy-document update;
- permission review;
- user-visible explanation;
- a new public release.

## 8. License and distribution direction

The project is intended to remain:

- proprietary;
- source-available;
- free for authorized personal non-commercial use;
- controlled by Bruno DELNOZ;
- unavailable for unauthorized redistribution;
- unavailable for unauthorized browser-store publication;
- unavailable for unauthorized commercial integration;
- protected against rebranding and unofficial mirrors.

Commercial, redistribution, integration, translation, or derivative-work permission requires a separate written authorization.

## 9. Areas deliberately out of scope

The current project does not aim to become:

- a general operating-system voice controller;
- a replacement AI model;
- a NoXoZ hosted AI service;
- an advertising platform;
- an analytics product;
- a user-account platform;
- a mobile application;
- a browser automation framework for arbitrary websites;
- a system for bypassing AI provider restrictions;
- an official accessibility certification product;
- a replacement for the AI website's own authentication or subscription.

## 10. Release policy

Future public releases should:

- preserve a clear public semantic version;
- identify the validated internal runtime baseline when necessary;
- document permissions;
- document compatibility;
- document privacy behavior;
- document user-visible changes;
- avoid publishing private development history as the public changelog unless the author explicitly decides otherwise;
- provide complete official files from the official repository.

## 11. Priority rule

Stability of the validated working workflow has priority over adding many new targets.

A new platform, browser, translation, or feature should not damage the current ChatGPT/Brave baseline.

## 12. Author authority

The final decision about roadmap scope, priorities, acceptance, release timing, compatibility claims, licensing, and official publication belongs to:

**Bruno DELNOZ — @NoXoZ_be**
