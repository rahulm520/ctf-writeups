# Nmap Live Host Discovery

Platform: TryHackMe  
Category: Networking / Reconnaissance  
Difficulty: Easy  

---

## 1. Challenge Overview

This room focused on discovering which systems are online within a network.  
It covered how Nmap uses different protocols to identify live hosts before port scanning.  
The goal was to understand host discovery logic rather than scanning services.

---

## 2. Objective

The objective was to identify live hosts on a network using multiple discovery techniques such as ARP, ICMP, TCP, and UDP.

---

## 3. Environment & Tools Used

- TryHackMe AttackBox  
- Nmap  
- Network simulation interface  

---

## 4. Step-by-Step Approach

I started by understanding why host discovery is performed before port scanning.  
Scanning offline systems wastes time and creates unnecessary network noise.

First, I explored ARP-based discovery.  
When scanning systems on the same subnet, ARP requests were used to identify live hosts based on MAC address responses.

Next, I tested ICMP-based discovery methods.  
ICMP Echo, Timestamp, and Address Mask requests were used to check which hosts responded.  
Some ICMP methods returned no results, which showed how firewalls or host settings can block specific packet types.

After that, I used TCP-based discovery.  
By sending TCP SYN and TCP ACK packets to common ports, I could infer host availability based on responses, even when ICMP was blocked.

Finally, I tested UDP-based discovery.  
Closed UDP ports triggered ICMP “port unreachable” responses, indirectly confirming that the host was online.

Throughout the process, I compared the results of each method to understand their reliability and limitations.

---

## 5. Key Finding / Vulnerability

Different host discovery methods produce different results depending on network configuration and firewall rules.  
Relying on a single technique can lead to missed hosts.

The main weakness highlighted was assuming ICMP alone is sufficient for network discovery.

---

## 6. Result

I successfully identified live hosts on the network using multiple Nmap discovery techniques.  
Each method provided partial visibility, and combining them gave a more accurate result.

---

## 7. Security Impact (Real-World Mapping)

In real environments, improper host discovery can lead to:
- Missed compromised systems  
- Incomplete asset visibility  
- Ineffective incident response  

Defenders and attackers both rely on accurate host discovery to understand network exposure.

---

## 8. Mitigation / Defensive Takeaway

- Use multiple detection and monitoring methods for asset discovery  
- Do not rely solely on ICMP for network visibility  
- Maintain accurate asset inventories and monitoring  

---

## 9. Learning Outcome

- Understood how different protocols reveal live hosts  
- Learned when and why specific Nmap discovery options are used  
- Improved network reconnaissance and analysis skills  

