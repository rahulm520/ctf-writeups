# Character Encoding

Platform: CTFLearn  
Category: Cryptography  
Difficulty: Easy  

---

## 1. Challenge Overview

This challenge provided a sequence of values that did not look like readable text.  
The goal was to identify the encoding used and convert it back into human-readable form.  
It tested basic knowledge of character encoding formats.

---

## 2. Objective

The objective was to decode the given sequence of values and retrieve the hidden message.

---

## 3. Environment & Tools Used

- Linux terminal  
- Python (optional)  
- Command-line utilities  

---

## 4. Step-by-Step Approach

I started by looking at the format of the values provided.  
They were pairs of characters using numbers and letters from A to F, which suggested hexadecimal encoding.

Hexadecimal is commonly used to represent ASCII characters, so I assumed the values might map directly to text.

To verify this, I converted each hex value into its ASCII equivalent.  
I used a simple script and also validated the output using command-line tools.

Once converted, the output formed a readable string that followed a common CTF flag format.

---

## 5. Key Finding / Vulnerability

The data was not encrypted, only encoded in hexadecimal.  
Hex encoding is reversible and provides no security on its own.

The mistake here was relying on encoding instead of encryption to hide sensitive data.

---

## 6. Result

I successfully decoded the hex values into readable text and obtained the hidden message.

---

## 7. Security Impact (Real-World Mapping)

If sensitive data is only hex-encoded in a real system, anyone with basic knowledge can decode it.  
This could lead to exposure of credentials, tokens, or internal data.

---

## 8. Mitigation / Defensive Takeaway

- Do not rely on encoding methods to protect sensitive information  
- Use proper encryption for data that needs confidentiality  

---

## 9. Learning Outcome

- Improved understanding of hexadecimal and ASCII encoding  
- Learned how to quickly identify common encoding patterns  
- Reinforced the difference between encoding and encryption  
