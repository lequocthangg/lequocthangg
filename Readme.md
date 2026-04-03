<div align="center">

```
███████╗ █████╗ ██╗     ███████╗███████╗
╚══███╔╝██╔══██╗██║     ██╔════╝██╔════╝
  ███╔╝ ███████║██║     █████╗  ███████╗
 ███╔╝  ██╔══██║██║     ██╔══╝  ╚════██║
███████╗██║  ██║███████╗███████╗███████║
╚══════╝╚═╝  ╚═╝╚══════╝╚══════╝╚══════╝
```

### Mobile Security · Reverse Engineering · Camera Systems

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&size=16&pause=1200&color=FF4444&center=true&vCenter=true&width=600&lines=iOS+%2F+Android+Reverse+Engineering;Binary+Patching+%7C+Hook+Injection;AES+%2F+RSA+%2F+ECC+Cryptanalysis;Camera+Spoofing+%26+Anti-Detection;Native+.so+Injection+%7C+Frida+%7C+Ghidra)](https://git.io/typing-svg)

</div>

---

## 👤 Identity

```yaml
alias     : Zales
location  : Ho Chi Minh City, Vietnam 🇻🇳
org       : "@trustingsocial"
focus     : Mobile security · RE · Camera systems
languages : Kotlin · Python · JavaScript · Java · C/C++ (native)
timezone  : UTC+07:00
```

---

## 🔬 Research Projects

### [`VcamIOS`](https://github.com/lequocthangg/Vcamlos) · iOS Reverse Engineering & Auth Bypass Toolkit

> Full RE workflow on a real-world iOS camera app — from binary extraction to complete auth bypass.

```
[.deb package]
    │
    ├─ patch_ip.js (Node.js)         → Hex-patch hardcoded API endpoint in dylib
    │       └─ Fixed-length replace, null-byte padding, port injection (:80)
    │
    ├─ vcam_server.py (Python/Flask) → Emulate backend, intercept encrypted traffic
    │       ├─ AES-CBC decrypt  →  key extracted from binary
    │       ├─ Dynamic IV / zero-IV fallback
    │       └─ Always returns: {"code":0,"txt":"OK","token":"Zales_<ts>"}
    │
    └─ patched.deb                   → Re-signed, ready to sideload
```

**Attack flow:**
```
App → patched dylib → attacker server → AES decrypt → log & analyze → fake response → ✅ bypass
```

**Tools:** `Frida` `Ghidra` `IDA Pro` `Burp Suite` `Node.js` `Python` `Flask` `PyCryptodome` `adb` `dpkg` `ar` `zstd`

---

### [`mexico-2QR`](https://github.com/lequocthangg/mexico-2QR) · INE Multi-Part QR Decoder

> Reverse engineered cryptographic pipeline of a real-world identity card system (Mexico INE) that splits data across 2 QR codes.

```
[QR1.png] + [QR2.png]
    │
    ├─ QR Extraction     → zxing-cpp (primary) / pyzbar / OpenCV (fallback)
    ├─ Segment Merge     → [2-byte index] + payload → sorted + concatenated
    ├─ RSA Stage 1       → Public decrypt → part B
    ├─ RSA Stage 2       → Merge A+B → full block decrypt
    ├─ ECC Verify        → secp256r1, SHA-256, r‖s (64-byte sig)
    ├─ Bit Unpack        → 6-bit packed stream → binary reconstruction
    └─ WEBP Rebuild      → Inject 23 constant bytes → valid RIFF/WEBP output
```

| Script | Purpose |
|---|---|
| `decode_1img.py` | Single-image multi-QR extraction with fallback chain |
| `gIMG.py` | Full pipeline → extract embedded WEBP image |
| `gTxt.py` | Full pipeline → extract text payload |

**Tools:** `Ghidra` `Burp Suite` `Python` `zxing-cpp` `OpenCV` `pyzbar` `RSA` `ECC P-256` `SHA-256` `PIL`

---

### [`VcamAndroid`](https://github.com/lequocthangg/VcamAndroid) · Android Native Library Wrapper

> Kotlin Android app wrapping 3 low-level ARM64 binaries to inject a virtual camera hook into `cameraserver` via SU shell.

```
APK assets/arm64-v8a/
    ├─ vcam-inject          (injection utility)
    ├─ libvcam-hook.so      (camera hook library)
    └─ libshadowhook.so     (shadow hook support)

Runtime flow:
    Extract from APK assets → app private dir
    Deploy via SU → /data/local/tmp/vcam/
        chmod 755 vcam-inject
        chmod 644 *.so
    export LD_LIBRARY_PATH=/data/local/tmp/vcam
    vcam-inject inject -so libvcam-hook.so → cameraserver PID
    Verify → /proc/[pid]/maps
```

**App UI:** `Deploy Binaries` · `Inject Hook` · `Eject Hook` · `Check Status`

**Arch:** Root / SU required · Android 7.0+ API 24+ · ARM64 only

**Tools:** `IDA Pro` `Frida` `Kotlin` `JNI` `Android SDK` `Camera2` `SU shell` `adb`

---

### [`DetectVcam`](https://github.com/lequocthangg/DetectVcam) · Android Anti-VCam Detection Module

> Research module detecting virtual camera injection by exploiting inconsistencies between CameraX pipelines.

```
Core insight:
    VideoCapture  (stream sharing OFF) → cannot be hooked → trusted ground truth ✅
    ImageAnalysis / Camera2            → always hookable  → attacker surface    ❌

Detection algorithm:
    1. Open Preview + ImageAnalysis   (potentially compromised)
    2. Switch to VideoCapture         (trusted, unhookable path)
    3. Record short clip → extract frame via MediaMetadataRetriever
    4. Bitmap diff: ImageAnalysis frame vs VideoCapture frame

    diff > 6%  →  🚨 FRAUD — virtual camera detected
    diff ≤ 6%  →  ✅ CLEAN — real camera confirmed
```

**Tech:** `Java` `CameraX` `Camera2 API` `VideoCapture` `ImageAnalysis` `Bitmap diff` `MediaMetadataRetriever`

---

## 🛠️ Toolchain

### Reverse Engineering
![Frida](https://img.shields.io/badge/Frida-FF4E00?style=for-the-badge&logoColor=white)
![Ghidra](https://img.shields.io/badge/Ghidra-CC0000?style=for-the-badge&logoColor=white)
![IDA Pro](https://img.shields.io/badge/IDA_Pro-4A90D9?style=for-the-badge&logoColor=white)
![Burp Suite](https://img.shields.io/badge/Burp_Suite-FF6600?style=for-the-badge&logoColor=white)
![adb](https://img.shields.io/badge/adb%20%2F%20dpkg-3DDC84?style=for-the-badge&logo=android&logoColor=white)

### Mobile & Native
![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![iOS](https://img.shields.io/badge/iOS-000000?style=for-the-badge&logo=apple&logoColor=white)
![C++](https://img.shields.io/badge/C%2FC%2B%2B-00599C?style=for-the-badge&logo=c&logoColor=white)
![Java](https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)

### Crypto & Data
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![OpenCV](https://img.shields.io/badge/OpenCV-5C3EE8?style=for-the-badge&logo=opencv&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)

---

## 📊 Stats

<div align="center">

<img height="175em" src="https://github-readme-stats.vercel.app/api?username=lequocthangg&show_icons=true&theme=github_dark&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d1117&title_color=FF4444&icon_color=FF4444&text_color=c9d1d9"/>

<img height="175em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=lequocthangg&layout=compact&langs_count=10&theme=github_dark&hide_border=true&bg_color=0d1117&title_color=FF4444&text_color=c9d1d9&count_private=true"/>

</div>

<div align="center">

<img src="https://streak-stats.demolab.com?user=lequocthangg&theme=github-dark-blue&hide_border=true&background=0d1117&ring=FF4444&fire=FF4444&currStreakLabel=FF4444"/>

</div>

---

## 🕒 Recent Activity — April 2026

| Repository | Commits | Domain |
|---|---|---|
| `Vcamlos` | 8 | iOS binary patching & server emulation |
| `mexico-2QR` | 6 | Cryptographic QR pipeline (RSA + ECC) |
| `DetectVcam` | 6 | Anti-spoofing detection (CameraX diff) |
| `VcamAndroid` | 2 | Android native .so hook injection |

> All repositories are **private** — 28 contributions tracked in 2026

---

## ⚠️ Disclaimer

> All projects are for **educational and security research purposes only.**
> Techniques are used to understand vulnerabilities and improve defensive security.

---

<div align="center">

*"Code is my life"* — **Zales**

![Profile Views](https://komarev.com/ghpvc/?username=lequocthangg&color=FF4444&style=flat-square&label=profile+views)

</div>
