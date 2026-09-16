# Paperonii Roadmap

Paperonii is an Xteink X4 Pro-first custom firmware built from the CrossPoint Reader baseline. Its roadmap is intentionally broader than a dedicated reader: reading remains first-class, while games, notes, PDF experiments, utilities, and network applications are valid directions.

Milestones are ordered by dependency, not by a promise to implement every idea. Work may be explored early, but a milestone is complete only when its exit criteria are met on real X4 Pro hardware.

Status: ✅ done · 🚧 in progress · 🧪 experimental · ⏳ planned · ❌ dropped

---

## 🚧 Milestone 0 - Paperonii Foundation

**Goal:** Turn the imported baseline into a reproducible, identifiable, and recoverable Paperonii firmware for the Xteink X4 Pro, then prove the broader application direction with one small feature.

### Baseline and identity

- Confirm the imported CrossPoint baseline and recorded submodule revisions.
- Rename user-visible firmware identity, build metadata, storage namespaces where safe, and release artifacts to Paperonii.
- Keep upstream attribution, the original MIT license and copyright notice, and third-party notices intact.
- Document how selected upstream changes can be reviewed and adapted despite the independent Git history.

### X4 Pro hardware verification

- Produce a clean, reproducible X4 Pro build from documented prerequisites.
- Verify boot, display initialization, touch input, buttons, SD storage, battery reporting, and sleep/wake.
- Verify USB mass-storage and firmware flashing/recovery paths.
- Verify Wi-Fi, existing transfer features, and OTA behavior or explicitly disable any path that is not yet safe for Paperonii.
- Record test device details and known limitations.

### Release safety

- Add a concise hardware smoke-test checklist.
- Define versioning and produce a clearly labeled development build.
- Ensure a failed experiment cannot silently overwrite or masquerade as an official CrossPoint release.
- Document backup, flash, and recovery steps before publishing the first binary.
- Do not call the milestone stable until installation and recovery have both been exercised on real hardware.

### Representative feature: Touch Sketch

Add a minimal built-in touch sketch pad that can:

- open and return cleanly without disturbing reader state;
- draw with touch using an e-ink-aware refresh strategy;
- clear the canvas;
- save and reopen one local sketch;
- handle missing or unwritable storage without crashing.

This feature is deliberately small. It validates application navigation, touch input, partial refresh behavior, persistence, and separation from the reader core. Advanced drawing tools and a full notes system are deferred.

### Exit criteria

Milestone 0 is complete when:

- a clean checkout builds reproducibly for X4 Pro;
- the hardware checklist passes on at least one real device;
- flash and recovery instructions have been tested;
- Paperonii identity is visible without removing upstream attribution;
- Touch Sketch passes its basic interaction and persistence checks;
- a development release and known-issues note are published.

---

## ⏳ Milestone 1 - Application Foundation and Polished Reading

**Goal:** Make non-reader features safe to add while preserving a dependable reading experience.

**Focus areas:**

- Define a lightweight launcher or application registry.
- Establish application lifecycle rules for entry, exit, memory cleanup, persistence, and error handling.
- Centralize reusable touch, keyboard, dialog, and refresh primitives.
- Add regression checks for opening, reading, suspending, and resuming books.
- Fix X4 Pro-specific reading, touch, USB, and power-management issues found during Milestone 0.
- Decide whether experimental applications are build-time options, runtime flags, or a separate release channel.

**Not required for completion:** a large catalog of applications.

---

## ⏳ Milestone 2 - Notes, Tools, and Small Games

**Goal:** Deliver a useful first collection of local, e-ink-friendly applications.

Candidate work:

- On-screen keyboard and reusable text input.
- Simple notes or checklist application with safe local persistence and export.
- Expansion of Touch Sketch based on hardware results.
- Calculator, timer, calendar, or reference utilities.
- One or more turn-based or low-refresh games.
- Per-application settings and storage boundaries.

Candidates are selected by maintainability and hardware fit; this list is not a commitment to ship all items.

---

## ⏳ Milestone 3 - Documents and PDF Experiments

**Goal:** Determine which fixed-layout document workflows are genuinely useful on the X4 Pro.

Planned investigation:

- Measure feasible PDF parsing/rendering approaches on device.
- Compare native rendering, host-side preprocessing, and page-to-image pipelines.
- Prototype page fit, crop, rotation, zoom, pan, and thumbnail navigation.
- Define supported PDF subsets and failure behavior.
- Promote PDF support from experimental only if memory use, navigation, and recovery are acceptable.

A constrained viewer is a valid result. Paperonii does not promise desktop-class PDF compatibility.

---

## ⏳ Milestone 4 - Connected Applications

**Goal:** Add user-controlled network experiences without turning background activity into a battery or reliability problem.

Candidate work:

- RSS or feed reader.
- Weather and small information panels.
- Remote libraries, downloads, and sync services.
- Improvements to OPDS, WebDAV, web transfer, and OTA.
- Scheduling and caching rules for intermittent connectivity.
- Clear offline states, timeouts, credential handling, and opt-in background behavior.

Network features must disclose when they connect and remain usable or fail cleanly offline.

---

## Ongoing Work

These concerns apply across every milestone:

- EPUB and local reading quality.
- X4 Pro touch, display refresh, USB, battery, and sleep reliability.
- Memory, flash, storage, and power measurement.
- Recovery paths and avoidance of data loss.
- Tests, diagnostics, documentation, localization, and accessibility.
- Review and selective adaptation of useful upstream changes with attribution.

---

## How This Roadmap Changes

- Milestones describe direction and exit criteria, not fixed deadlines.
- Large additions should start with an issue or design note describing hardware costs and validation.
- Experimental work must be labeled as such until tested on real X4 Pro hardware.
- Scope changes should update both this file and [SCOPE.md](SCOPE.md).
- The project's broader direction does not permit removal of upstream license, copyright, or third-party notices.
