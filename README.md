<p>
    <strong>一款指纹识别工具</strong>
</p>

<p align="center">
    <a href="https://github.com/yourusername/muki/blob/main/LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg"></a>
    <a href="https://github.com/yourusername/muki/releases"><img src="https://img.shields.io/github/v/release/yourusername/muki"></a>
    <a href="https://golang.org/"><img src="https://img.shields.io/badge/language-Go-blue.svg"></a>
</p>
</p>
<p align="center">
  <img width="324" height="120" alt="Muki - Active Asset Fingerprinting Tool" src="https://github.com/user-attachments/assets/fd331a9e-7628-462e-9189-3eb8387323c6" />
</p>
<p align="center">
Muki is a brand-new active asset fingerprinting tool designed for red team operations. During reconnaissance, Muki enables security researchers to rapidly pinpoint vulnerable systems from chaotic C-class segments and massive asset lists, enabling targeted exploitation.

---

- **Smart Deduplication**: Advanced deduplication algorithm based on URL standardization to dramatically improve scanning efficiency

- **Multi-format Export**: Export results in both Excel (.xlsx) and JSON formats for seamless analysis

- **Key Asset Extraction**: Automatically identifies and exports critical systems, highlighting high-value targets

- **Thread Control**: Customize concurrency level with `-T` flag to balance speed and stability

- **False Positive Reduction**: Fixed common false positives (e.g., GeoServer) with refined signature matching

- **30,000+ Precision Fingerprints**: Built-in library of over 30,000 validated active fingerprint rules covering mainstream frameworks, middleware, APIs, and vulnerability signatures

- **Dual-mode Output**: Excel files automatically split into two sheets — “Passive Fingerprinting” and “Active Fingerprinting” — for clear audit trails

---


Release 2.02



![录屏2025-11-26 10 04](https://github.com/user-attachments/assets/3f864d60-e40e-499a-ad84-dd951503138b)




安装

直接拉取linux版本
git clone https://github.com/yourusername/muki.git 
cd muki|chmod +x muki-linux-amd64
./muki-linux-amd64

