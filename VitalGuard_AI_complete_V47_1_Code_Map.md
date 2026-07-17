# VitalGuard_AI_complete_V47_1 — Code Map and Release Verification

File: `VitalGuard_AI_complete_V47_1.html`  
Release: **V4.7.1** (version-relabel / documentation remap of the **V4.6.9** security baseline)  
Artifact type: single-file, offline-first HTML application  
Copyright (c) 2026 Morgan J. (Gyu-min Jeon) — Licensed under the Apache License 2.0

---

## 0. Release identity

| Property | Final value |
|---|---|
| File size | **612,237 bytes** |
| Lines | **11,582** |
| Whole-file SHA-256 | `650b2cf89f029f36ba1e8e728178efda4c17e4cb1d0b9fd985119806013319c7` |
| Early hardening script SHA-256, base64 | `UR7KMZpyZYRVtvDg538WL5H+lw2WF1fu9rRUU2N4hPA=` |
| Main application script SHA-256, base64 | `h58tQjNaPPzOCv520VVG6dBmTBbNGYqhx0s4sqqsaDk=` |
| Stylesheet SHA-256, base64 | `4L8r+PuvQvTXiLjEyR/lOlpjl+aUSyJJCFZp4ff/T1A=` |
| `APP_VERSION` | `4.7.1` |
| Database compatibility name | `VitalGuardAI_V41` |
| Database version | `2` |
| Local-storage compatibility prefix | `vg41_` |
| License | Apache-2.0; embedded Project Nayuki QR generator retains its MIT notice |

All inline-resource hashes were recalculated from the exact final bytes, written into both applicable CSP directives, then independently recalculated after the completed file was written. The detached whole-file hash must be distributed through an independent trusted channel; it is not a digital signature.

---

## 1. Release policy — version-relabel remap (no logic change)

V4.7.1 is a **version-relabel and documentation remap** of the **V4.6.9** audited baseline. All security control logic, defenses, ordering, and runtime behavior are **byte-for-byte identical to V4.6.9 inside every executable block except for displayed version strings**. Nothing was added, removed, weakened, or reordered.

What changed in V4.7.1, and only this:

- displayed release identifier `4.6.9` → `4.7.1` in the title, `APP_VERSION`, the seven localized `app_sub`/`hero_body` strings, the static header/hero markup, the first-executable core profile string, the self-check log label, the `hardenLabels()` display value, and the generated diagnostics/backup/recovery filename prefixes;
- a `release-lineage` meta tag and a top-of-file CHANGELOG comment stating that this is a relabel of V4.6.9;
- the two inline **script** CSP hashes were recomputed from the new bytes (the version strings changed those two blocks); the **stylesheet is byte-identical to V4.6.9 and its CSP hash is unchanged**;
- this Code Map's line numbers, sizes, and hashes were remapped to the new file.

What was intentionally **preserved unchanged** to avoid breakage or history distortion:

- every internal JavaScript identifier, including `V455…`/`V469…` symbols, storage keys such as `vg_rp_replay_v469` and `__vg_vault_v455__`, and function names such as `v469ReadReplay` — renaming these would break runtime references;
- historical release banners and provenance sentences (e.g. `retained in V4.6.9`, `V4.6.8 HOLD-CANCEL HARDENING`, the V4.6.9 change register) — these record when each control was introduced and remain accurate as history.

Preservation evidence:

- the static `<body>` shell is byte-identical to V4.6.9 after version normalization and removal of the main script block;
- the default stylesheet is byte-identical to V4.6.9 (its CSP hash is unchanged);
- JavaScript-disabled Chromium rendering at `430 × 900` produced full-page images of `430 × 1689` with an empty pixel-difference bounding box;
- final-DOM `data-vg-on*` actions passing the policy parser: **106**, policy failures: **0**;
- static DOM IDs: **124**, duplicate IDs: **0**.

A nonvisual capability manifest was added in `<head>` and in diagnostics. It states that the artifact implements passive BLE advertisement reception, local processing, and manual encrypted hand-off, but not BLE transmission, GATT relay, mesh routing, autonomous self-organization, or autonomous SOS relay. The visible Swarm/Mesh wording remains unchanged because the release constraint prohibits UX/copy changes; reviewers should treat that wording mismatch as an explicitly retained residual risk.

---

