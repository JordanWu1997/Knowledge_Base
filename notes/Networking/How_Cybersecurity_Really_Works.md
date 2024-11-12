# How Cybersecurity Really Works

## Internet

International Protocol (IP)
Transmission Control Protocol (TCP)
Network Address Translation (NAT)

Cyber Kill Chain (CKC)

1. Reconnaissance
   - Sniffing
   - Scanning
1. Weaponization
1. Delivery
1. Exploitation
1. Installation
1. Control
1. Action

Operation Security (OPSEC)

Network tools

- `ifconfig`
- `nslookup`
- `ping`
- `traceroute`

Shodan (shodan.io)
`dnf install shodan`
`shodan init <API>`
`shodan host <IP>`

## Phishing

Web Fishing

- Pharming
- Typosquatting

DNS Server

- Google: `8.8.8.8`
- Cloudflare: `1.1.1.1`

MX Toolbox (mxtoolbox.com)
Virus Total (virustotal.com)

Advanced Persistent Threat (APT)

## Malware

Malware

- Virus
  - Interact with users
- Worm
  - May not interact with users
- Trojan
  - Remote Acess Trojan (RAT)
- ## Ransomware/Spyware/Adware
- rootkit
  - Access root permission
- bootkit
  - Access boot logs
- Polymorphic malware

Anti-malware

- Detection
  - Signature
    - Code signature
  - Heuristic

## Password and Account Access

Identification

Authentication

1. Things you know
   - e.g. Cognitive password
1. Things you have
   - e.g.
     - Common Access Card (CAC)
     - Digital certificate
     - Trusted Platform Module (TPM)
1. Things represent you
   - e.g. Biology signatures
     - False Rejection Rate (FRR)
     - False Accept Rate (FAR)
     - Cross-over Error Rate (CER)
1. Things you are doing
   - e.g. Completely Automated Public Turing test to tell Computers and Human Apart (CAPTHA)
1. Places you are

Authorization

1. Mandatory Access Control (MAC)
1. Rule-Based Access Control
1. Role-Based Access Control
   - Least privilege, separation of duties
1. Attribute-Based Access Control (ABAC)
1. Discretionary Access Control (DAC)
   e.g. Google Drive

Accounting

- Logging
- Audit
- Indicators of Attack (IoA)

## Network Trapping

Network tap
IP spoofing
Port mirroring
