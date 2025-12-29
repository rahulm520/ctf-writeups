# Memory Forensics

Platform: TryHackMe  
Category: Forensics  
Difficulty: Medium  

---

## 1. Challenge Overview

This challenge involved analyzing a memory dump from a Windows system.  
The goal was to extract sensitive information that was present only in system memory.  
It tested practical memory forensics skills and understanding of volatile artifacts.

---

## 2. Objective

The objective was to analyze the memory dump to identify:
- User credentials
- Command-line activity
- System shutdown time
- Encryption passphrases stored in memory

---

## 3. Environment & Tools Used

- TryHackMe AttackBox  
- Volatility  
- Memory dump file (VMEM)

---

## 4. Step-by-Step Approach

I started by loading the memory dump into Volatility and identifying the correct profile.  
This step is necessary to ensure that memory structures are parsed correctly.

First, I focused on credential-related artifacts.  
Memory often contains plaintext or recoverable credentials due to active processes or cached authentication data.

Next, I analyzed command-line history and console-related artifacts.  
This helped determine what actions were being performed by the user before the system was shut down.

To build a timeline, I checked system metadata to identify when the machine was last powered off.  
This is useful for correlating user activity with system events.

Finally, I searched for evidence of encryption software usage.  
Since encrypted containers were suspected, I examined memory for any readable passphrases related to disk encryption.

---

## 5. Key Finding / Vulnerability

Sensitive information such as passwords and encryption passphrases were present in system memory.  
This occurs because memory contents are not automatically wiped and can retain data from running applications.

The core issue was reliance on encryption without considering memory exposure.

---

## 6. Result

I successfully recovered:
- The user’s login password  
- Command-line input entered by the user  
- The last system shutdown timestamp  
- The passphrase for an encrypted TrueCrypt volume  

---

## 7. Security Impact (Real-World Mapping)

In a real incident, exposed memory artifacts could allow:
- Credential compromise  
- Access to encrypted data  
- Reconstruction of user activity  

Memory analysis can completely bypass disk-level encryption if secrets remain in RAM.

---

## 8. Mitigation / Defensive Takeaway

- Use full disk encryption with proper system shutdown policies  
- Disable unnecessary credential caching  
- Implement memory protection and secure endpoint configurations  
- Restrict access to memory dump files  

---

## 9. Learning Outcome

- Learned how volatile memory can expose sensitive data  
- Gained hands-on experience using Volatility  
- Improved understanding of post-compromise forensic investigation  
