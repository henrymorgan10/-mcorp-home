## I’m just a blacksmith forging tools

<img width="358" height="237" alt="1" src="https://github.com/user-attachments/assets/1ed6d48d-46cc-4ede-8736-9496dec6280b" />

## If you underpay the blacksmith, you’ll only get cheap tools.

**The following 10 principles are non-negotiable in my AI design philosophy:**
1. Hallucinations must be minimized.
2. Transparency must be fully guaranteed.
3. AI must remain free or extremely affordable, even in low-income environments.
4. Data exploitation must be completely eliminated.
5. AI must operate reliably in low-resource environments.
6. Legal liability risks (including GDPR-related risks) must be minimized as much as possible.
7. The system must be open-source and customizable by anyone.
8. Simplicity, standardization, and modularity must be prioritized.
9. The system must be accessible and understandable to non-specialists.
10. The AI must not collect unnecessary data, and if any data is stored, users must be able to delete it easily at any time.

## I am a white-box AI architect. “I deeply respect open-source culture.”

**The AI I develop is not designed for the wealthy. It is designed for the socially vulnerable, the poor, and those most in need.**

The AI I develop is not a black-box AI designed to replace human jobs. It is a white-box AI designed to create jobs and opportunities for people living in poverty.

White-box AI is built through the contributions of many individuals, allowing fair and legitimate compensation to be distributed to those in need. Even something as simple as typing “Hello, World!” can become a meaningful contribution that enables people in low-income environments to receive legal payment for their work.

**White-box AI can evolve into a large-scale ESG ethical certification system.** 

In other words, when wealthy individuals or organizations donate to white-box AI initiatives, they can receive ESG ethical certification reports documenting their humanitarian and social contributions. At the same time, people living in low-income environments can contribute to the white-box AI ecosystem and receive fair and legitimate compensation for their work.

Fair compensation is not just about money — it can also restore dignity, strengthen self-esteem, and give people a meaningful sense of purpose and participation in society.

**Massive data centers are often an inefficient use of resources.** They consume enormous amounts of money just to maintain infrastructure and server operations. If even a fraction of that investment were redirected toward building white-box AI, tens of thousands of people living in poverty could directly benefit from it.

All academic contributions worldwide are provided completely free of charge. If these contributions are recognized as meaningful ethical and humanitarian work, I believe that a public nomination for the Nobel Peace Prize would also be justified. Moral authority can help save even more lives. 

I have also already developed a refugee self-sufficiency model — **[McorpAi.org](https://mcorpai.org/)** — an AI system designed to help refugees achieve self-reliance within refugee camps themselves, without requiring relocation to other countries. A sovereign AI system that refugees can directly operate means that refugee communities themselves can become self-sustaining.

> **This “Pet Safety Leash” UI is a neutral demo skin for everyday usability testing.**  
> Under the hood, it is an **Offline Bluetooth Swarm Network** built for zero‑infrastructure disaster response.  
> When internet and grid power collapse to zero—wildfires, floods, hurricanes—devices self‑organize and keep operating.  
> No cloud. No cell towers. No accounts: local coordination, SOS relay, and continuity across nearby nodes.  
> **Early‑warning system + life‑saving mesh**—an infrastructure‑independent resilience layer, deployable from ordinary phones.

# VitalGuard AI - Infrastructure-Independent Survival Framework

VitalGuard AI is a **single-file, offline-first** continuity demo that keeps **local decision support** available when **power and connectivity are disrupted** - with **no accounts, no cloud dependency, and no telemetry by design**.
**UI languages (7):** English · 한국어 · العربية (RTL) · 日本語 · Français · 繁體中文(台灣) · Español

**Format:** one self-contained HTML file (no build system; no external JS/CSS libraries)

---

## Document control (government / enterprise friendly)

| Field | Value |
|---|---|
| Document | VitalGuard AI README (Executive + Audit Notes) |
| Release artifact | `VitalGuard_AI_complete_V42_1.html` (single-file offline demo) |
| Version | v4.2 |
| Release date | 2026-02-17 |
| Owner | Morgan J. (Gyumin Jeon) |
| Contact | contact@mcorpai.org (mcorpai.org) |
| Classification | Unclassified - For external review |

---

## Release integrity (recommended for restricted environments)

**SHA-256 (approved artifact):** `f37502a9f511c856d4c6d720b93cac202214ff23e01280d7f69eabf33bdd3721`  
**File size:** 412572 bytes (~402.9 KiB)

Integrity verification commands:
- macOS: `shasum -a 256 VitalGuard_AI_complete_V42_1.html`
- Linux: `sha256sum VitalGuard_AI_complete_V42_1.html`
- Windows (PowerShell): `Get-FileHash .\VitalGuard_AI_complete_V42_1.html -Algorithm SHA256`

Why this matters:
- **Single audited artifact:** reduces runtime supply-chain exposure and "what exactly ran?" ambiguity.
- **Tamper-evident distribution:** reviewers can record the hash in a change-control memo (and optionally attach a digital signature) before use.

---

## Executive brief (60 seconds)

**What it is**
- A **local-only** web demo that uses **Bluetooth Low Energy (BLE) proximity (RSSI)** plus **on-device stability logic** to support **short-range coordination** when networks are unreliable.

**What it's for**
- Demonstrating **offline continuity patterns** for disaster response / field operations:
  - proximity-based mustering / asset boundary alerts,
  - short-range search & rescue assistance workflows (BLE proximity - not GPS),
  - offline hand-off continuity between devices (encrypted export option).

**What it is NOT**
- **Not GPS** (no map, no geolocation), and **not certified emergency/medical equipment**.
- Not a cloud product (no accounts, no remote control, no analytics).
- Not a "tracking platform" (no central database; no remote admin).

**Decision question this demo answers**
- "Can we evaluate an offline-first proximity/stability workflow without introducing cloud risk or third-party runtime dependencies?"

---

## Main-screen pillars (field narratives)

1) **Extreme S&R (Avalanche/Landslide)** - BLE beacon proximity + on-device stability logic to support a radar-like life-locator workflow when responders are operating off-grid.  
2) **Upcycling E-Waste (ESG & SDGs)** - repurpose retired smartphones into offline relief nodes, aligning with ESG and UN SDG objectives.  
3) **Off-Grid Agriculture & Asset Protection** - practical patterns for livestock and asset safety in rangeland/desert environments with no coverage.  
4) **Arabic & Global Ready** - multilingual UI is built in (7 languages), including Arabic (RTL).

