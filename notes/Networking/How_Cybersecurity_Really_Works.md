# How Cybersecurity Really Works

## Internet

International Protocol (IP)
Transmission Control Protocol (TCP)
Network Address Translation (NAT)

Cyber Kill Chain (CKC)

1. Reconnaissance
   - Sniffing
   - Scanning
2. Weaponization
3. Delivery
4. Exploitation
5. Installation
6. Control
7. Action

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
2. Things you have
   - e.g.
     - Common Access Card (CAC)
     - Digital certificate
     - Trusted Platform Module (TPM)
3. Things represent you
   - e.g. Biology signatures
     - False Rejection Rate (FRR)
     - False Accept Rate (FAR)
     - Cross-over Error Rate (CER)
4. Things you are doing
   - e.g. Completely Automated Public Turing test to tell Computers and Human Apart (CAPTHA)
5. Places you are

Authorization

1. Mandatory Access Control (MAC)
2. Rule-Based Access Control
3. Role-Based Access Control
   - Least privilege, separation of duties
4. Attribute-Based Access Control (ABAC)
5. Discretionary Access Control (DAC)
   e.g. Google Drive

Accounting

- Logging
- Audit
- Indicators of Attack (IoA)

## Network Trapping

Network tap
IP spoofing
Port mirroring
