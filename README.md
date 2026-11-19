
## WEEK 3 PROJECT: PDF PASSWORD AUDITING WITH JOHN THE RIPPER & DICTIONARY ATTACKS

**B084-NETWORKWALKS | CYBERSECURITY | NETWORKWALKS**

| Project Details | Information |
|---|---|
| Student / Pentester | Musa-Mustapha Khakiqat |
| Programme / Batch | B084 – NetworkWalks |
| Project | Week 3 – PDF Password Auditing with John the Ripper and Dictionary Attacks |
| Date | 18 November 2026 |
| Assessment Target | Password-protected PDF files supplied for the authorized training exercise |
| Permission secured? | Yes – activity limited to the authorized training files |
| Project Status | Completed |

---

## 1. Liability Disclaimer

I performed this activity only on the PDF files provided for the authorized NetworkWalks training exercises. I did not attempt to access, extract, or crack hashes from files or systems belonging to other people. The information and screenshots in this repository are shared for educational and cybersecurity learning purposes only.

Do not use these techniques to access files without the owner's clear permission. Unauthorized access may violate laws and can result in serious consequences. The author, instructors, and training provider are not responsible for misuse of the information shared in this report. Anyone applying these concepts is responsible for ensuring that their actions are lawful and authorized.

## 2. Introduction

This Week 3 project built on the previous PDF hash-extraction exercise by introducing John the Ripper (via the Johnny GUI) and a browser-based dictionary-attack tool to audit the strength of passwords protecting sample PDF files.

The exercise involved reviewing John the Ripper's background and official binaries, configuring the Johnny GUI to recognize the John the Ripper executable, extracting crackable hashes from authorized sample PDFs, and running dictionary attacks against those hashes in a controlled training environment. Each successfully audited file revealed a completion flag confirming the exercise was finished correctly.

The purpose was to gain hands-on exposure to password-auditing tools, understand how dictionary attacks work, and reinforce why predictable passwords are a serious security risk.

## 3. Tools Used

| Tool | Purpose |
|---|---|
| John the Ripper (Openwall) | Industry-standard password-auditing tool reviewed as the basis for the exercise |
| Johnny (GUI for John the Ripper) | Graphical front end used to configure and run John the Ripper locally |
| Online Hash Crack – PDF Hash Extractor | Used to extract crackable hash representations from the training PDFs |
| NetworkWalks Hash Calculator | Used to generate/extract hashes and explore hash formats |
| NetworkWalks Password Cracker (Dictionary Attack Lab) | Browser-based tool simulating a dictionary attack against a PDF hash |
| Notepad | Used to view extracted hash text |
| Web browser | Used to access the online training tools |
| Password-protected PDF samples | Authorized files used for the exercises |

## 4. Activities Performed

### 4.1 Reviewing John the Ripper and Johnny

I reviewed the official Openwall page for John the Ripper to understand its purpose as a password-auditing tool, and the Johnny GUI binaries page to identify the correct release for the training environment.

Johnny was then configured to point to the local John the Ripper executable (jumbo build), confirming the tool was correctly detected and ready to accept a password hash.

### 4.2 Extracting the PDF Hash

An authorized password-protected PDF was uploaded to an online PDF-hash-extraction tool, which produced a crackable hash in the format used by `pdf2john` / `pdf2hashcat`. The extracted hash was reviewed in Notepad and saved locally for use in the lab.

The complete hash values are not reproduced in this public README; they are redacted in the evidence screenshots below.

### 4.3 Loading the Hash into Johnny

The saved hash file was imported into Johnny, where it appeared in the password table ready for an attack to be started. The password and hash columns are redacted in the evidence to avoid publishing crackable credential data.

### 4.4 Capturing Flag 1

Opening the first unlocked PDF with the recovered password displayed a congratulations page confirming the flag had been captured. The flag value itself is redacted in the evidence screenshot, consistent with responsible disclosure practice.

### 4.5 Exploring the Hash Calculator

The NetworkWalks Hash Calculator was reviewed again, this time focusing on its PDF-hash extraction tab. A sample locked PDF was processed to confirm the tool could generate the same crackable hash format used by John the Ripper, reinforcing the link between the two tools.

### 4.6 Dictionary Attack – Lab 1

The extracted hash was pasted into the NetworkWalks Password Cracker (Dictionary Attack Lab), which hashes every word in a wordlist and compares it against the target hash – the same underlying idea John the Ripper uses. The built-in 100-word list was used to run the attack, which successfully matched the password. The recovered password was then used to unlock the corresponding PDF, revealing a second captured flag.

### 4.7 Dictionary Attack – Lab 2

A second, independent hash was run through the same dictionary-attack process. After trying a number of common passwords, the tool again found a match. Unlocking the associated PDF with the recovered password displayed a third congratulations page and flag, reinforcing the lesson that predictable, dictionary-style passwords (e.g. keyboard patterns) are quickly defeated by this type of attack.

## 5. Risk Analysis / Impact

| Area | Observation / Impact |
|---|---|
| Weak / common passwords | Passwords found in common wordlists (e.g. keyboard patterns, simple words plus numbers) are cracked almost immediately by dictionary attacks |
| Hash exposure | Extracted PDF hashes should be treated as sensitive security information, since possession of the hash is often enough to recover the password |
| Tool accessibility | Free, browser-based tools make password auditing (and potential misuse) accessible to anyone, raising the importance of authorization and ethics |
| File protection | Password protection on a PDF is only as strong as the password chosen and the encryption settings used to create it |
| Unauthorized use | Running password-auditing tools against files without permission can cause harm and may be unlawful |
| Data confidentiality | Long, unique, non-dictionary passwords significantly increase the time and resources needed for a successful attack |

