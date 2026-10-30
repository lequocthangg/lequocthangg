<!-- ░▒▓ lequocthangg · security research profile ▓▒░ -->

<div align="center">
  <img src="./assets/header.svg" alt="lequocthangg — mobile security research" width="100%" />
</div>

<p align="center">
  <img alt="field: mobile security" src="https://img.shields.io/badge/field-mobile_security-00ff9c?style=flat-square&labelColor=0b1016" />
  <img alt="reverse engineering" src="https://img.shields.io/badge/core-reverse_engineering-00e0ff?style=flat-square&labelColor=0b1016" />
  <img alt="eKYC and liveness testing" src="https://img.shields.io/badge/focus-eKYC_%2F_liveness_testing-f472b6?style=flat-square&labelColor=0b1016" />
  <img alt="device integrity research" src="https://img.shields.io/badge/focus-device_integrity-fde047?style=flat-square&labelColor=0b1016" />
</p>

---

> **Mobile RE & identity-attack researcher.** I test how eKYC, liveness and device-integrity
> controls fail — then build the detections that catch it. I work the whole loop: reverse-engineer
> the app and runtime, measure where authentication over-trusts, reproduce the gap in a controlled
> lab, then design and attack my own mitigation until it holds. Strictly on devices, apps, models
> and environments I own or am authorized to test.
>
> 🔒 **Most of my work lives in private repositories** — targets, PoCs and findings are sensitive.
> This profile describes the *methodology*, not the artifacts. Details available on request, under
> appropriate terms.

<div align="center">
  <img src="./assets/terminal.svg" alt="whoami: lequocthangg, born 2006 — mobile RE, eKYC/liveness attack testing, device integrity; rules of engagement: only owned or authorized targets, self-hosted models or sandboxes with written consent, never real identities or funds, coordinated disclosure" width="730" />
</div>

## ▌ Research Tracks

| # | Track | What I actually do |
|---|-------|--------------------|
| `01` | **Reverse Engineering** | Static + dynamic analysis of Android & iOS apps and native code — disassembly, decompilation, runtime tracing and hooking to understand how a binary really works. |
| `02` | **eKYC & Liveness Testing** | Measuring where remote identity-proofing and liveness/face-auth pipelines over-trust — run as controlled attack tests against self-hosted models or sandboxes, framed around PAD (ISO/IEC 30107-3) coverage. Output: detections, not tooling. |
| `03` | **Device Integrity (Root / JB)** | Rooting and jailbreaking as a research platform — `KernelSU-Next`, `roothide`, root-hiding modules — to measure which root/JB/hook signals survive hiding and which detections still hold. |
| `04` | **Custom ROM / Kernel** | Flashing custom ROMs and kernels to keep clean, reproducible test devices — a controlled baseline for every experiment above. |
| `05` | **Injection-Attack Testing (Android + iOS)** | Virtual-camera / camera-pipeline injection PoCs on my own devices — mapping where presentation-attack detection (PAD) stops and injection-attack detection (IAD, CEN/TS 18099) has to take over. |
| `06` | **Defense Engineering & Self-Testing** | The other half of the loop: take every weakness I can prove, build the mitigation, then attack my own fix. Nothing ships in my notes until it survives me. |
| `07` | **AI Agents & Automation** | LLM-driven agents that automate the tedious parts of research — triage, repetitive instrumentation, log/report synthesis — so human time goes to the hard problems. |

<div align="center">
  <img src="./assets/pipeline.svg" alt="Methodology: recon → reverse → threat model → PoC → harden → automate" width="100%" />
</div>

## ▌ Arsenal

<p align="center">
  <img alt="Frida" src="https://img.shields.io/badge/Frida-E63946?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="Ghidra" src="https://img.shields.io/badge/Ghidra-5B2C6F?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="IDA Pro" src="https://img.shields.io/badge/IDA_Pro-2D2D2D?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="radare2" src="https://img.shields.io/badge/radare2-1E1E1E?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="LLDB" src="https://img.shields.io/badge/LLDB-262D3A?style=for-the-badge&logoColor=white&labelColor=0b1016" />
</p>
<p align="center">
  <img alt="Magisk" src="https://img.shields.io/badge/Magisk-00AF9C?style=for-the-badge&logo=magisk&logoColor=white&labelColor=0b1016" />
  <img alt="KernelSU-Next" src="https://img.shields.io/badge/KernelSU--Next-FF6D00?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="roothide" src="https://img.shields.io/badge/roothide-1C1C1C?style=for-the-badge&logo=apple&logoColor=white&labelColor=0b1016" />
  <img alt="LSPosed" src="https://img.shields.io/badge/LSPosed-6A1B9A?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="jadx" src="https://img.shields.io/badge/jadx-4B8BBE?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="apktool" src="https://img.shields.io/badge/apktool-7C4DFF?style=for-the-badge&logoColor=white&labelColor=0b1016" />
  <img alt="Theos" src="https://img.shields.io/badge/Theos-262626?style=for-the-badge&logo=apple&logoColor=white&labelColor=0b1016" />
</p>
<p align="center">
  <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white&labelColor=0b1016" />
  <img alt="C" src="https://img.shields.io/badge/C-00599C?style=for-the-badge&logo=c&logoColor=white&labelColor=0b1016" />
  <img alt="C++" src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white&labelColor=0b1016" />
  <img alt="Kotlin" src="https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white&labelColor=0b1016" />
  <img alt="Swift" src="https://img.shields.io/badge/Swift-F05138?style=for-the-badge&logo=swift&logoColor=white&labelColor=0b1016" />
  <img alt="Smali" src="https://img.shields.io/badge/Smali-A4C639?style=for-the-badge&logo=android&logoColor=white&labelColor=0b1016" />
</p>

## ▌ Current Research

```text
[~] KernelSU-Next ............ kernel-based root; what integrity checks still see
[~] Root / JB detection ...... which signals survive hiding — and how to harden them
[~] Custom ROM + kernel ...... clean, reproducible test devices
[~] eKYC liveness lab ........ PAD vs. injection coverage, self-hosted models only
[~] agent tooling ............ LLM agents that drive the repetitive RE work
```

## ▌ Rules of Engagement

```diff
+ I test only devices, apps and models I own or am explicitly authorized to test.
+ eKYC / liveness work runs on self-hosted models, vendor sandboxes with written
+ permission, or in-scope bug-bounty targets — never live onboarding.
+ Never real identities, live accounts, or real money.
+ Break it to understand it, then build the detection. Coordinated disclosure, always.
```

> I share *methods of thinking* and *defensive lessons* — not turnkey tooling for fraud.

## ▌ Contribution Snake

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/lequocthangg/lequocthangg/output/snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/lequocthangg/lequocthangg/output/snake.svg" />
    <img alt="my contribution graph being eaten by a snake" src="https://raw.githubusercontent.com/lequocthangg/lequocthangg/output/snake-dark.svg" width="100%" />
  </picture>
</div>

<div align="center">
  <br/>
  <code>thang@research:~$ whoami</code> → <b>a builder who breaks things on purpose, so they break less in the wild.</b>
</div>
