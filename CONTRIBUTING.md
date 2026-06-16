<!--
==============================================================================
Document       : CONTRIBUTING.md
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
Description    : Controlled contribution guidelines for the proprietary source-available project.
==============================================================================
-->

# Contributing

## 1. Project model

NoXoZ AI VoiceControl is a proprietary, source-available project.

It is not open-source software.

Public visibility of the source code does not grant a general right to:

- modify and redistribute it;
- publish a fork as a separate product;
- create derivative releases;
- upload it to a browser store;
- sell it;
- rebrand it;
- integrate it into another product or service.

All contributions remain subject to the [NoXoZ Personal License v1.0](LICENSE).

## 2. Project owner

Project owner and final maintainer:

**Bruno DELNOZ — @NoXoZ_be**

Email:

`bruno.delnoz@protonmail.com`

Feedback contact used by the extension:

`noxoz_be@proton.me`

## 3. Contribution philosophy

The project prioritizes:

- preservation of the validated workflow;
- narrowly scoped changes;
- user control;
- local browser-side operation;
- no telemetry;
- no unrequested feature removal;
- no unrelated refactoring;
- no silent selector changes;
- clear public documentation;
- explicit author validation.

A contribution should solve one identified problem without rewriting unrelated working behavior.

## 4. Contact before substantial work

Before preparing a substantial code change, translation, browser port, or new AI-platform adaptation:

1. describe the problem;
2. describe the exact proposed scope;
3. identify the public release and internal runtime;
4. identify the files likely to change;
5. state what must remain unchanged;
6. contact Bruno DELNOZ;
7. obtain authorization when requested.

Unrequested large rewrites, architectural replacements, generalized frameworks, or unrelated cleanups may be rejected without review.

## 5. Accepted contribution types

Possible contribution types include:

- reproducible bug reports;
- selector-change reports;
- narrowly scoped corrections;
- browser compatibility test results;
- documentation corrections;
- security reports;
- feature proposals;
- authorized patches;
- authorized translations;
- authorized browser adaptations;
- authorized AI website adaptations.

Submission does not guarantee acceptance.

## 6. Contributions that are not accepted by default

Do not submit changes that:

- remove working features;
- simplify the runtime without request;
- rename project elements;
- change the public identity;
- change `@NoXoZ_be`;
- replace the license;
- add telemetry;
- add analytics;
- add advertisements;
- add a remote backend;
- upload audio;
- add user accounts;
- broaden website permissions without a documented need;
- add unsupported browsers to compatibility claims;
- claim full Claude support without validation;
- publish development files;
- include private logs;
- include secrets;
- include internal `.old` or `.zip` content;
- modify governance files without an explicit project-owner request;
- reformat the complete codebase for style only;
- refactor unrelated stable selectors or workflow logic;
- create an independent release or mirror.

## 7. Bug reports before patches

A useful bug report should normally come before a patch.

Include:

- public release version;
- internal runtime version;
- browser;
- browser version;
- operating system;
- AI website;
- interface language;
- active controls;
- Time Of Silence;
- Threshold;
- reproduction steps;
- expected behavior;
- observed behavior;
- sanitized evidence.

See [FEEDBACK.md](FEEDBACK.md).

## 8. Patch scope

An authorized patch must:

- address the approved issue only;
- preserve unchanged behavior;
- avoid unrelated refactoring;
- avoid selector generalization not required by the issue;
- preserve the current working ChatGPT baseline;
- preserve manual Read Aloud controls;
- preserve Full Flow behavior;
- preserve AutoSend-off draft behavior;
- preserve voice and Read Aloud mutual exclusion;
- preserve local storage compatibility when possible;
- preserve branding and public identity;
- preserve copyright and license notices.

## 9. Code requirements

Code contributions must:

- use readable JavaScript, HTML, or CSS;
- remain compatible with the declared Manifest V3 target;
- avoid unnecessary dependencies;
- avoid remote code execution;
- avoid dynamically loaded remote scripts;
- avoid minified or obfuscated source;
- avoid secrets and credentials;
- use defensive error handling;
- avoid destructive browser behavior;
- keep user-visible state understandable;
- preserve local-only behavior unless a separately approved specification changes it.

## 10. Permissions

A contribution that adds or changes browser permissions must explain:

- the exact permission;
- the feature requiring it;
- why a narrower permission is insufficient;
- what data becomes accessible;
- what data is stored;
- what data is transmitted;
- how the privacy document must change.

Permission expansion will not be accepted merely for convenience.

## 11. Network behavior

The public v1.0.0 runtime contains no extension-owned network client.

A proposed network feature must not be added without explicit prior authorization.

Any authorized network change would require:

- clear user benefit;
- explicit endpoint documentation;
- data-flow documentation;
- security review;
- privacy update;
- permission review;
- failure behavior;
- opt-in design;
- new public release.