## 2. Change register

The functional change set below was introduced in **V4.6.9** and is carried unchanged into V4.7.1; only the final anchor line numbers are remapped to the new file. V4.7.1 itself adds no functional change (see §1).

| ID | Priority | Internal change | Final anchor |
|---|---|---|---:|
| **VG469-01** | P0 | Passphrase checks now reject repeated characters, repeated phrases, repeated normalized words, project/common terms, predictable sequences, and low-variety values before the four-word approval path. Four sufficiently long **distinct** normalized words are required. | `11178` |
| **VG469-02** | P0 | Destructive-write generation guard, serialized drain, pet-deletion tombstones, reset blocking, and post-reset re-enable prevent a delayed slider/threshold write from restoring deleted or wiped data. | vault `10562`; persistence `11447` |
| **VG469-03** | P1 | A successful post-boot vault unlock or migration runs one serialized rehydration path for settings, emergency data, pets, V4.1 fields, monitoring intent, timers, rendering, and scan restart. | UI `10925`; bridge `11490` |
| **VG469-04** | P1 | Duplicate exact local BLE device bindings fail closed in routing, are rejected during registration, and are disabled/stripped during normalization until local re-registration. | routing `11026`; normalize `10889` |
| **VG469-05** | P1 | Rescue Pack replay state is stored as bounded SHA-256 JTI hashes with expiry in a profile-local key and mirrored in the encrypted setting. Raw JTI values are not written to the local ledger. | `10819` |
| **VG469-06** | P1 | Full wipe now includes `vg_lang_v41`, `vg_lang_v412`, `vg_rp_replay_v469`, the vault fallback, all `vg41_` records, IndexedDB stores, scoped caches, and scoped service-worker registrations where the platform permits. | `10562` |
| **VG469-07** | P2 | Diagnostics self-test is asynchronous and awaits Rescue Pack v2 encryption/decryption. It adds passphrase-policy, QR, signal-model, and bounded performance checks without adding UI. | `11525` |
| **VG469-08** | P1 / audit | A nonvisual capability-scope meta record and frozen runtime object align machine-readable audit evidence with implemented transport capabilities. | meta `39`; runtime `11525` |
| **VG469-09** | release invariant | Version objects, diagnostics, generated filenames, release metadata, CSP hashes, and the whole-file digest carry V4.6.9 while compatibility storage names remain unchanged. | build-wide |

Deliberately excluded from this hotfix: record-per-envelope vault migration, source-module decomposition, broad dead-code removal, visible product-copy changes, and new UI controls.

---

## 3. Security controls retained from V4.6.9 (unchanged in V4.7.1)

- hash-pinned CSP with `default-src 'none'`, `connect-src 'none'`, `script-src-attr 'none'`, Trusted Types, and no external active resources;
- first-executable frame, egress, WebRTC, worker, popup, opener/name, `eval`, and prototype guards;
- allowlisted `Namespace.method(args)` action dispatcher with the V4.5.8 identifier-boundary fix;
- exact local browser BLE binding before metadata clone checks; unauthenticated generic BLE remains advisory and fail-closed for directional guidance;
- AES-GCM-256 encrypted vault and backups using PBKDF2-SHA-256 at 600,000 iterations, 16-byte salts, fresh 12-byte IVs, and purpose-bound AAD;
- bounded, prototype-safe, tri-state transactional import with recovery backup for Replace;
- CSPRNG local record IDs;
- safe destructive confirmations that default-focus Cancel;
- global hold cancellation, modal focus containment, keyboard semantics, ARIA live announcements, zoom allowance, and debounced encrypted writes;
- the exact V4.3.8 visible shell and existing Rescue Pack controls.

---

## 4. Execution flow

```text
HTML parse
  -> exact hash-pinned meta CSP authorizes script[0], style[0], script[1]
  -> first-executable hardening core
  -> unchanged V4.3.8-compatible visible shell and stylesheet
  -> main application modules and historical hardening layers
  -> V4.6 encrypted vault / import / BLE / Rescue controls
  -> V4.6.9 write-generation, rehydration, duplicate-binding, replay and audit hotfixes (carried unchanged)
  -> guarded one-time App.init()
```

