# Project Vision & Scope: Paperonii

Paperonii is an independent custom firmware project for the **Xteink X4 Pro**, initially derived from [CrossPoint Reader](https://github.com/crosspoint-reader/crosspoint-reader). It keeps CrossPoint's capable reading foundation while exploring a broader idea: a small, playful, general-purpose e-ink device for reading, tools, games, documents, and connected experiences.

Paperonii is not an official CrossPoint Reader release and does not follow CrossPoint's product scope or release policy.

## 1. Core Mission

Make the Xteink X4 Pro more useful and enjoyable without sacrificing its reliability as an e-reader.

Reading remains a first-class experience, but it is not the sole criterion for accepting features. Paperonii may add applications and workflows that make good use of the X4 Pro's touch screen, ESP32-S3, storage, USB, Wi-Fi, and e-ink display.

## 2. Product Principles

### X4 Pro First

Paperonii targets the Xteink X4 Pro. Portability to other devices is welcome only when it does not delay, complicate, or weaken the X4 Pro experience. Generalizing hardware support is not a project goal by itself.

### Stable Reader, Broader Device

Existing reading features should remain usable and regressions should be treated seriously. New work does not, however, need to be part of the reading flow. Games, utilities, note-taking, document viewers, and network applications are legitimate project areas.

### E-Ink-Aware by Design

Features should be designed around slow refresh, ghosting, battery use, limited memory, and intermittent connectivity. A feature is not rejected merely because it is interactive; it should instead choose an appropriate refresh strategy and interaction model.

### Modular Growth

Non-reader features should be separated from the reader core where practical. Shared services such as navigation, input, persistence, networking, and display refresh should have clear boundaries so experimental applications do not destabilize core reading.

### Honest Capability

Paperonii should distinguish between proven support, experimental support, and ideas. Features are documented as supported only after they have been tested on real X4 Pro hardware.

## 3. In Scope

### Reading

- EPUB, TXT, XTC/XTCH, image, typography, font, localization, library, bookmark, dictionary, progress, and rendering improvements.
- Reader usability and touch interactions.
- Performance, memory, storage, and battery improvements that benefit reading.

### Applications and Games

- Small e-ink-friendly games.
- Calculators, clocks, timers, calendars, reference tools, and similar utilities.
- A reusable application launcher and lifecycle where it provides clear value.
- Experiments that explore the X4 Pro as more than a dedicated reader.

### Notes and Input

- Typed or touch-driven notes, simple editors, checklists, and sketching.
- On-screen keyboard and reusable text-input components.
- Local persistence, export, and recovery appropriate to the hardware.

### Documents

- PDF support, including feasibility experiments and constrained viewers.
- Image-based and fixed-layout document viewing.
- Deliberate tradeoffs such as preprocessing, cropping, tiling, zooming, or reduced feature coverage are acceptable when documented.

### Connectivity

- User-initiated network applications such as RSS, weather, downloads, sync, remote libraries, and selected web APIs.
- Improvements to existing web, OPDS, WebDAV, OTA, and transfer features.
- Background or periodic networking when battery and failure behavior are explicit and controllable.

### Platform and Customization

- X4 Pro hardware integration, USB workflows, touch UX, power management, storage, and recovery.
- Themes, launchers, sleep screens, sounds where supported, and other playful customization.
- Refactoring, tests, diagnostics, build tooling, and documentation that improve development or release safety.

## 4. Constraints and Non-Goals

Paperonii has a broad feature scope, but not an unlimited engineering budget. The following are constraints rather than permanent category bans:

- **X4 Pro support comes first.** Other boards must not dictate architecture or block releases.
- **Core reliability matters.** Features that corrupt books, settings, files, or device recovery paths will not ship as stable.
- **Resource costs must be visible.** Large features should document flash, RAM, storage, refresh, and battery tradeoffs.
- **Networking must be user-controlled.** Applications should avoid hidden continuous activity and handle offline use cleanly.
- **PDF support may remain constrained.** Full desktop-class rendering is not promised; useful subsets and preprocessing workflows are acceptable.
- **No compatibility promise before validation.** Imported CrossPoint behavior is a baseline, not proof that a Paperonii release has been verified on the X4 Pro.
- **No feature is accepted merely because it is possible.** It still needs a maintainable implementation and a coherent X4 Pro interaction model.

## 5. Current Priority

The first milestone is **Paperonii Foundation**:

1. Establish a reproducible X4 Pro build.
2. Verify boot, display, touch, storage, USB, Wi-Fi, sleep/wake, and recovery on real hardware.
3. Separate Paperonii identity, configuration, release artifacts, and documentation from upstream CrossPoint.
4. Add minimal smoke tests and a repeatable release checklist.
5. Ship one small representative application to validate the direction beyond reading.

The representative application is a simple **touch sketch pad**. It is intentionally small, but it exercises app entry/exit, touch input, e-ink refresh behavior, local persistence, and separation from the reader core. It is a foundation test, not a promise that note-taking will be the project's dominant feature.

See [ROADMAP.md](ROADMAP.md) for milestone details and exit criteria.

## 6. Proposal and Acceptance Guidelines

A proposal should answer:

- What X4 Pro use case does this enable?
- Is it stable, experimental, or a feasibility study?
- What are its flash, RAM, storage, refresh, and battery costs?
- How is it isolated from the reader core?
- How will it be tested on real hardware?
- What happens when storage, network access, or power is unavailable?

Large features should begin with an issue or design note. Experimental features may land behind a build option or explicit experimental label while their constraints are still being understood.

## 7. Upstream, Copyright, and License

Paperonii began from CrossPoint Reader commit [`3f874f8472280398c3d1900ab66450583c101e7a`](https://github.com/crosspoint-reader/crosspoint-reader/commit/3f874f8472280398c3d1900ab66450583c101e7a), with the submodule versions recorded by that commit.

The original MIT license and copyright notice in [LICENSE](LICENSE) are retained. Copyright notices and license terms belonging to included submodules and third-party components must also remain intact. Paperonii's independent Git history and broader scope do not imply that the imported source was newly authored by Paperonii contributors.

Where useful, changes from CrossPoint may be reviewed and selectively adapted with attribution. Paperonii is independently maintained and is not endorsed by or affiliated with CrossPoint Reader or Xteink.
