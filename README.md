# phishing-email-analysis-task
This file contains a sample of a phishing email designed to impersonate PayPal. It is intended for training, analysis, or demonstration purposes only.
# 🛡️ Phishing Email Investigation - PayPal Case Study

This repository contains a detailed analysis of a **phishing email** impersonating PayPal, showcasing spoof detection techniques using email headers and content traits.

---

## 📧 Sample Email Overview

A suspicious email claiming to be from **PayPal Support** with the subject:

> **"Verify your recent Paypal Login."**

- **From:** `support@paypaypal.net`
- **To:** `john.doe@mybusiness.com`
- **Content:** Urges the user to verify login details via a button or link.

---

## 🔍 Phishing Traits Identified

| **Phishing Trait**              | **Evidence in Sample Email**                                                                 |
|-------------------------------|----------------------------------------------------------------------------------------------|
| **Spoofed sender email**       | `support@paypaypal.net` domain used instead of official `paypal.com`                        |
| **Urgent/threatening language**| Phrases pressing immediate action and fear                                                  |
| **Suspicious CTA button**      | Likely redirects to a non-PayPal domain (link hover mismatch)                               |
| **Generic greeting**           | Uses only a first name or no personalization                                                |
| **Grammar issues**             | Minor unnatural phrasing or placeholder errors                                              |
| **Threat of restriction**      | Mentions account blocking or limitations if user doesn't act quickly                        |
| **Credential request**         | Asks user to update login credentials via suspicious link                                   |

---

## 🧾 Header Analysis

The full email header was extracted and analyzed using **Google Header Analyzer** and manual inspection.

### ✅ Key Findings

| Field        | Result & Red Flag                                 |
|--------------|---------------------------------------------------|
| **SPF**      | `softfail` — IP not authorized to send as domain |
| **DKIM**     | `none` — No digital signature detected            |
| **DMARC**    | `fail` — Domain policy failure                    |
| **Return-Path** | `support@paypaypal.net` — mismatched and suspicious |
| **Received From** | IP: `192.0.2.100` — Not a PayPal server       |

---

## 🧠 Conclusion

This email is a **phishing attempt** impersonating PayPal to trick users into revealing their credentials. It uses:

- **Spoofed headers**
- **Urgency tactics**
- **Deceptive URLs**
- **Lack of personalization**

---

## 📎 Screenshots

- 📩 Email Preview  
- 🛠️ Header Analyzer Results  
- 🧾 Raw Header Dump  

*(All located in the `screenshots/` folder)*

---

## ✅ Tools Used

- Google Header Analyzer: https://toolbox.googleapps.com/apps/messageheader/
- VirusTotal (for link inspection): https://www.virustotal.com/
- Raw header parsing (manual)

---

## 📁 Folder Structure

📁 phishing-email-paypal/
├── screenshots/
│ ├── email_preview.png
│ ├── header_analyser.png
│ └── raw_header.png
├── raw_header.txt
└── README.md
