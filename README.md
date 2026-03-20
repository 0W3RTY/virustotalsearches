# 🔍 VirusTotal Bulk Hash Scanner

A Python-based automation tool designed for SOC Analysts and Incident Responders to perform bulk reputation checks against the **VirusTotal V3 API**.



## 🎯 Overview
Manually checking multiple file hashes during an investigation is time-consuming. This script automates the process by reading a list of IOC like MD5, SHA-1, or SHA-256 hashes, Urls, IPs, etc... from a text file and retrieving their reputation scores, providing a quick summary of malicious detections.

## 🚀 Key Features
* **V3 API Integration:** Leverages the latest VirusTotal API for faster and more detailed reports.
* **Bulk Processing:** Efficiently handles multiple hashes in a single execution.
* **Clean Output:** Displays the "Malicious" vs. "Undetected" count directly in the console for rapid triage.
* **Error Handling:** Robust management of API connection issues and invalid hash formats.

## 🛠️ Installation & Setup

1. **Clone the repository:**
   
````bash
   git clone [https://github.com/0W3RTY/virustotalsearches.git](https://github.com/0W3RTY/virustotalsearches.git)
   cd virustotalsearches
````

2. **Install Dependencies:**

 ````Bash
pip install requests
````

3. **Configure API Key:**
Replace the placeholder in the script with your personal VirusTotal API key:


Python**
  ````  
api_key = "YOUR_API_KEY_HERE"
 ````

## 📖 Usage

1.- **Create a file named indicators.txt in the root directory.**

2.- **Add your indicators (one per line). Example:**

````
8.8.8.8
[https://suspicious-site.com](https://suspicious-site.com)
e5081c7944263e55179248439365c197
Run the script:
````

3.- **Run the script:**

````
python virustotal_v3.py
````

## 📊 Example Output

````
Plaintext
[+] Searching hash: e5081c79...
[!] Detections: 45 / 72 (MALICIOUS)
[+] Searching hash: d41d8cd9...
[-] Detections: 0 / 72 (CLEAN)
````

## 🎯 MITRE ATT&CK Context
This tool supports the Resource Development tactic, specifically Stage Capabilities (T1608), by allowing defenders to quickly identify known malicious tools used by adversaries.

Author: 0W3RTY
