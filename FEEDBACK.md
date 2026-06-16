<!--
==============================================================================
Document       : FEEDBACK.md
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
Description    : Feedback, bug-report, compatibility-report and request guidelines.
==============================================================================
-->

# Feedback

## 1. Purpose

Feedback helps improve NoXoZ AI VoiceControl while keeping the extension controlled, small, private, and aligned with its original purpose.

Useful feedback includes:

- reproducible bugs;
- browser compatibility results;
- AI website interface changes;
- selector failures;
- workflow-state errors;
- microphone and silence-detection behavior;
- documentation corrections;
- carefully scoped feature proposals;
- translation requests;
- licensing questions.

## 2. Contact methods

### Extension contact link

In Maxi mode, click:

**@NoXoZ_be**

The extension opens a normal email draft addressed to:

`noxoz_be@proton.me`

No email is sent automatically.

### Repository contact

Official repository:

`https://github.com/bdelnoz/NoXoZ_AI_VoiceControl`

When GitHub Issues are enabled, they may be used for public, non-sensitive reports.

### Repository metadata and licensing email

`bruno.delnoz@protonmail.com`

Use this address for:

- licensing questions;
- commercial permission requests;
- redistribution requests;
- contribution authorization;
- translation authorization;
- private technical contact when a public report is unsuitable.

## 3. Before reporting

Check these points first:

1. confirm the official extension source;
2. confirm public version `v1.0.0`;
3. note the internal runtime version shown in the widget;
4. reload the extension;
5. reload the AI tab;
6. reproduce with a short safe test;
7. check [HELP.md](HELP.md);
8. check [COMPATIBILITY.md](COMPATIBILITY.md);
9. remove private information from evidence.

## 4. Bug-report template

Use this structure:

### Title

`[BUG] Short description`

### Environment

- Public release:
- Internal runtime shown:
- Operating system:
- Browser:
- Browser version:
- AI website:
- Website domain:
- Interface language:
- Account/interface variant:
- Installation method:

### Extension state

- Full Flow:
- New Transcription + TOS:
- AutoSend:
- Trigger ReadAloud:
- Set ReadAloud Mode:
- Time Of Silence:
- Threshold:
- Display mode:
- Platform profile:

### Microphone environment

- Microphone or headset:
- Background noise:
- Browser microphone permission:
- Volume level while silent:
- Volume level while speaking:

### Expected behavior

Describe exactly what should have happened.

### Observed behavior

Describe exactly what happened instead.

### Reproduction steps

1.
2.
3.
4.

### Frequency

- always;
- often;
- intermittent;
- occurred once.

### Recovery

State whether any of these recovered the workflow:

- Full Flow off and on;
- Stop ReadAloud;
- page reload;
- Reload Ext;
- browser extension reload;
- browser restart.

### Evidence

Attach only sanitized evidence.

Examples:

- screenshot;
- short screen recording;
- console error;
- exact visible status;
- relevant HTML accessibility label;
- sanitized transcript fragment.

## 5. Compatibility-report template

### Title

`[COMPATIBILITY] Browser / AI website / result`

### Environment

- Operating system:
- Browser:
- Browser version:
- AI website:
- Interface language:
- Public extension version:
- Internal runtime:
- Installation method:

### Tested features

Mark each item:

- widget toggle:
- Maxi mode:
- Mini mode:
- Button mode:
- widget dragging:
- local setting persistence:
- microphone permission:
- volume meter:
- Threshold:
- Time Of Silence:
- transcript validation:
- AutoSend:
- Trigger ReadAloud:
- ReadAloud Last Message:
- Stop ReadAloud:
- new-transcription restart:
- Reload Ext:

### Result

- fully working;
- partly working;
- not working.

### Notes

Describe exact limitations.

## 6. Website-change report

AI websites frequently change interface structure.

A useful website-change report includes:

- date first observed;
- website domain;
- interface language;
- old behavior;
- new visible behavior;
- missing or renamed control;
- screenshot with private data removed;
- browser console error, when available;
- whether the website's own manual action still works.

Do not report only that "it is broken."

Identify the failed stage, for example:

- voice button not found;
- transcription finish not found;
- composer not detected;
- Send not detected;
- response completion never detected;
- Read Aloud not found;
- Stop Read Aloud not found;
- new transcription not started.

## 7. Feature-request template

### Title

`[FEATURE] Short description`

### Problem

Describe the real workflow problem.

### Current workaround

Explain what must currently be done manually.

### Proposed behavior

Describe the smallest useful behavior change.

### User control

Explain:

- whether the feature is optional;
- how it is enabled or disabled;
- what safe default should apply;
- how the user stops or reverses it.

### Scope

State whether the proposal concerns:

- ChatGPT;
- Claude;
- browser compatibility;
- UI;
- microphone;
- TOS;
- AutoSend;
- Read Aloud;
- documentation;
- packaging.

### Out of scope

State what the proposal must not change.

## 8. Documentation-correction template

Include:

- file name;
- section;
- incorrect statement;
- proposed correction;
- reason;
- source or runtime evidence.

Documentation corrections must not silently expand the claimed compatibility or license rights.

## 9. Translation requests

Translations are controlled by the project author.

Before preparing a public translation:

1. contact Bruno DELNOZ;
2. identify the target language;
3. identify the exact source version;
4. request authorization;
5. preserve technical names and legal meaning;
6. submit the translation for validation;
7. do not publish it independently as an official release.

A translation request does not grant redistribution rights.

## 10. Contribution requests

The project is source-available, not open source.

Before preparing a substantial code change:

1. read [LICENSE](LICENSE);
2. read [CONTRIBUTING.md](CONTRIBUTING.md);
3. contact the author with the proposed scope;
4. wait for authorization when required;
5. keep the change narrowly scoped;
6. do not publish a modified release independently.

## 11. Sensitive data rules

Never include these in a public issue or ordinary feedback email:

- password;
- API key;
- authentication token;
- session cookie;
- private email;
- private chat export;
- unredacted medical data;
- unredacted legal data;
- confidential work material;
- private repository code;
- personal address;
- payment information.

When a screenshot is necessary:

- crop it;
- blur identities;
- hide the browser profile;
- hide conversation history;
- hide attachments;
- hide account menus;
- hide notification content.

## 12. Good feedback characteristics

Good feedback is:

- factual;
- reproducible;
- specific;
- limited to one issue;
- versioned;
- sanitized;
- clear about expected and observed behavior.

Poor feedback is:

- vague;
- based on an unknown modified copy;
- missing browser and version;
- missing the failed stage;
- combining many unrelated requests;
- publishing private information;
- claiming compatibility without testing.

## 13. Response and acceptance

Submitting feedback does not guarantee:

- a response;
- acceptance;
- implementation;
- a release date;
- compatibility with every environment;
- permission to redistribute or publish changes.

Bruno DELNOZ remains the final authority for:

- project direction;
- accepted fixes;
- public releases;
- translations;
- compatibility claims;
- documentation;
- licensing;
- branding.

## 14. Thank you

Precise reports reduce debugging time and help protect the stable validated workflow.
