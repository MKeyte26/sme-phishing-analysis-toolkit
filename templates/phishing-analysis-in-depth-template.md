# SME Phishing Analysis Report Template 

### Contents:

- Executive Summary/Scope
- In-Depth Phishing Analysis Template Report
- Sign Off Process


### Scope:

Many SME’s do not have access to a full security operations centre, security professionals/consultants, managed service provider with security responsibilities or have clearly defined internal security roles. This often arises from the huge financial constraints organisations operate under and may result in a lack of internal security knowledge surrounding cyber defence, security operations, cyber risk management or incident response. Many organisations only face this reality when they have unfortunately encountered a security breach. 

With 42% of UK small businesses and 67% of medium business reporting cyber breaches/attacks in the past year, there is a growing risk that organisations will experience a security breach. This is enhanced due to a growing risk of automated (AI/Bots) non-targeted attacks which scan the internet in search of known vulnerabilities and exploit automatically upon detection. Many business owners mistakenly downplay their risk of attack as they don’t believe they are big enough to be targeted or ask themselves ‘why would someone want to target us’, without realising the reality of non-targeted automated risk. Phishing is responsible for a majority of attacks (approx 85%) and remains one of the greatest risks to an organisation's security. 

With this risk in mind, and to help enhance SME cyber security defence, these templates provide both a brief and in-depth phishing analysis playbook for internal investigations/reports, depending on internal  IT skills and comfort using investigation tools. I have ensured this template remains vendor neutral (does not rely on specific operating systems or software) and can be conducted by any member of an IT team or someone comfortable using IT systems. 

### This investigation/report serves the following purposes:
- Assess risk of account/system compromise
- Identify post-compromise actions such as Isolate compromised accounts and prevent lateral movement/escalation
- Provide evidence of investigation to stakeholders/external bodies (ICO)
- Build internal security skills and enhance security awareness
- Provide detailed investigation notes which can be provided to specialist/security consultant in the event the organisation seeks help with incident response/business continuity post-compromise. 

This report is free to use and please adapt appropriately to your organisations needs. 


## In-Depth Phishing Analysis Template Report:

### 1. Basic Information
 
  | Incident ID:    |  |
  |-----------------|------------------|
  |Date of Analysis:|
  |Analyst Name:    |
  |Source:          |
  |Severity:        |

__________________________________________________________________________________________________________________

### 2. Email Overview
  | Subject:     |   |
  |--------------|------------------|
  |From (Header):|
  |To:           |
  |Reply-To:     |
  |Date Sent:    |

__________________________________________________________________________________________________________________

### 3. Social Engineering Techniques
  |Impersonation (brand/person):| |
  |-----------------------------|----------------|
  |Urgency (“act now”):         |             
  |Fear / consequence:          |
  |Incentive (reward / package / invoice): |

__________________________________________________________________________________________________________________

### 4. Header Analysis (IMF)
  |Return-Path:| |
  |------------|-----------------|
  |Received Chain (summarise origin IP/domain):|
  |SPF Result (Pass / Fail / Softfail):|
  |DKIM Result:|
  |DMARC Result:|

__________________________________________________________________________________________________________________

### 5. URL Analysis
  |Extracted URLs [DEFANGED (CyberChef)]:| |
  |--------------------------------------|----------------|
  |Root Domain:|
  |Reputation (VirusTotal):|
  |Domain Age:|
  |Domain unrelated to sender:|
  |Suspicious TLD (.xyz, .top, etc.):|

__________________________________________________________________________________________________________________

### 6. Attachment Analysis
  | File Name:| |
  |-----------|----------------|
  |File Type:|
  |Hash (SHA256):|
  |Encoding: (base64 / quoted-printable):|
  |Opened in sandbox - Any.run etc, (Yes/No):|
  |Behaviour observed:|
  |Malicious indicators:|

__________________________________________________________________________________________________________________

### 7. Infrastructure Analysis
  |Source IP:| |
  |----------|----------------|
  |Hosting provider:|
  |Geolocation:|

__________________________________________________________________________________________________________________

### 8. Indicators of Compromise (IOCs)
  |URL:| |
  |----|----------------|
  |Attachment:|
  |User interaction:|
  |Sites visited:|
  |Suspicious downloads:|
  |Other:|

__________________________________________________________________________________________________________________

### 9. Verdict

|Classification (Phishing / Malicious / Suspicious / Benign etc): | |
|-----------------------------------------------------------------|----------------|

__________________________________________________________________________________________________________________

### 10. Recommended Actions
  (Please document any recommended actions based on the completed analysis and verdict provided. 

1.
2.
3.

__________________________________________________________________________________________________________________

### 11. Lessons Learned
  (To be completed post-investigation once outcomes are successfully identified and lessons learned can be assessed.)

1.
2.
3.

__________________________________________________________________________________________________________________

### Sign Off: 

|               | Investigator/Analyst | Investigation Lead | Risk Owner/Security Lead | Board of directors/CEO/CISO |
|---------------|----------------------|--------------------|--------------------------|-----------------------------|
| Name          |
| Position/Role |
| Date          |

__________________________________________________________________________________________________________________
