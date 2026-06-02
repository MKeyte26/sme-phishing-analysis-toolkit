
# SME Phishing Analysis Report Template 

## Walkthrough Edition

### Contents:

- Executive Summary/Scope
- In-Depth Phishing Analysis Template Report
- Sign Off Process


### Scope:

Many SME’s do not have access to a full security operations centre, security professionals/consultants, managed service provider with security responsibilities or have clearly defined internal security roles. This often arises from the huge financial constraints organisations operate under and may result in a lack of internal security knowledge surrounding cyber defence, security operations, cyber risk management or incident response. Many organisations only face this reality when they have unfortunately encountered a security breach. 

With 42% of UK small businesses and 67% of medium business reporting cyber breaches/attacks in the past year, there is a growing risk that organisations will experience a security breach. This is enhanced due to a growing risk of automated (AI/Bots) non-targeted attacks which scan the internet in search of known vulnerabilities and exploit automatically upon detection. Many business owners mistakenly downplay their risk of attack as they don’t believe they are big enough to be targeted or ask themselves ‘why would someone want to target us’, without realising the reality of non-targeted automated risk. Phishing is responsible for a majority of attacks (approx 85%) and remains one of the greatest risks to an organisation's security. 

With this risk in mind, and to help enhance SME cyber security defence, these templates provide both a brief and in-depth phishing analysis playbook for internal investigations/reports, depending on internal  IT skills and comfort using investigation tools. I have ensured this template remains vendor neutral (does not rely on specific operating systems or software) and can be conducted by any member of an IT team or someone comfortable using IT systems. 

### The purpose of these investigations/reports are as follows:
- Assess risk of account/system compromise
- Identify post-compromise actions such as Isolate compromised accounts and prevent lateral movement/escalation
- Provide evidence of investigation to stakeholders/external bodies (ICO)
- Build internal security skills and enhance security awareness
- Provide detailed investigation notes which can be provided to specialist/security consultant in the event the organisation seeks help with incident response/business continuity post-compromise. 

This report is free to use and please adapt appropriately to your organisations needs. 


## Phishing Analysis Template Report:

### 1. Basic Information
 
  | Incident ID:    |  Enter Response: |
  |-----------------|------------------|
  |Date of Analysis:|
  |Analyst Name:    |
  |Source:          |
  |Severity:        |


> This section covers the basic information required to document the report. The incident number will follow any internal system and can be   as simple as ‘001’ or ‘CySec 01’. Ensure dates and names are accurate as this may be required as evidence for external stakeholders.

> The source of the incident can be from internal staff, external service users, endpoint detection & response software, anti-virus, security information and event management software. If this alert is not from specific security software and the severity is not known, please enter ‘not determined’, as this will be identified through the course of this investigation. 


### 2. Email Overview
  | Subject:     |  Enter Response: |
  |--------------|------------------|
  |From (Header):|
  |To:           |
  |Reply-To:     |
  |Date Sent:    |

> Before we begin investigating the finer details, we need to document the key pieces of information such as who sent the email, what it regards (subject), who received it and the dates this communication occurs as this may differ from the date of this report.

> Having an accurate timeline is an essential part of any cyber security investigation. 

### 3. Social Engineering Techniques
  |Impersonation (brand/person):| Response Here|
  |-----------------------------|--------------|
  |Urgency (“act now”):         |             
  |Fear / consequence:          |
  |Incentive (reward / package / invoice): |

> A good early indication that an email was a phishing attempt, can be identified from the style and context within.

> In this section we will assess known social engineering techniques such as impersonating known brands (email content, signatures, email name appearing to indicate a known brand), Urgency (anything asking the users to act immediately or applying pressure to act), fear/consequence (pushes the user to click as they are worried about facing consequences) and incentive (offering a false reward for user click/engagement).

> These are all signs of phishing attacks however it is too early in the investigation to make any verdict, we will use this evidence with information ascertained below to assess likelihood, impact and risk. 

