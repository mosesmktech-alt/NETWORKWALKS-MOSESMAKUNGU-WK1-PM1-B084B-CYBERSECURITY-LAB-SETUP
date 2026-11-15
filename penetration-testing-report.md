# PENETRATION TESTING REPORT
## FOOTPRINTING & NETWORK SCANNING PHASES

**W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS**

---

## REPORT INFORMATION

| Field | Details |
|---|---|
| **Pentester Name** | Moses Makungu |
| **Professional Title** | Cybersecurity Professional |
| **Program / Batch** | B082 - Networkwalks |
| **Date** | 17 August 2026 |
| **Modules Completed** | W2-PM1 (Multiple Kali Tools), W2-PM5 (Zenmap Scanning) |
| **Client / Target** | Networkwalks and my own local LAN network |
| **Permission Secured?** | Yes - subject to documented authorization and approved scope |
| **Phases Covered** | Phase 1: Reconnaissance & Footprinting; Phase 2: Scanning & Network Discovery |
| **Remaining Phases** | Phases 3-5: In Progress |

---

## TABLE OF CONTENTS

1. [Liability Disclaimer](#1-liability-disclaimer)
2. [Introduction](#2-introduction)
3. [Tools Used](#3-tools-used)
4. [Activities Performed](#4-activities-performed)
   - [4.1 Footprinting & Reconnaissance](#41-footprinting--reconnaissance)
   - [4.2 Network Scanning with Zenmap](#42-network-scanning-with-zenmap)
5. [Risk Analysis / Impact](#5-risk-analysis--impact)
6. [Recommendations](#6-recommendations)
7. [Conclusion](#7-conclusion)
8. [Evidence Collected](#8-evidence-collected)
9. [Author](#9-author)
10. [Project Information](#10-project-information)

---

## 1. LIABILITY DISCLAIMER

I have performed these activities only on systems and devices for which I had secured written permission or systems and devices that I own.

All materials presented in this report are intended for educational and research purposes only. This knowledge must not be used to engage in unauthorized activities or break the law.

The instructor, authors and Networkwalks are not responsible for any misuse of the information presented in this report. Every action taken using this knowledge remains the responsibility of the individual.

Unauthorized access to computer systems and networks may result in criminal charges, financial penalties, employment consequences and other legal repercussions.

All cybersecurity activities must be conducted within an approved scope and with appropriate authorization.

---

## 2. INTRODUCTION

This report covers footprinting the `networkwalks.com` domain using multiple Kali Linux tools (W2-PM1) and scanning my own local network with Zenmap (W2-PM5).

One module covers the footprinting phase, while the other covers the scanning phase. Together, these exercises demonstrate how information gathering progresses from collecting publicly available information to identifying active hosts on a network.

This report represents the Week 2 activities of my ongoing Cybersecurity and Ethical Hacking internship program at Networkwalks.

All commands were executed in Kali Linux for footprinting and on a Windows PC with Zenmap installed for network scanning.

The report documents the activities performed, commands used, observations made, screenshots collected as evidence and the potential security implications of the findings.

---

## 3. TOOLS USED

The following table lists the tools used during the practical exercises and their respective purposes.

| # | Tool | Platform | Purpose |
|:---:|---|---|---|
| 1 | Kali Linux | Linux | Operating system used for reconnaissance activities |
| 2 | WHOIS | Kali Linux | Retrieves publicly available domain registration information |
| 3 | WhatWeb | Kali Linux | Identifies website technologies, CMS platforms and plugins |
| 4 | Nslookup | Kali Linux | Resolves domain names into IP addresses using DNS |
| 5 | Curl (`-I`) | Kali Linux | Inspects HTTP response headers |
| 6 | Wafw00f | Kali Linux | Identifies Web Application Firewall technologies |
| 7 | DNSRecon | Kali Linux | Enumerates DNS records, including NS, MX, SPF and TXT |
| 8 | Zenmap | Windows | Performs network discovery and visualizes network topology |
| 9 | Windows CMD | Windows | Identifies local IP configuration and MAC addresses |

---

## 4. ACTIVITIES PERFORMED

### 4.1 FOOTPRINTING & RECONNAISSANCE

I performed reconnaissance against the `networkwalks.com` domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon.

Each tool was used to collect a different category of information about the target.

#### 4.1.1 WHOIS

I used WHOIS to obtain publicly available domain registration information and identify the domain's name servers.

The results provided information relating to domain registration and hosting infrastructure.

**Purpose:** Domain registration information gathering.

**Evidence:**

![WHOIS Results](screenshots/whois.png)

#### 4.1.2 WhatWeb

I used WhatWeb to identify technologies used by the website.

The results identified:

- WordPress 7.0.4
- WP Download Manager 3.3.58
- Other publicly exposed website technology information

**Purpose:** Website technology fingerprinting.

**Evidence:**

![WhatWeb Results](screenshots/whatweb.png)

#### 4.1.3 Nslookup

I used Nslookup to resolve the domain name into its corresponding IP address.

The observed result identified:

`192.232.216.135`

**Purpose:** DNS resolution and IP address identification.

**Evidence:**

![Nslookup Results](screenshots/nslookup.png)

#### 4.1.4 Curl

I used Curl with the `-I` option to inspect the HTTP response headers.

The results provided additional information about the web application and exposed the WordPress REST API endpoint:

`/wp-json/`

**Purpose:** HTTP response header inspection.

**Evidence:**

![Curl Results](screenshots/curl.png)

#### 4.1.5 Wafw00f

I used Wafw00f to determine whether a Web Application Firewall was protecting the website.

The observed result identified:

`ModSecurity (SpiderLabs)`

**Purpose:** Web Application Firewall identification.

**Evidence:**

![Wafw00f Results](screenshots/wafw00f.png)

#### 4.1.6 DNSRecon

I used DNSRecon to enumerate DNS records associated with the domain.

The results provided information relating to:

- Name servers (NS)
- Mail exchange records (MX)
- SPF records
- TXT records
- Service records (SRV)
- DNS infrastructure information

**Purpose:** DNS enumeration and infrastructure information gathering.

**Evidence:**

![DNSRecon Results](screenshots/dnsrecon.png)

---

### 4.2 NETWORK SCANNING WITH ZENMAP

For the second activity, I used Zenmap to perform network discovery on my local network.

The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.

#### Step 1: Identify Local Network Configuration

I first used the Windows `ipconfig` command to identify my local IP address and LAN subnet.

```cmd
ipconfig
```

This provided information about the local network configuration.

#### Step 2: Perform Network Discovery

I entered the identified subnet into Zenmap and selected the Ping Scan option to discover active hosts.

The example results provided in the practical identified the following four live hosts:

| # | IP Address |
|:---:|---|
| 1 | 10.0.0.1 |
| 2 | 10.0.0.4 |
| 3 | 10.0.0.19 |
| 4 | 10.0.0.5 |

The example results also included four corresponding MAC addresses.

**Note:** These are example results from the practical. They should not be presented as actual personal network discoveries unless independently verified.

#### Step 3: Generate Network Topology

After completing the scan, I opened the Topology section in Zenmap, enabled the legend and saved the network topology in PDF format as required by the practical task.

**Evidence:**

![Zenmap Network Scan](screenshots/zenmap-scan.png)

**Network Topology:**

[View Network Topology PDF](topology/network-topology.pdf)

---

## 5. RISK ANALYSIS / IMPACT

Based on the information collected during the footprinting and network scanning activities, I identified the following potential security risks.

| # | Risk / Finding | Evidence / Observation | Potential Impact | Risk Level |
|:---:|---|---|---|:---:|
| 1 | Web technology information exposed | WhatWeb identified WordPress and WP Download Manager | Attackers may use exposed technology information to identify software requiring further security review | Medium |
| 2 | Server IP address identifiable | Nslookup resolved the domain to 192.232.216.135 | Provides information about the network location of the web service | Low |
| 3 | HTTP technical information exposed | Curl returned HTTP response headers and exposed `/wp-json/` | May assist technology fingerprinting and further enumeration | Low |
| 4 | WAF technology identifiable | Wafw00f identified ModSecurity (SpiderLabs) | Reveals information about the web application's security architecture | Low |
| 5 | DNS infrastructure information exposed | DNSRecon identified DNS, mail and service-related records | DNS information can help build a broader infrastructure profile | Medium |
| 6 | Multiple live hosts visible on local network | Zenmap identified four hosts in the example network | Unknown or unauthorized devices may potentially be present on a network | Medium |

### Risk Level Classification

| Risk Level | Description |
|---|---|
| Critical | Immediate security attention required |
| High | Significant security concern requiring prompt review |
| Medium | Requires investigation, review and monitoring |
| Low | Limited potential impact but should still be monitored |

The risks above are observations from the footprinting and scanning exercises, not confirmed vulnerabilities.

The practical exercises primarily involved information gathering and host discovery. No exploitation or vulnerability validation was performed as part of these two modules.

Therefore, the presence of information such as a software version, IP address or DNS record does not automatically mean that a system is vulnerable. Further authorized security testing would be required to confirm any actual vulnerability.

---

## 6. RECOMMENDATIONS

Based on the observations from these activities, I recommend the following security improvements:

### 6.1 Review Publicly Exposed Technology Information

Organizations should regularly review what information about their web technologies, CMS platforms and plugins is publicly visible.

### 6.2 Keep Software Updated

CMS platforms, plugins and other web technologies should be regularly updated and reviewed against current security advisories.

### 6.3 Review HTTP Headers

HTTP response headers should be reviewed to determine whether unnecessary technical information is being exposed.

### 6.4 Review DNS Records Regularly

DNS records should be checked periodically to ensure that only required information and services are publicly exposed.

### 6.5 Properly Configure and Monitor the WAF

Keep the Web Application Firewall (ModSecurity) enabled, properly configured and monitored to help protect web applications against malicious traffic.

### 6.6 Perform Regular Internal Network Discovery

Organizations should periodically scan their own networks to identify active devices and maintain an accurate inventory.

### 6.7 Investigate Unknown Devices

Any unexpected device discovered during network scanning should be investigated and verified.

### 6.8 Maintain Network Documentation

Network topology, device information and network configurations should be documented and updated regularly.

### 6.9 Perform Security Testing with Authorization

Reconnaissance and scanning should only be performed against systems and networks where appropriate authorization has been provided.

---

## 7. CONCLUSION

During Week 2 of my Cybersecurity and Ethical Hacking internship, I completed practical activities covering footprinting, reconnaissance and network scanning.

In the footprinting activity, I used six Kali Linux tools to collect information about the target domain.

I learned how:

- WHOIS provides publicly available domain registration information.
- WhatWeb identifies website technologies.
- Nslookup resolves domain names into IP addresses.
- Curl inspects HTTP response headers.
- Wafw00f identifies Web Application Firewall technologies.
- DNSRecon provides additional DNS infrastructure information.

In the network scanning activity, I used Zenmap to identify local network configurations and discover active hosts. I also worked with IP and MAC address identification and network topology visualization.

The exercises demonstrated that information gathering is an important part of cybersecurity. Even before attempting to exploit a system, a security professional can learn a significant amount about an environment by carefully analyzing publicly available information and network responses.

I also learned that technical findings should be documented clearly. A good cybersecurity report should explain what was performed, what was discovered, what the observation means, what risk it may create and what can be done to reduce that risk.

Finally, I learned that reconnaissance and scanning must always be performed within an authorized scope. These activities were completed as part of the assigned educational cybersecurity lab.

---

## 8. EVIDENCE COLLECTED

The following evidence directory contains screenshots and supporting documents collected during the practical exercises.

| # | Evidence | Description | File |
|:---:|---|---|---|
| 1 | WHOIS | Domain registration information | `screenshots/whois.png` |
| 2 | WhatWeb | Website technology fingerprinting | `screenshots/whatweb.png` |
| 3 | Nslookup | Domain IP resolution | `screenshots/nslookup.png` |
| 4 | Curl | HTTP response headers | `screenshots/curl.png` |
| 5 | Wafw00f | WAF identification | `screenshots/wafw00f.png` |
| 6 | DNSRecon | DNS enumeration results | `screenshots/dnsrecon.png` |
| 7 | Zenmap | Network discovery results | `screenshots/zenmap-scan.png` |
| 8 | Network Topology | Generated network topology | `topology/network-topology.pdf` |

### Screenshot Gallery

#### WHOIS Results
![WHOIS Evidence](screenshots/whois.png)

#### WhatWeb Results
![WhatWeb Evidence](screenshots/whatweb.png)

#### DNSRecon Results
![DNSRecon Evidence](screenshots/dnsrecon.png)

#### Zenmap Network Scan
![Zenmap Evidence](screenshots/zenmap-scan.png)

**Evidence Note:** Replace the image placeholders with your actual screenshots before publishing the repository. GitHub will display images when the referenced files exist at the specified paths.

---

## 9. AUTHOR

**Moses Makungu**  
Cybersecurity Professional  
Program / Batch: B084 - Networkwalks

**LinkedIn:** [Add your LinkedIn profile URL here](https://www.linkedin.com/)

---

## 10. PROJECT INFORMATION

| Field | Details |
|---|---|
| **Program Name** | Cybersecurity Program at Networkwalks |
| **Week** | 02 |
| **Project** | Penetration Testing Report |
| **Modules** | W2-PM1 and W2-PM5 |
| **Focus Areas** | Footprinting, Reconnaissance and Network Scanning |
| **Operating Systems** | Kali Linux and Windows |
| **Documentation Platform** | GitHub |

---

**END OF REPORT**


-curl.png

*Cybersecurity | Ethical Hacking | Network Security | Continuous Learning*
