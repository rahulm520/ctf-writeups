# Surfing the Waves

Platform: picoCTF  
Category: Forensics  
Difficulty: Easy  

---

## 1. Challenge Overview

This challenge provided an audio file instead of a typical document or image.  
The task was to analyze the audio data to determine if it contained hidden information.  
It tested basic audio forensics and data extraction skills.

---

## 2. Objective

The objective was to inspect the audio file and extract the hidden flag embedded within it.

---

## 3. Environment & Tools Used

- Audio editor (Audacity)  
- Python  
- Basic scripting libraries  

---

## 4. Step-by-Step Approach

I started by listening to the audio file and visually inspecting it in an audio editor.  
After increasing the volume and waveform visibility, I noticed unusual repeating patterns that did not resemble normal audio signals.

Because visual inspection alone was not enough, I decided to analyze the raw audio data.  
I extracted the numerical values representing the audio samples and reviewed them programmatically.

While reviewing the data, I noticed that the values followed a repeated structure.  
After removing minor noise from the values, only a small set of unique numbers remained.

The number of unique values matched the number of characters used in hexadecimal encoding.  
This suggested that the audio samples were encoding hexadecimal data.

---

## 5. Key Finding / Vulnerability

The audio file was not purely sound data.  
It contained structured numerical values that represented encoded information.

The data was hidden through obfuscation rather than encryption, making it reversible with basic analysis.

---

## 6. Result

I successfully reconstructed the encoded data from the audio file and decoded it to reveal the hidden flag.

---

## 7. Security Impact (Real-World Mapping)

If sensitive data is hidden inside media files without encryption, it can be extracted through forensic analysis.  
Audio files shared publicly could unintentionally leak internal scripts, credentials, or messages.

This type of data hiding offers no real security.

---

## 8. Mitigation / Defensive Takeaway

- Do not embed sensitive information inside media files  
- Use proper encryption instead of obfuscation  
- Scan files before sharing them externally  

---

## 9. Learning Outcome

- Learned how data can be hidden inside audio files  
- Improved understanding of audio-based forensic analysis  
- Practiced identifying encoding patterns in non-text files  