### 4. Header Analysis (IMF)
  |Return-Path:| Response Here |
  |------------|---------------|
  |Received Chain (summarise origin IP/domain):|
  |SPF Result (Pass / Fail / Softfail):|
  |DKIM Result:|
  |DMARC Result:|

> This section focuses on analysing the email headers (technical metadata) to identify how the email was sent and whether it is legitimate. Attackers can spoof display names and email content, but cannot easily fake the full delivery path or authentication results.

> To begin, open the full email headers (often “view source” or “view original”). This will display multiple fields.
The Return-Path shows the actual sending address and may differ from the visible “From” address. If this appears unrelated or suspicious, note this. The Received Chain shows the route the email took. Read this from bottom to top and identify the original sending server (IP/domain). If this does not align with the claimed sender or appears unusual, this is a red flag.

> Review authentication results:
SPF: checks if the sender is authorised (fail/softfail = suspicious)
DKIM: checks email integrity (fail = suspicious)
DMARC: validates alignment (fail = strong indicator of phishing)

> A “pass” does not guarantee safety, as compromised accounts can still send phishing emails. Use this alongside other findings to assess risk.

### 5. URL Analysis
  Extracted URLs [DEFANGED (CyberChef)]:
  
  Root Domain:
  
  Reputation (VirusTotal):
  
  Domain Age:
  
  Domain unrelated to sender:
  
  Suspicious TLD (.xyz, .top, etc.):

```
This step takes us to our first look past the initial email view to gather additional details from the URL.
It is important to remember not to click anything in an email as this links cold all be dangerous, therefore we must follow a defang process (uses [.] throughout the link to render it un-clickable but still shows the original format as evidence.
Before we attempt this, we need to view the email source code (often right click and view source or in the email header bar). Copy this source to add into our URL/defang tool.
A great free tool for this is CyberChef, developed by GCHQ. This tool has a ‘Extract URL’ option in the left options bar and you can add a ‘Defang URL’ step which will provide all the urls from the email defanged.
From the results output, look for domain names and identify any unknown root domains. The root domain is typically the last two parts of the domain name (e.g. company.com or company.co.uk), and this is what determines whether a link is legitimate or malicious.

Another important free tool we can use, is VirusTotal.
For this we will paste in the normal URL identified, (not-defanged for this step) and press search. This will return the results of security vendors and help identify if there is a known risk for the email links.
For reference, no vendors flagging as malicious does not make it certain its not malicious, as it may be a new link/site compromise that has not yet been assessed/reassessed by security vendors. If multiple vendors have flagged as malicious or suspicious, this is a good indication that this may be a phishing attempt. 

Based on this information, we are going do use free tools such as ‘WHOIS lookup’ to identify the domain age. Search for the domain ‘company.co.uk' into the search bar and browse results for domain age.
A recently created age is a red flag however does not by itself determine phishing. Is the identified domain name matching the email content or sender details viewed in step 2? Finally we will also look at the domain to determine if there is an uncommon or suspicious top level domain (.xyz or .top etc rather than common TLD’s like .co.uk or .com). 
```

### 6. Attachment Analysis
  File Name:
  
  File Type:
  
  Hash (SHA256):
  
  Encoding: (base64 / quoted-printable):
  
  Opened in sandbox - Any.run etc, (Yes/No):
  
  Behaviour observed:
  
  Malicious indicators:

