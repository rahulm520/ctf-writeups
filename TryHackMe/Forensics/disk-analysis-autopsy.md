# Disk Analysis & Autopsy

Platform: TryHackMe  
Category: Forensics  
Difficulty: Medium  

---

## 1. Challenge Overview

This challenge involved investigating a Windows 10 disk image using Autopsy.  
The task focused on manual forensic analysis of system artifacts rather than automated exploitation.  
It tested understanding of disk forensics, user activity, and system-level evidence.

---

## 2. Objective

The objective was to analyze the disk image and extract forensic artifacts such as:
- User accounts and login activity  
- Network configuration details  
- Installed tools and suspicious files  
- Evidence of privilege escalation and misuse  

---

## 3. Environment & Tools Used

- TryHackMe AttackBox  
- Autopsy  
- Windows disk image (E01 format)

---

## 4. Step-by-Step Approach

I started by loading the provided Autopsy case file and re-pointing it to the disk image.  
Since ingest modules were already completed, I focused on manual review of artifacts.

First, I verified the integrity of the image by checking the MD5 hash.  
This step is important to ensure the evidence has not been altered.

Next, I reviewed system information to identify the computer name, network configuration, and hardware details.  
This helped establish the environment in which the activity occurred.

I then examined user accounts and login records to determine who had access to the system and who logged in most recently.  
This is a common step in incident investigations to establish user timelines.

After that, I analyzed installed applications and user files.  
This led to identifying password-focused hacking tools and evidence of privilege escalation activity.

I also reviewed browser artifacts and bookmarks, which revealed a saved Google Maps location.  
Desktop files and wallpapers were inspected to identify user attribution.

Finally, I examined scripts and archives related to known exploits and inspected a YARA rule file to identify its author.

---

## 5. Key Finding / Vulnerability

The system showed clear evidence of misuse, including:
- Presence of credential-dumping tools  
- Privilege escalation activity  
- Exploit-related archives targeting domain controllers  

The root issue was lack of system hardening and monitoring, allowing tools and exploits to exist undetected.

---

## 6. Result

I successfully extracted all required forensic artifacts, including:
- User and login details  
- Network configuration  
- Evidence of credential access tools  
- Indicators of exploitation and privilege escalation  

---

## 7. Security Impact (Real-World Mapping)

In a real environment, these findings could indicate:
- Credential compromise  
- Unauthorized privilege escalation  
- Potential lateral movement within a network  

If not detected early, this could lead to full domain compromise.

---

## 8. Mitigation / Defensive Takeaway

- Monitor endpoints for credential access tools  
- Restrict administrative privileges  
- Enable logging and alerting for privilege escalation attempts  
- Perform regular forensic readiness checks  

---

## 9. Learning Outcome

- Gained hands-on experience with disk forensics using Autopsy  
- Learned how to correlate user activity with system artifacts  
- Improved understanding of post-compromise investigation techniques  
