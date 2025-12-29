
# Forensics 101

Platform: CTFLearn  
Category: Forensics  
Difficulty: Easy  

---

## 1. Challenge Overview

This challenge provided an image file and suggested that the flag was hidden somewhere inside it.  
The task focused on basic file analysis rather than visual inspection.  
It tested fundamental forensic techniques used to inspect files beyond what is immediately visible.

---

## 2. Objective

The objective was to locate and extract the hidden flag from the provided image file.

---

## 3. Environment & Tools Used

- Linux terminal  
- strings command  
- steghide (checked, but not required)

---

## 4. Step-by-Step Approach

I started by opening the image normally to see if anything unusual was visible.  
Nothing suspicious appeared in the image itself, so I assumed the data might be hidden in the file content.

Next, I ran the `strings` command on the image file to extract readable text.  
This step is useful in forensics because files often contain embedded metadata or hidden messages.

The output from `strings` showed readable text that included the flag format, confirming that the data was directly embedded in the file.

I also checked the file using steganography tools, but they requested a passphrase and were not needed once the flag was found using basic analysis.

---

## 5. Key Finding / Vulnerability

The flag was stored in clear text within the image file.  
It was not encrypted or properly hidden, making it easily retrievable using simple forensic tools.

The issue was improper handling of sensitive data inside files.

---

## 6. Result

I successfully extracted the hidden flag from the image using basic string analysis.

---

## 7. Security Impact (Real-World Mapping)

If sensitive information is stored directly inside files without protection, it can be easily extracted.  
This could lead to data leaks, exposure of credentials, or disclosure of internal information.

---

## 8. Mitigation / Defensive Takeaway

- Avoid embedding sensitive data directly into files  
- Use encryption or secure storage mechanisms for confidential information  

---

## 9. Learning Outcome

- Learned how to analyze files beyond visual content  
- Gained hands-on experience using basic forensic tools  
- Improved understanding of how data can be unintentionally exposed  