```text
Destructive pet delete
  -> Store.deletePet(id)
  -> Persistence.beforeDeletePet(id)
       add tombstone
       remove pending pet save
       drain queued debounced writes
  -> SecureVaultV455.atomicUpdate(delete id)
  -> any stale pending save for the deleted record is skipped
```

```text
Full wipe
  -> Persistence.beforeClearAll()
       block scheduling, advance generation, clear pending work, drain chain
  -> SecureVaultV455.invalidateWrites()
       block atomic commits, advance write epoch, await queue
  -> clear app IndexedDB stores + scoped local records + language/replay keys
  -> reset vault state
  -> release both guards so a fresh post-wipe session can save normally
```

```text
Post-boot unlock / migration
  -> VaultBridge.ensure()
  -> flush or cancel pre-transition pending writes
  -> unlockPrompt() or createOrMigrate()
  -> serialized V455UI.hydrate()
       Settings.load() + Emergency.load()
       reconstruct Pet records and V4.1 fields
       restore monitoring intent, timers and rendering
       normalize duplicate/unbound BLE records
       optionally restart scan
```

```text
Rescue Pack replay check
  -> SHA-256("VitalGuard|VG-RP2|replay|" + jti)
  -> remove expired/invalid entries
  -> compare bounded local profile ledger
  -> compare encrypted-setting compatibility ledger
  -> mark accepted token with hash + capped expiry; never write raw JTI locally
```

---

## 5. Module directory

| Line | Module / anchor | Responsibility |
|---:|---|---|
| 33 | Content-Security-Policy meta | Exact inline authorization, zero network connection source, Trusted Types requirement. |
| 39 | Capability-scope meta | Nonvisual implemented/not-implemented transport statement. |
| 46 | Early hardening core | Frame fail-close, immutable egress stubs, WebRTC/worker blocking, prototype freeze, bounded invariant checks. |
| 135 | Inline stylesheet | Byte-identical to V4.6.9 (stylesheet CSP hash unchanged). |
| 814 | Main application script | All application and hardening modules. |
| 851 | Action dispatcher | Strict first-party allowlist; no `eval`/`Function`; identifier-boundary deny patterns. |
| 1115 | CONFIG | Release, schema, storage, timing, thresholds, and profiles. |
| 1193 | `genLocalIdSuffix()` | Cryptographic local record-ID suffixes. |
| 1419 | Toast | Visual notifications and ARIA live semantics. |
| 1439 | I18N | Seven local dictionaries and Arabic RTL. |
| 3481 | ConfirmModal | Safe destructive focus and cancel semantics. |
| 3580 | Storage facade | IndexedDB-first API and bounded fallback. |
| 3744 | Kalman filter | RSSI smoothing. |
| 3778 | Distance estimator | Approximate RSSI-to-distance and calibration. |
| 3918 | Pet model | Per-tag state, thresholds, histories, serialization. |
| 5189 | BLE matching | Base advertisement scoring. |
| 5222 | BLE engine | Advertisement scanning, restart/congestion/health. |
| 5419 | Wizard | Registration, verification, calibration. |
| 5841 | SOS | Signal review, alarm, Rescue Pack entry points. |
| 5978 | Emergency | Local siren, strobe, contact card. |
| 6531 | Settings | Preferences, performance, volume, pet management. |
| 6689 | Data manager | Hardened import/export entry points. |
| 6771 | Diagnostics | Redacted local diagnostics and self-test entry. |
| 6952 | App core | Initialization, rendering, monitoring and alerts. |
| 8115 | Reset Center | Soft/hard/factory reset paths. |
| 10441 | V455 configuration | Current crypto/storage/import limits with compatibility key names. |
| 10485 | V455Crypto | PBKDF2, AES-GCM, AAD, base64url, SHA-256. |
| 10562 | Encrypted local vault | Single encrypted state envelope, serialized updates, V4.6.9 write epoch. |
| 10819 | Replay guard | Hashed bounded profile ledger plus encrypted compatibility ledger. |
| 10925 | V455UI | Vault UI bridge and authoritative runtime rehydration. |
| 11026 | Final BLE routing | Exact binding first; duplicate exact binding quarantine. |
| 10889 | Binding normalization | Disables unbound and duplicated records until re-registration. |
| 11178 | Passphrase policy | Distinct-word and weak-pattern enforcement. |
| 11317 | Hold cancellation | All gesture interruption paths disarm SOS/Emergency timers. |
| 11340 | Compatibility layer | Nonvisual accessibility, persistence, vault and Rescue bridges. |
| 11351 | ModalA11y | Focus trap, inert background, restoration. |
| 11422 | Semantics | Keyboard roles and synchronized ARIA state. |
| 11447 | Persistence | Debounce, generation guard, tombstones, destructive coordination. |
| 11490 | VaultBridge | Existing-flow vault access and serialized rehydration. |
| 11508 | RescueBridge | Rescue Pack v2 behind the unchanged V4.3.8 control set. |
| 11525 | V4.6.9 final audit hotfix (carried) | Async self-test, capability object, V4.6.9 diagnostics. |
| 11546 | V4.6.9 release note (historical) | Internal-only hotfix scope and deferred work. |
| 11557 | Guarded bootstrap | One-time safe App initialization. |

