import requests
import time
import os
import base64

# --- CONFIGURATION ---
API_KEY = "YOUR_API_KEY_HERE"  # Replace with your VirusTotal API Key
INPUT_FILE = "indicators.txt"    # File containing hashes, IPs, or URLs (one per line)
# ---------------------

def get_vt_report(indicator, api_key):
    """
    Fetches the reputation report from VirusTotal V3 API.
    Supports IPs, URLs, and File Hashes.
    """
    headers = {"x-apikey": api_key}
    
    # Indicator type detection logic
    if "." in indicator and not indicator.startswith("http"):
        # Indicator is an IP Address
        url = f"https://www.virustotal.com/api/v3/ip_addresses/{indicator}"
    elif indicator.startswith("http"):
        # Indicator is a URL (requires base64 padding removal for VT API)
        url_id = base64.urlsafe_b64encode(indicator.encode()).decode().strip("=")
        url = f"https://www.virustotal.com/api/v3/urls/{url_id}"
    else:
        # Indicator is a Hash (MD5, SHA1, SHA256)
        url = f"https://www.virustotal.com/api/v3/files/{indicator}"

    try:
        response = requests.get(url, headers=headers)
        if response.status_code == 200:
            return response.json()
        elif response.status_code == 429:
            print(f"[!] Quota exceeded. Waiting 15s...")
            time.sleep(15)
            return get_vt_report(indicator, api_key)
        elif response.status_code == 404:
            return "NOT_FOUND"
        else:
            return f"ERROR_{response.status_code}"
    except Exception as e:
        return f"EXCEPTION_{str(e)}"

def main():
    if not os.path.exists(INPUT_FILE):
        print(f"[!] Error: {INPUT_FILE} not found. Please create it first.")
        return

    print(f"--- VirusTotal Multi-Indicator Scanner ---")
    
    # Load indicators from file
    with open(INPUT_FILE, "r") as f:
        indicators = [line.strip() for line in f if line.strip()]

    for item in indicators:
        print(f"[*] Analyzing: {item}...", end="\r")
        report = get_vt_report(item, API_KEY)

        if isinstance(report, dict):
            # Extract analysis statistics
            stats = report['data']['attributes']['last_analysis_stats']
            malicious = stats['malicious']
            total = sum(stats.values())
            
            status = "🚨 MALICIOUS" if malicious > 0 else "✅ CLEAN"
            # Clear line and print result
            print(f"[{status}] {item} -> Detections: {malicious}/{total}    ")
        elif report == "NOT_FOUND":
            print(f"[-] {item} -> Not found in VirusTotal database.      ")
        else:
            print(f"[?] {item} -> Error: {report}                          ")

        # Rate limiting: 4 requests per minute for free API tier
        time.sleep(15)

if __name__ == "__main__":
    main()