## 6. Recommendations

1. Use long, unique passwords for sensitive PDF documents – avoid single dictionary words, keyboard patterns, and simple substitutions.
2. Avoid reusing the same password across multiple protected files or accounts.
3. Store passwords securely (e.g. in a password manager) and never share them publicly.
4. Treat extracted hashes as sensitive data; do not post them in public repositories.
5. Use strong, modern encryption settings when creating password-protected PDFs.
6. Only run password-auditing tools such as John the Ripper, Johnny, or online dictionary-attack tools against files for which written authorization has been granted.
7. Keep password-auditing tools and wordlists updated, and stay within the scope defined for each authorized lab or engagement.

## 7. Conclusion

The Week 3 project extended my practical understanding of password security by moving from hash extraction into active password auditing with John the Ripper (via Johnny) and a dictionary-attack simulation tool.

I gained clearer insight into how quickly weak or common passwords can be recovered once their hash is known, why hash values must be treated as sensitive, and how legitimate security tools are used responsibly within an authorized scope. The multiple flag captures across this exercise reinforced both the technical workflow and the ethical boundaries that must accompany it.

## 8. Evidence Collected

The screenshots below document the activities carried out during the Week 3 exercise. Sensitive values — including complete hash strings, recovered passwords, and unique flag/completion tokens — have been redacted (blacked out) in the images below. Nothing sensitive is reproduced in the text of this README.

### Evidence 1 – John the Ripper Overview
Reference page on Openwall describing John the Ripper and its purpose as a password-auditing tool.

![John the Ripper overview](evidence/01-john-the-ripper-overview.jpg)

### Evidence 2 – Johnny GUI Binaries Page
The official binaries page used to identify the correct Johnny GUI release for the training environment.

![Johnny GUI binaries page](evidence/02-johnny-gui-binaries-page.jpg)

### Evidence 3 – Johnny Configured with John the Ripper
Johnny's settings page showing the configured path to the local John the Ripper (jumbo) executable.

![Johnny settings configured](evidence/03-johnny-settings-configured.jpg)

### Evidence 4 – PDF Hash Extraction Output
The online PDF-hash-extraction tool after processing the authorized sample PDF. The extracted hash is redacted.

![PDF hash extractor output](evidence/04-pdf-hash-extractor-output.jpg)

### Evidence 5 – Extracted Hash Viewed in Notepad
The extracted hash opened in Notepad for review before being imported into Johnny. The hash text is redacted.

![Hash viewed in Notepad](evidence/05-hash-viewed-in-notepad.jpg)

### Evidence 6 – Saving the Hash File
The hash saved locally as a text file for use with Johnny / John the Ripper.

![Saving hash file](evidence/06-saving-hash-file.jpg)

### Evidence 7 – Hash Imported into Johnny
The saved hash loaded into Johnny's password table, ready for an attack. The password and hash columns are redacted.

![Johnny hash imported](evidence/07-johnny-hash-imported.jpg)

### Evidence 8 – Flag 1 Captured
The first unlocked PDF displaying a congratulations page confirming the flag was captured. The flag value is redacted.

![Flag captured – PDF 1](evidence/08-flag-captured-pdf1.jpg)

### Evidence 9 – NetworkWalks Hash Calculator
The Hash Calculator tool reviewed again, with its PDF tab selected for generating a crackable hash from a locked PDF.

![Hash Calculator tool](evidence/09-hash-calculator-tool.jpg)

### Evidence 10 – Hash Calculator Extracted Hash
The Hash Calculator's PDF tab after processing a sample locked PDF, confirming the same crackable hash format. The hash is redacted.

![Hash Calculator extracted hash](evidence/10-hash-calculator-extracted-hash.jpg)

### Evidence 11 – Dictionary Attack Lab, Hash Entered
The NetworkWalks Password Cracker with the extracted PDF hash pasted in, ready to run the dictionary attack. The hash is redacted.

![Dictionary attack hash entered](evidence/11-dictionary-attack-hash-entered.jpg)

### Evidence 12 – Dictionary Attack Success (1)
The dictionary attack successfully matching a password against the hash, with the result used to unlock the PDF. The password and hash are redacted.

![Dictionary attack success 1](evidence/12-dictionary-attack-success-password1.jpg)

### Evidence 13 – Flag 2 Captured
The second unlocked PDF confirming the flag for this exercise was captured. The flag value is redacted.

![Flag captured – PDF 2](evidence/13-flag-captured-pdf2.jpg)

### Evidence 14 – Dictionary Attack Success (2)
A second, independent dictionary attack successfully matching a different password against its target hash. The password and hash are redacted.

![Dictionary attack success 2](evidence/14-dictionary-attack-success-2.jpg)

### Evidence 15 – Flag 3 Captured
The final unlocked PDF confirming the last flag of this exercise was captured. The flag value is redacted.

![Flag captured – PDF 3](evidence/15-flag-captured-pdf3-persistence.jpg)

## 9. Author

**Musa-Mustapha Khakiqat**
Cybersecurity Student – B084
Aspiring Security Analyst

## 10. Project Information

**Project Title:** Week 3 – PDF Password Auditing with John the Ripper and Dictionary Attacks
**Training Provider:** NetworkWalks
**Programme / Batch:** B084
**Focus Area:** Password Security, Password Auditing Tools, and Dictionary Attacks

---

### Ethical Use Guidelines

- Work only with files and systems you own or have explicit permission to assess.
- Keep passwords, hashes, and other sensitive evidence private.
- Do not upload confidential files to online tools unless you are authorized and understand how the service handles uploaded data.
- Use the knowledge gained from this project to improve security awareness and defensive practices, not to access systems or files without authorization.
