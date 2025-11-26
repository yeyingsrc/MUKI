<p>
    <strong>A fingerprinting tool</strong>
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

- **Smart Deduplication**: URL normalization–based deduplication for higher scan efficiency  
- **Multi-format Export**: Results exported in Excel (.xlsx) and JSON  
- **Key Asset Extraction**: Auto-identifies and highlights high-value targets  
- **Thread Control**: Adjust concurrency with `-T` for optimal speed/stability  
- **Reduced False Positives**: Refined matching logic (e.g., fixed GeoServer FPs)  
- **30,000+ Precision Fingerprints**: Covers mainstream frameworks, middleware, APIs, and known vulnerabilities  
- **130+ Active Fingerprint Rules**: Targeted probes for accurate service detection  

Release 2.02



![录屏2025-11-26 10 04](https://github.com/user-attachments/assets/3f864d60-e40e-499a-ad84-dd951503138b)

command-line options:

    -t,  --threads <num>        Set the number of concurrent threads (default: auto).

    --proxy= <url>              Specify an HTTP/HTTPS/SOCKS proxy (e.g., http://127.0.0.1:8080).

    -N,  --no-path-scan        Disable directory/path enumeration.

    -A,  --no-active-fp        Disable active fingerprinting (e.g., service/version detection via probes).

    -x,  --no-passive-fp       Disable passive fingerprinting (e.g., fingerprint inference from responses).

    -u,  --target <url>        Scan a single target URL or IP address.

    -l,  --target-list <file>  Perform batch scanning from a file containing multiple targets (one per line).


Introduction

<img width="517" height="886" alt="whiteboard_exported_image" src="https://github.com/user-attachments/assets/86a79ecd-30e5-405e-a308-5b3b01397c07" />


The tool performs systematic reconnaissance through a four-stage pipeline: asset ingestion → parallel probing → data aggregation → structured reporting. 

Asset Ingestion
Targets (IPs, domains, URLs) are loaded from an external list, defining scan scope and ensuring reproducibility. 

Parallel Probing Modules
Three independent modules run concurrently: 
     

Active Fingerprinting: Sends protocol-specific probes to identify services (e.g., SSH, RDP, web servers) with high confidence.  
Passive Fingerprinting: Analyzes response artifacts (HTTP headers, TLS JA3, HTML patterns) to infer frameworks, WAFs, or CMS without additional traffic.  
Sensitive Path Detection: Checks for high-risk paths—including admin interfaces (e.g., /admin), config files (e.g., .env), version control dirs (e.g., /.git), and known vulnerability endpoints (e.g., Spring Boot Actuator, ThinkPHP routes)—using curated dictionaries and response validation.
     

Each module can be disabled via command-line flags (-A, -x, -N) for operational flexibility. 

Data Aggregation
Raw results are normalized, deduplicated, correlated (e.g., paths linked to hosts), and optionally enriched with vulnerability intelligence. 

Report Generation
Outputs machine-readable reports (JSON/XLSX/) containing: 
     

Asset inventory  
Service fingerprints (active/passive)  
Confirmed sensitive paths with HTTP status codes  
Actionable risk indicators
     

Designed for red team operations, attack surface mapping, and security validation—prioritizing precision, coverage, and integration readiness. 
