# Morse Code Decoding

Platform: CTFLearn  
Category: Cryptography  
Difficulty: Easy  

---

## 1. Challenge Overview

This challenge provided a long sequence of dots and dashes representing an encoded message.  
The task was to recognize the encoding format and convert it into readable text.  
It tested basic pattern recognition and understanding of Morse code.

---

## 2. Objective

The objective was to decode the Morse code message and identify the hidden text.

---

## 3. Environment & Tools Used

- Browser  
- Online Morse code translator  
- Linux terminal (optional)

---

## 4. Step-by-Step Approach

I started by visually inspecting the input data.  
The repeated dots and dashes separated by spaces strongly suggested Morse code.

Because Morse code is a standard encoding, I decided to translate it into plain text.  
I used a Morse code converter to decode the sequence.

After decoding, I reviewed the output to ensure it formed a readable message and checked for any invalid or extra characters.

---

## 5. Key Finding / Vulnerability

The message was only encoded using Morse code and not protected in any secure way.  
Morse code is a simple encoding method that can be decoded easily.

The main issue was relying on encoding instead of encryption to hide information.

---

## 6. Result

I successfully decoded the Morse code into readable text that revealed the intended message.

---

## 7. Security Impact (Real-World Mapping)

If sensitive information is shared using simple encodings like Morse code, it can be easily decoded by anyone.  
This could result in information disclosure if used in real communication systems.

---

## 8. Mitigation / Defensive Takeaway

- Do not rely on basic encodings to protect sensitive data  
- Use proper encryption methods for confidential communication  

---

## 9. Learning Outcome

- Improved ability to recognize common encoding patterns  
- Gained hands-on experience decoding Morse code  
- Reinforced the importance of encryption over encoding  

