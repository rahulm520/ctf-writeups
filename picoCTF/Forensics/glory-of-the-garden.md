# Glory of the Garden

Platform: picoCTF  
Category: Forensics  
Difficulty: Easy  

---

## 1. Challenge Overview

This challenge provided an image file that appeared normal at first glance.  
The task was to determine whether the file contained hidden data beyond its visual content.  
It tested basic file inspection and forensic analysis skills.

---

## 2. Objective

The objective was to analyze the image file and extract any hidden or embedded information.

---

## 3. Environment & Tools Used

- Linux terminal  
- xxd (hex dump utility)  

---

## 4. Step-by-Step Approach

I started by opening the image normally to check for any visible clues.  
Since nothing unusual was visible, I assumed the hidden data might exist at the file level rather than the image layer.

Because this was a forensics challenge, I inspected the raw contents of the file using a hex dump.  
Viewing the raw bytes helps identify embedded strings or encoded data that are not rendered visually.

After generating the hex output, I searched through it for recognizable patterns.  
CTF challenges often include identifiable text markers, so I looked for common strings associated with flags.

This search revealed an encoded string embedded within the file data.

---

## 5. Key Finding / Vulnerability

The image file contained readable data embedded directly within its raw bytes.  
This data was not encrypted and could be extracted using basic file inspection tools.

The issue was improper handling of sensitive information within a file.

---

## 6. Result

I successfully extracted an encoded string from the image file and decoded it to obtain the hidden message.

---

## 7. Security Impact (Real-World Mapping)

In real environments, embedding sensitive information directly inside files can lead to data leakage.  
Anyone with access to the file can extract such information using simple forensic techniques.

This can expose credentials, secrets, or internal identifiers.

---

## 8. Mitigation / Defensive Takeaway

- Avoid embedding sensitive data directly into files  
- Use encryption when storing confidential information  
- Validate files before sharing them externally  

---

## 9. Learning Outcome

- Learned how to inspect files beyond visual content  
- Improved understanding of hex-level file analysis  
- Reinforced the importance of secure data handling  

