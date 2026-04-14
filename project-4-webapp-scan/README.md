# 🌐 Project 4: Web Application Scan using OpenVAS

## 🎯 Objective

To perform a vulnerability assessment of a web-accessible system using OpenVAS and identify potential security issues from an external (non-credentialed) perspective.

---

## 🖥️ Target Information

* **Target IP:** 192.168.1.82
* **Service:** Apache Web Server (HTTP)
* **Scan Type:** Non-Credentialed (External Scan)

---

## ⚙️ Methodology

1. Installed and started a local web server (Apache)
2. Verified web service availability via browser
3. Created target in OpenVAS using system IP
4. Performed a **Full and Fast scan**
5. Analyzed vulnerability report

---

## 📊 Scan Results Summary

| Severity    | Count |
| ----------- | ----- |
| 🔴 Critical | 0     |
| 🟠 High     | 0     |
| 🟡 Medium   | 0     |
| 🔵 Low      | 3     |

---

## 🔍 Key Findings

### 1️⃣ ICMP Timestamp Information Disclosure

* The system responds to ICMP timestamp requests
* **Risk:** May expose system time and assist attackers in reconnaissance

---

### 2️⃣ Weak MAC Algorithms Supported (SSH)

* SSH service supports weak MAC algorithms such as `umac-64`
* **Risk:** Reduced integrity protection for SSH communication

---

### 3️⃣ TCP Timestamp Information Disclosure

* System exposes TCP timestamps
* **Risk:** Allows estimation of system uptime

---

## 🧠 Key Learning

* Non-credentialed scans provide **external visibility only**

* They detect:

  * open ports
  * network behavior
  * protocol-level issues

* They do NOT detect:

  * installed software vulnerabilities
  * internal system misconfigurations

---

## 🔍 Comparison with Credentialed Scan

| Aspect       | Credentialed Scan | Web Scan |
| ------------ | ----------------- | -------- |
| Access Level | Internal          | External |
| Depth        | Deep              | Surface  |
| Findings     | Critical/High     | Low only |

---

## 🛠️ Recommendations

* Disable ICMP timestamp responses
* Disable TCP timestamps
* Remove weak SSH MAC algorithms
* Harden system configurations

---

## 🧠 Conclusion

The scan revealed **only low-level vulnerabilities**, mainly related to information disclosure and protocol configurations.

> These issues do not directly compromise the system but may assist attackers during reconnaissance.

---

## ⚠️ Disclaimer

This scan was performed on my own system for **educational and ethical purposes only**.

