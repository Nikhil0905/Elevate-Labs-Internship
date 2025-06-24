# 🛡️ Task 2: Phishing Email Analysis
Date: 24th June, 2025

**Task Objective:**  
Analyze a suspicious email and identify phishing indicators using header analysis and content inspection.

---

## 📩 Sample Phishing Email

From: Amazon Security security-update@amaz0n-support.com
To: aman2025@gmail.com
Subject: Important: Password Change Required Immediately

Dear Amazon Customer,

As part of our ongoing efforts to ensure your account's safety, we have detected unusual login attempts from a new device on your Amazon account.

To prevent any unauthorized access, we require you to verify your identity and update your account password immediately.

Please follow the link below to confirm your identity and set a new password:

🔐 Secure Password Update Portal:
https://amazon-security.com/verify/account

Failure to act within 24 hours will result in a temporary suspension of your account for security reasons.

Sincerely,
Amazon Account Protection Team

---

## 🔍 Phishing Indicators in Email Content

| Indicator                   | Observed | Description |
|----------------------------|----------|-------------|
| **Spoofed Sender Address** | ✅       | Domain `amaz0n-support.com` mimics `amazon.com` using a zero (`0`) |
| **Urgent Language**        | ✅       | Threatens account suspension within 24 hours |
| **Suspicious Link**        | ✅       | `amazon-security.com` is not an official Amazon domain |
| **Generic Greeting**       | ✅       | Uses “Dear Amazon Customer” instead of a real name |
| **Unusual Domain**         | ✅       | Domain does not match Amazon’s infrastructure |
| **Grammatical Clues**      | ⚠️       | No clear errors, but content is very templated |
| **No Digital Signature**   | ✅       | SPF, DKIM, and DMARC validation all failed |

---

## 🧠 Key Concepts Demonstrated

- **Email Spoofing**
- **Social Engineering (Urgency & Threats)**
- **Link-Based Phishing**
- **Email Header Inspection**
- **SPF/DKIM/DMARC Verification**

---

## 🧪 Email Header Analysis

### **Header Summary**

| Field            | Value |
|------------------|-------|
| **Message ID**   | `<XJ293810234809124@amaz0n-support.com>` |
| **Created At**   | 23 June 2025, 10:12 PM GMT+5:30 |
| **Delivered At** | 23 June 2025, 10:14:31 PM GMT+5:30 |
| **Delay**        | 3 minutes |
| **From**         | Amazon Security `<security-update@amaz0n-support.com>` |
| **To**           | aman2025@gmail.com |
| **Subject**      | Important: Password Change Required Immediately |
| **Mailer**       | PHP/7.2.24 |

---

### **Relay & Delivery Path**

| Hop | Delay | From                | To             | Protocol | Time Received (UTC)           | Blacklist |
|-----|-------|---------------------|----------------|----------|-------------------------------|-----------|
| 1   | 0s    | smtp.fakehost.com (91.123.45.67) | mx.google.com | ESMTPS   | 23 June 2025, 04:44:31 PM UTC | Not blacklisted |

---

### **SPF/DKIM/DMARC Analysis**

| Check       | Result |
|-------------|--------|
| SPF         | ❌ Fail – IP not authorized |
| DKIM        | ❌ Fail |
| DMARC       | ❌ Fail |
| Return-Path | `<spoofed@malicious-domain.com>` |

---

### **Raw Header Sample (Extracted)**

Return-Path: spoofed@malicious-domain.com
Received: from smtp.fakehost.com (smtp.fakehost.com. [91.123.45.67])
by mx.google.com with ESMTPS id d23si1011131qtc.212.2025.06.23.09.44.31
for aman2025@gmail.com
(version=TLS1_3 cipher=TLS_AES_256_GCM_SHA384);
Mon, 23 Jun 2025 09:44:31 -0700 (PDT)
Received-SPF: Fail (google.com: domain of amaz0n-support.com does not designate 91.123.45.67 as permitted sender)
Authentication-Results: spf=fail dkim=fail dmarc=fail
Message-ID: XJ293810234809124@amaz0n-support.com
Date: Mon, 23 Jun 2025 09:42:00 -0700
MIME-Version: 1.0
Content-Type: text/html; charset="UTF-8"
X-Mailer: PHP/7.2.24

---

## 🧾 Conclusion

This phishing email is a well-crafted spoof attempting to trick the user into clicking a malicious link by creating **urgency and fear**. The **sender's domain**, **link**, and **failed authentication checks** confirm it is not from a legitimate source.

**Skills practiced:**
- Email header dissection
- Threat identification
- Basic forensic investigation of a phishing attempt

---

## 🔗 Tools Used

- [Google Admin Toolbox – Header Analyzer](https://toolbox.googleapps.com/apps/messageheader/)
- [MXToolbox Email Header Parser](https://mxtoolbox.com/EmailHeaders.aspx)
- [VirusTotal Link Scanner](https://www.virustotal.com/)
- Manual HTML and header review

---
## 📩 Submission & Instructions

Please refer to the official task PDF for the **submission link**.  
This repository only contains the completed work and relevant documentation.

> **Note:** Interview questions mentioned in the PDF have been prepared separately and are not part of this submission, as instructed.

---

## 🙌 Closing Remarks

This task simulated a real-world security assessment scenario and was completed with careful attention to process, accuracy, and documentation. I’ve also explored multiple angles of data analysis and traffic behavior to provide a comprehensive solution.

---