```
First we need to inspect the source code again to identify any attachments contained in the email.
If the email is base 64 encoded (random alphanumeric characters ending in = such as ‘aHR0cHM6Ly8=‘) we need to paste this into cyberchef select the decode base 64 option. The results will help us identify any hidden attachments.
We are now going to search the decoded email source code for tags such as Content-Type: application/pdf; name=“filename.pdf” or Content-Disposition: attachment; filename=“filename.pdf”. Red flags at this stage include double extensions (.pdf.exe), HTML attachments (.html), office docs with macros (.docm, xlsm).
The last extension is the file type, which we will record above. 

A really useful tool to identify what the attachment does, is called Any.Run.
This will open the attachment in a sandboxed environment to identify what it tries to do on a device, which will allow us to identify if it was malicious and if so what we should be looking for on our devices.
*An important point before attempting this stage, is that it relies on having a download of the attachment however we want to do this safely and not execute the file. If in doubt please skip this stage.
To download safely, we will copy the base64 from the view source for the attachment into CyberChef and safe the output as a file. We will then use this saved output to place into any.run.
Alternatively, if the email was attempting to direct to malicious links, we can copy the link (being very careful not to click) and place this into Any.Run to analyse what happens. Document your findings here, it will produce a report, you can download and save the report for evidence of investigation or to pass to security consultants. 
```

### 7. Infrastructure Analysis
  Source IP:
  
  Hosting provider:
  
  Geolocation:

```
This section focuses on analysing the underlying infrastructure used to send the email or host any associated links. Using the originating IP address identified in the header analysis or URL investigation, we can gather further intelligence about the source.
Search the IP address using publicly available tools (e.g. whois.com) to identify the hosting provider and approximate geolocation.
If the infrastructure is associated with known cloud providers (e.g. AWS, Azure), this does not automatically indicate legitimacy, as attackers frequently abuse trusted platforms. Compare the identified infrastructure with the expected origin of the sender.
For example, if an email claims to be from a UK organisation but originates from infrastructure hosted in an unrelated region, this may indicate suspicious activity.
```

### 8. Indicators of Compromise (IOCs)
  URL:
  
  Attachment:
  
  User interaction:
  
  Sites visited:
  
  Suspicious downloads:
  
  Other:

```
This section documents any Indicators of Compromise (IOCs) identified during the investigation.
IOCs are artefacts that provide evidence of potential malicious activity and are critical for both containment and further investigation.
Record any malicious or suspicious URLs, attachment hashes, domains, IP addresses, or behaviours identified in previous steps.
If a user has interacted with the email (e.g. clicked a link, entered credentials, downloaded a file), this must be clearly documented as it significantly increases the likelihood of compromise.
Where possible, identify any follow-on activity such as redirection to additional sites, unexpected downloads, or abnormal system behaviour. These indicators can be used to:
Search across systems for further impact
Block malicious infrastructure
Support escalation to security specialists

Accurate documentation of IOCs is essential for effective incident response and ongoing monitoring.
```

### 9. Verdict

  Classification (Phishing / Malicious / Suspicious / Benign etc): 

```
This section provides the final assessment of the email based on all evidence gathered throughout the investigation. The classification should consider a combination of social engineering indicators, header analysis, URL and attachment findings, and any observed user interaction.
Phishing: Strong indicators of deception with intent to obtain sensitive information or prompt malicious action
Malicious: Confirmed harmful content (e.g. malware delivery, credential harvesting, known malicious infrastructure)
Suspicious: Some indicators present but insufficient evidence to confirm malicious intent
Benign: No indicators of malicious or deceptive activity identified
Where a phishing or malicious classification is determined, this should trigger appropriate incident response actions, including containment, credential resets, and further investigation of affected systems.
Ensure the reasoning behind the classification is clearly documented, as this may be required for internal review or external reporting.
```

### 10. Recommended Actions
  (Please document any recommended actions based on the completed analysis and verdict provided. 

1.
2.
3.

```
Please read the dealing with compromise section if unsure how to proceed at this point.
If there is no evidence of compromise, please record any actions that would be helpful to support the team in future investigations, such as training, tabletop exercises, resources or additional tools/external support. 
```

### 11. Lessons Learned
  (To be completed post-investigation once outcomes are successfully identified and lessons learned can be assessed.)

1.
2.
3.

### Sign Off: 

|               | Investigator/Analyst | Investigation Lead | Risk Owner/Security Lead | Board of directors/CEO/CISO |
|---------------|----------------------|--------------------|--------------------------|-----------------------------|
| Name          |
| Position/Role |
| Date          |
