# 🔍 VirusTotal Bulk Hash Scanner

A Python-based automation tool designed for SOC Analysts and Incident Responders to perform bulk reputation checks against the **VirusTotal V3 API**.



## 🎯 Overview
Manually checking multiple file hashes during an investigation is time-consuming. This script automates the process by reading a list of MD5, SHA-1, or SHA-256 hashes from a text file and retrieving their reputation scores, providing a quick summary of malicious detections.

## 🚀 Key Features
* **V3 API Integration:** Leverages the latest VirusTotal API for faster and more detailed reports.
* **Bulk Processing:** Efficiently handles multiple hashes in a single execution.
* **Clean Output:** Displays the "Malicious" vs. "Undetected" count directly in the console for rapid triage.
* **Error Handling:** Robust management of API connection issues and invalid hash formats.

## 🛠️ Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/0W3RTY/virustotalsearches.git](https://github.com/0W3RTY/virustotalsearches.git)
   cd virustotalsearches
