# 🔐 Project 3: Credentialed Vulnerability Scan using OpenVAS

## 🎯 Objective

To perform a **credentialed (authenticated) vulnerability scan** using OpenVAS in order to gain deeper visibility into system-level vulnerabilities.

---

## 🖥️ Target Information

* **Target IP:** 192.168.1.82
* **Environment:** Local system (authorized)
* **Authentication Method:** SSH (Username + Password)

---

## ⚙️ Methodology

1. Configured SSH access on the target system
2. Verified SSH login manually
3. Created SSH credential in OpenVAS
4. Configured target with real IP (not localhost)
5. Executed **Full and Fast scan with credentials**
6. Analyzed vulnerability report

---

## 🔑 Key Learning (Critical Insight)

> Using `127.0.0.1` failed because OpenVAS runs in a separate environment.
> Switching to the actual local IP (**192.168.1.82**) enabled proper credentialed scanning.

---

## 📊 Scan Results Summary

| Severity    | Count |
| ----------- | ----- |
| 🔴 Critical | 1     |
| 🟠 High     | 8     |
| 🟡 Medium   | 4     |
| 🔵 Low      | 3     |

---

## 🚨 Key Findings

### 🔴 Critical Vulnerability

* **VLC Media Player DoS Vulnerability**
* Cause: Heap overflow
* Impact: Crash or possible code execution

---

### 🟠 High Severity Issues

* Multiple **outdated packages**:

  * ffmpeg
  * gstreamer
  * mupdf
  * cjson
* Risk:

  * Remote Code Execution (RCE)
  * Denial of Service (DoS)

---

### 🟡 Medium Severity Issues

* Additional outdated packages
* Software vulnerabilities requiring updates

---

### 🧠 System-Level Finding

* Missing Linux kernel mitigation for:

  * **GDS (Downfall) hardware vulnerability**
* Risk: Potential data leakage at CPU level

---

## 🔍 Why Credentialed Scan Matters

Unlike normal scans, this scan:

* Accessed internal system via SSH
* Detected installed software versions
* Identified real vulnerabilities (not just services)

---

## 🛠️ Recommendations

```bash
sudo apt update && sudo apt upgrade -y
```

* Update all vulnerable packages
* Upgrade VLC, ffmpeg, gstreamer
* Apply kernel updates
* Enable regular security patching

---

## 🧠 Conclusion

The credentialed scan successfully revealed **critical and high-risk vulnerabilities** that were not visible in non-authenticated scans.

> Most vulnerabilities were caused by **outdated software and missing security patches**.

---

## ⚠️ Disclaimer

This scan was performed on my own system for **educational and ethical purposes only**.

