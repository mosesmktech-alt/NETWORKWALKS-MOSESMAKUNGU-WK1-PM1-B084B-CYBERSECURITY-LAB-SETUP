## 5. Risk Analysis / Impact Assessment

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|:--:|---|---|---|:--:|
| 1 | Web Technology Information Exposed | WhatWeb identified WordPress and WP Download Manager | May help attackers identify software versions requiring security review | Medium |
| 2 | Server IP Address Identifiable | Nslookup resolved the domain to 192.232.216.135 | Provides information about the hosting infrastructure | Low |
| 3 | HTTP Technical Information Exposed | Curl identified HTTP response headers and the REST API endpoint | May assist further technology fingerprinting | Low |
| 4 | WAF Technology Identifiable | Wafw00f identified ModSecurity (SpiderLabs) | Reveals information about the website's security architecture | Low |
| 5 | DNS Infrastructure Information Exposed | DNSRecon identified DNS, mail and service records | May assist infrastructure profiling | Medium |
| 6 | Multiple Live Hosts Discovered | Zenmap identified four example local network hosts | Unknown devices may require investigation | Medium |

**Risk Level Classification:**
- Critical: Immediate security attention required.
- High: Significant security concern.
- Medium: Requires review and monitoring.
- Low: Limited potential impact.

- ## 3. Tools Used

| # | Tool | Operating System | Purpose |
|:--:|---|---|---|
| 1 | WHOIS | Kali Linux | Domain registration lookup |
| 2 | WhatWeb | Kali Linux | Website technology fingerprinting |
| 3 | Nslookup | Kali Linux | DNS resolution |
| 4 | Curl | Kali Linux | HTTP header inspection |
| 5 | Wafw00f | Kali Linux | Web Application Firewall detection |
| 6 | DNSRecon | Kali Linux | DNS enumeration |
| 7 | Zenmap | Windows | Network discovery and scanning |
| 8 | Windows CMD | Windows | Local IP and MAC identification |
