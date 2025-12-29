# Junior Security Analyst Intro

Platform: TryHackMe  
Category: Defensive / SOC  
Difficulty: Easy  

---

## 1. Challenge Overview

This room simulated a basic workday of a Junior Security Analyst in a Security Operations Center (SOC).  
The focus was on understanding SOC roles, handling alerts, and following escalation procedures.  
It tested analyst mindset rather than technical exploitation.

---

## 2. Objective

The objective was to review security alerts, identify a malicious indicator, and take appropriate response actions following SOC workflow.

---

## 3. Environment & Tools Used

- Web-based SOC dashboard  
- Alert monitoring interface  
- Firewall action panel  

---

## 4. Step-by-Step Approach

I started by reviewing the alert dashboard to understand what type of activity was being reported.  
One of the alerts highlighted suspicious network traffic originating from a specific IP address.

I focused on identifying the malicious indicator first, as this is the primary task for a Level 1 analyst.  
The alert details clearly showed a source IP that had been flagged as malicious.

After confirming the IP, I followed the SOC workflow and escalated the alert to the senior analyst.  
This step is important because Junior Analysts do not make high-impact decisions alone.

Once approved, I blocked the malicious IP address using the firewall controls provided in the lab.

---

## 5. Key Finding / Vulnerability

The key issue was malicious traffic originating from a known bad IP address.  
The threat was detectable due to proper logging and alerting mechanisms.

This scenario highlighted how early detection depends on correctly configured monitoring tools.

---

## 6. Result

The malicious IP address was successfully identified, escalated, and blocked.  
The alert was resolved following proper SOC procedures.

---

## 7. Security Impact (Real-World Mapping)

If such malicious traffic is not detected or blocked in a real environment, it could lead to:
- Unauthorized access attempts  
- Malware communication with external servers  
- Further compromise of internal systems  

Early response helps prevent larger incidents.

---

## 8. Mitigation / Defensive Takeaway

- Maintain updated threat intelligence and IP reputation feeds  
- Ensure alerts are reviewed and escalated correctly  
- Follow role-based access and approval workflows in SOC operations  

---

## 9. Learning Outcome

- Understood the role of a Junior Security Analyst in a SOC  
- Learned basic alert triage and escalation flow  
- Gained exposure to real-world defensive decision-making  