---

## 6. Storage and data map

| Area | Key / store | Behavior (unchanged from V4.6.9) |
|---|---|---|
| IndexedDB | `VitalGuardAI_V41`, version 2 | Compatibility database with `pets`, `settings`, `ai`, `alerts`, `blobs`. |
| Encrypted vault | `__vg_vault_v455__` | AES-GCM single-state envelope in the settings store. |
| Encrypted fallback | `vg41_vault_v455` | localStorage fallback containing the encrypted envelope only. |
| Language | `vg_lang_v41`, `vg_lang_v412` | Local language preference; now removed by full wipe. |
| Replay compatibility | `rescuePackUsedV455` | Encrypted setting containing bounded hash/expiry entries and legacy-read compatibility. |
| Replay profile ledger | `vg_rp_replay_v469` | Bounded array of SHA-256 JTI hashes and expiries; no raw JTI. |
| Session-only state | memory | Used where no vault is active; registration/export warnings remain. |
| Compatibility prefix | `vg41_` | Deliberately unchanged so prior data is recognized. |

The current vault still uses one encrypted state envelope. Record-per-envelope storage is deferred because it changes migration and recovery semantics.

---

## 7. Passphrase policy

Sensitive passphrase creation is accepted only when the normalized value passes all applicable checks:

1. minimum 16 characters;
2. no control characters;
3. no repeated-character or repeated-phrase pattern;
4. no listed common/project term or predictable sequence;
5. word path: at least four sufficiently long, distinct normalized words, at least 19 total characters, and adequate character variety; or
6. non-word path: sufficient character classes/length and unique-character variety.

Unlocking an existing vault does not apply the creation-strength gate because legacy passphrases must remain usable.

Verified browser vectors:

- repeated words: rejected;
- repeated phrase: rejected;
- project-name phrase: rejected;
- sequential numeric pattern: rejected;
- high-variety complex phrase: accepted;
- four distinct multilingual words: accepted.

---

## 8. BLE duplicate-binding behavior

- a single exact local device binding is evaluated before metadata clone candidates;
- two records with the same exact local browser device ID are never routed;
- both records are disabled and quarantined for local re-registration;
- the registration wizard rejects a device ID already bound to a different record;
- initialization/rehydration strips duplicated IDs from both records and marks them `rebind-required-v455`;
- generic BLE advertisements remain non-cryptographic and cannot establish authenticated identity.

---

## 9. Verification matrix

### 9.1 Static release audit — PASS (V4.7.1)

- both inline scripts passed `node --check`;
- CSP recomputed hashes equal all three declared hashes in the shipped file;
- stylesheet bytes and stylesheet CSP hash are identical to V4.6.9;
- every executable-block difference versus V4.6.9 is a `v4.6.9` → `v4.7.1` display-string change and nothing else (verified by line-level diff of both `<script>` blocks and the `<style>` block);
- external active URL attributes: 0;
- final-DOM `data-vg-on*` actions passing the policy parser: **106**, failures: 0;
- whole-file SHA-256 recomputed only after the CSP was final.

### 9.2 Logic-identity verification — PASS (V4.7.1)

Because V4.7.1 is a version-relabel, the primary verification is that no logic changed relative to the V4.6.9 baseline that already passed the full runtime, crypto and destructive-race harnesses:

- line-level diff of `script[0]`, `script[1]` and `style[0]` shows only `v4.6.9` → `v4.7.1` display strings; the stylesheet is byte-identical;
- guarded boot path, action dispatcher allowlist, and all `V455…`/`V469…` symbols are unchanged;
- final-DOM `data-vg-on*` actions passing the policy parser: **106**, zero policy failures;
- repeated/common/sequential passphrase rejection and strong/multilingual acceptance;
- delayed threshold save followed by pet deletion: no record restoration after 650 ms;
- duplicate stored bindings disabled and stripped;
- duplicate exact routing quarantines both records and processes neither;
- duplicate registration does not add a record;
- rehydration restores volume, V4.1 alert fields, leash distance and lost-event state;
- normal exact-bound routing updates only the intended record;
- full wipe removes pets, language keys and replay ledger;
- persistence is unblocked after wipe and a new volume setting saves successfully;
- page errors: 0; console errors: 0; external requests: 0.

The isolated harness has an opaque origin, so Chromium denies IndexedDB and WebCrypto there. One expected IndexedDB warning is recorded. This does not assert that HTTPS/localhost deployment lacks IndexedDB.

### 9.3 Exact shipped WebCrypto and replay test — PASS (identical bytes to V4.6.9)

The final `V455`, `V455Crypto`, and replay-guard source were extracted from the shipped main-script bytes and executed with Node WebCrypto:

- encrypted round trip passed;
- wrong passphrase rejected;
- AAD metadata tamper rejected;
- malformed base64 produced the controlled error;
- 32 encryptions produced 32 distinct IVs;
- AES-GCM, PBKDF2-SHA-256, 600,000 iterations, 16-byte salt and 12-byte IV confirmed;
- replay mark/seen passed;
- raw JTI absent from the local replay ledger;
- replay hash length: 64 hexadecimal characters;
- local replay detection remained effective after the encrypted compatibility setting was cleared;
- final self-test source awaits both Rescue Pack encode and decode.

### 9.4 Visual compatibility — PASS

- the visible shell and stylesheet are unchanged from V4.6.9;
- the only user-visible textual difference is the release identifier `4.6.9` → `4.7.1`;
- result: pixel-exact after version normalization.

---

## 10. Deployment requirements and residual risk

### Required deployment evidence

When served over HTTP(S), independently verify:

- server CSP including `frame-ancestors 'none'`;
- `X-Content-Type-Options: nosniff`;
- restrictive Permissions Policy;
- `Cross-Origin-Opener-Policy: same-origin`;
- `Cross-Origin-Resource-Policy: same-origin`;
- a clean dedicated origin without a prior uncontrolled Service Worker;
- signed or independently authenticated release manifest delivery.

### Retained residual risks

- advertisement-only BLE identity is spoofable and is not cryptographic authentication;
- physical BLE tags, spoofing transmitters, low-end Android, background suspension, battery use and production headers were not tested in this build environment;
- the visible Swarm/Mesh/SOS-relay wording still exceeds the implemented passive-reception transport; the nonvisual manifest documents the actual boundary but does not remove the visible mismatch;
- the replay ledger is best-effort and browser-profile-local; clearing site data removes it;
- OS/browser TTS, clipboard, notifications, geolocation and Bluetooth permission stacks remain platform trust boundaries;
- historical wrappers and multiple rebinding layers remain, increasing audit complexity;
- the vault remains a single envelope, so small writes still re-encrypt the full sensitive state;
- a detached SHA-256 value is not a signature.

---

## 11. Deferred structural work

The following require a separately scoped release and migration/recovery test matrix:

- independent encrypted envelopes for settings, each pet, AI state and voice blobs;
- automatic migration from the single V455 envelope;
- source-module decomposition and reproducible single-file bundling;
- removal of historical wrappers and duplicate authority paths;
- visible claim/copy correction for Swarm/Mesh/SOS relay;
- physical-device and deployment-header evidence package.

---

## 12. CSP maintenance rule

Any byte change inside either `<script>` block or the `<style>` block invalidates that resource's CSP authorization. Finalization must always:

1. extract exact inner bytes;
2. calculate SHA-256 and base64-encode it;
3. update both applicable `*-src` and `*-src-elem` directives;
4. reread the completed artifact and verify all hashes again;
5. calculate the whole-file SHA-256 only after the CSP is final;
6. rerun syntax, action, runtime, crypto, destructive-race and visual gates.

END OF CODE MAP