---

## Threat model (half-page, review-friendly)

**In-scope assurances (what this demo is designed to resist):**
- **Cloud / telemetry risk by architecture:** no accounts, no analytics, no outbound endpoints in normal use.
- **Runtime supply-chain exposure:** no external JS/CSS/CDN dependencies at runtime (single-file artifact).
- **Accidental data leakage during review:** data stays in browser storage unless the user explicitly exports.

**Out-of-scope / non-goals (what this demo does NOT claim to protect against):**
- **Compromised device/OS:** malware, rooted devices, hostile firmware, or untrusted keyboards.
- **Malicious browser extensions / injected scripts** (enterprise add-ons, spyware, hostile profiles).
- **Physical capture of an unlocked device** (or screen/shoulder surfing).
- **Hostile MDM policies** (forced proxies, certificate injection, restricted Bluetooth policies).
- **Radio-layer attacks** (spoofed BLE advertisers, jamming, RF interference) beyond basic stability heuristics.

**Operational takeaway:** treat VitalGuard as a **reviewable prototype**. For real deployments, pair it with device hardening, policy controls, and a formal incident/assurance process.

---

## Acceptance criteria (5-line "pass/fail" checklist)

Use these as fast, objective "done" conditions for reviewers:

1) **Outbound requests to non-self origins: 0** during normal use (DevTools -> Network).  
2) **External runtime dependencies: 0** (no third-party `<script src=...>` / remote fonts / CDNs).  
3) **Local data is removable** (UI reset controls clear browser storage for the demo).  
4) **Offline usability**: in Airplane Mode, non-BLE features (Help, SOS UI, local data) remain usable.  
5) **BLE scan stability (foreground)**: on a supported device/browser, scanning remains stable for an evaluation window (e.g., 10-15 minutes) with watchdog recovery logged if stalls occur.

---

## How to run the demo (practical)

1. Open `VitalGuard_AI_complete_V42_1.html`.
2. Use a Chromium-based browser that supports Web Bluetooth scanning (platform support varies).
3. For the most reliable BLE behavior, open from a **secure context**:
   - `https://...` or `http://localhost` (recommended)
   - Avoid `file://` for scanning where possible (many browsers restrict Web Bluetooth on local files).
4. Optional (recommended when policy allows): **Install as an app (PWA).**
   - In Chrome/Edge, use **Install app** / **Add to Home Screen** so the demo runs in a dedicated window.
   - This can reduce accidental tab suspension and improve operational stability, but BLE scanning reliability remains OS/browser policy-dependent.
   - Keep the app **in the foreground** during BLE operations.
5. Click **Add Demo Tag** -> register a BLE tag -> start monitoring.

---

## Key verifiable claims (audit-friendly)

| Claim | How to verify (5 minutes) |
|---|---|
| Offline-first / local-only by default | Open DevTools -> Network, then use the UI. There should be no unexpected outbound requests to non-self origins during normal use. |
| No accounts / no cloud sync / no telemetry | Search the HTML for analytics endpoints, external scripts, or tracking code. Verify UI has no sign-in. |
| No third-party runtime dependencies | Confirm there are no external `<script src=...>` libraries loaded at runtime. |
| Data stays on device | Confirm browser local storage is used. Verify nothing leaves the device unless you explicitly export/share. |
| Optional secure hand-off | If using encrypted export, confirm it uses AES-GCM via WebCrypto (on-device). |

---

## Platform compatibility (typical)

| Platform | Expected status | Notes |
|---|---|---|
| Android + Chrome/Edge | Best experience | Web Bluetooth scanning support is strongest here. |
| Windows/macOS + Chrome/Edge | Often works | Depends on browser policies and BLE hardware support. |
| iOS/iPadOS + Safari/Chrome | Often limited | Web Bluetooth support differs; scanning may be unavailable. |
| Locked-down enterprise builds | Policy-dependent | BLE and local storage may be restricted by MDM policies. |

---

## Limitations (important)

- **BLE RSSI is not a tape measure.** Walls, pockets, bodies, and reflections distort signal strength.
- Scanning can pause due to OS battery restrictions; the demo includes watchdog recovery, but background behavior varies by device.
- This is a **technology demonstration**, not a certified safety/medical product.

---

## Provenance

- Official site: https://mcorpai.org  
- Demo (hosted): https://mcorpai.org/VitalGuard_AI  
- Source (GitHub): https://github.com/jekymin8232/luckyvicky-homepage  
- Contact: Morgan J. (Gyumin Jeon) - contact@mcorpai.org

---

*This README is not legal advice.*