## 12. Microphone behavior

Microphone-related contributions must preserve these principles:

- analyser use must remain visible and controllable;
- audio must not be stored without explicit approval;
- audio must not be uploaded without explicit approval;
- microphone tracks must be released when no longer needed;
- denied permission must fail safely;
- Threshold and TOS behavior must remain understandable;
- Read Aloud must not be captured as the next user transcription.

## 13. UI requirements

UI changes must:

- preserve visible public/runtime version information;
- preserve the project identity;
- preserve developer contact;
- preserve Mini, Maxi, and Button concepts unless explicitly changed;
- preserve clear active and inactive states;
- remain usable at common browser zoom levels;
- avoid hiding critical Stop controls;
- avoid starting automation merely because the widget was opened.

## 14. Documentation language

Public repository documentation is written in English by default.

A contribution must update relevant documentation when behavior changes.

Potentially affected documents include:

- README.md;
- INSTALL.md;
- PRIVACY.md;
- COMPATIBILITY.md;
- WORKFLOW.md;
- HELP.md;
- FEEDBACK.md;
- ROADMAP.md;
- CONTRIBUTING.md;
- LICENSE, only when the project owner explicitly requests a license change.

Do not change legal meaning through casual documentation edits.

## 15. Versioning

The public release version and internal runtime version may differ.

Contributors must not change either version without explicit authorization.

A patch description must identify both when relevant:

- public release;
- internal runtime.

Do not invent or publish a new official release number.

## 16. Testing requirements

An authorized code patch should test the smallest complete relevant workflow.

Depending on scope, testing may include:

- extension load;
- toolbar icon;
- widget show and hide;
- Maxi mode;
- Mini mode;
- Button mode;
- drag position;
- stored settings;
- microphone permission;
- volume meter;
- Threshold;
- Time Of Silence;
- transcript finish;
- AutoSend on;
- AutoSend off;
- assistant response completion;
- Trigger ReadAloud;
- ReadAloud Last Message;
- Stop ReadAloud;
- next-transcription restart;
- Full Flow off;
- extension reload;
- tab reload.

Do not claim a test was executed when it was not.

## 17. Browser and AI claims

A successful test in one browser does not prove support for all Chromium browsers.

A successful partial action on Claude does not prove full Claude workflow support.

Compatibility claims must be:

- specific;
- versioned;
- reproducible;
- approved for public documentation.

## 18. Translation contributions

A translation requires prior authorization.

An authorized translation must:

- identify the exact source version;
- preserve section structure;
- preserve technical meaning;
- preserve warnings;
- preserve license restrictions;
- preserve project and developer names;
- avoid adding unsupported features;
- avoid removing legal or privacy content;
- be submitted for final validation.

A translated file must not be published independently as an official NoXoZ release without written authorization.

## 19. Security reports

Do not publish an exploitable security issue publicly before contacting the author.

A private report should include:

- affected version;
- affected file or function;
- threat scenario;
- reproduction;
- impact;
- proposed mitigation, when known;
- whether sensitive data is involved.

Do not include real passwords, tokens, private conversations, or unauthorized third-party data.

## 20. Submission rights

By submitting material for project review, the contributor confirms that:

- they created the submitted material or have the right to submit it;
- the submission does not knowingly include third-party confidential material;
- the submission does not knowingly violate another license;
- the submission may be reviewed, modified, accepted, rejected, or not used by Bruno DELNOZ.

The project owner may require a separate written contributor agreement before incorporating or distributing a contribution.

Submission alone does not transfer ownership and does not create a right to publication.

## 21. No independent distribution

Preparing a contribution does not authorize the contributor to:

- distribute a modified extension;
- publish a modified ZIP;
- run an unofficial browser-store listing;
- create an unofficial public mirror;
- use NoXoZ branding for another release;
- offer a modified hosted or commercial service.

Use the official repository link when recommending the project.

## 22. Review authority

Bruno DELNOZ may:

- accept a contribution;
- reject it;
- request changes;
- rewrite it;
- implement the idea independently;
- postpone it;
- close it as out of scope;
- require additional validation;
- require separate legal terms.

## 23. Contribution checklist

Before submission, confirm:

- scope was authorized when required;
- public and runtime versions are identified;
- no secret is present;
- no private data is present;
- no unrelated file changed;
- no working feature was removed;
- no unsupported compatibility claim was added;
- permissions were not broadened without explanation;
- privacy documentation is synchronized;
- documentation is complete;
- tests are listed honestly;
- project identity is unchanged;
- license notices remain intact.

## 24. Contact

Contribution requests:

**Bruno DELNOZ — @NoXoZ_be**

`bruno.delnoz@protonmail.com`
