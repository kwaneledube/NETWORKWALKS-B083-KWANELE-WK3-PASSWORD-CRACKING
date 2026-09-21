# NetworkWalks B083 — Week 3: Password Cracking

**Program:** NetworkWalks Cybersecurity Internship (Batch B083)

## Overview
Week 3 focused on password cracking against a password-protected PDF file (`My Locked PDF1.pdf`), completed in two modules: PM1 using John the Ripper (JTR) with the Johnny GUI, and PM2 using NetworkWalks' own browser-based Hash Calculator and Password Cracker tools.

---

## PM1 — Password Cracking with JTR (John the Ripper + Johnny GUI)

**Objective:** Crack the password of `My Locked PDF1.pdf` using JTR John and Johnny on Windows.

### Steps & Evidence

**1. John the Ripper installed and verified**
JTR (jumbo build) installed on Windows; command line confirms the tool and lists available options.
`W3-PM1/john_exe.png`

**2. Johnny configured with the John the Ripper executable**
Johnny GUI pointed to `john.exe`, confirming detection of John the Ripper 1.9.0-jumbo-1.
`W3-PM1/Detected_John_the_Ripper.png`

**3. Hash extracted from the PDF**
Used the Online Hash Crack PDF Hash Extractor to pull the crackable `$pdf$...` hash from `My Locked PDF1.pdf`.
`W3-PM1/Hash_of_PDF1.png`

**4. Hash saved to a text file**
Hash saved locally as `hash1.txt` for import into Johnny.
`W3-PM1/Hash_Pasted.png`

**5. Attack run and password cracked**
Johnny ran the attack against the saved hash and successfully recovered the password.
`W3-PM1/Password_cracked.png`

**Result:** Password = `good-luck`

**6. PDF opened with the cracked password**
The decrypted PDF opened using the recovered password, confirming success.
`W3-PM1/Congratulations_page.png`

---

## PM2 — Password Cracking with NetworkWalks Tools

**Objective:** Crack the same PDF password using the NetworkWalks Hash Calculator and Password Cracker web tools.

### Steps & Evidence

**1. Hash extracted via NetworkWalks Hash Calculator**
Uploaded `My Locked PDF1.pdf` to the [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/), which parsed the file locally and returned the `$pdf$...` hash.
`W3-PM2/Hash_showing_on_the_Hash_Calculator.png`

**2. Initial attack with the built-in wordlist**
Pasted the hash into the [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/) and ran the attack using the tool's built-in 100-word list.
`W3-PM2/cracking_in_progress.png`

**3. Built-in wordlist exhausted — no match**
The 100-word list ran to completion without finding a match, and a larger wordlist was uploaded (`JTR_default_password.txt`) in response.
`W3-PM2/Added_JTR_default_password_txt.png`

**4. Wordlist verified in Notepad**
Opened the uploaded wordlist in Notepad and confirmed the correct password was present in the list before re-running the attack.
`W3-PM2/Notepad_txt_check_of_password.png`

**5. Second attack in progress with the larger wordlist**
Re-ran the attack using the uploaded `JTR_default_password.txt` (3,556 words).
`W3-PM2/Password_Cracking_in_Progress.png`

**6. Password cracked successfully**
The attack matched the password on this run.
`W3-PM2/Password_cracked_successfully.png`

**Result:** Password = `good-luck`

The same decrypted PDF and Congratulations page shown in `W3-PM1/Congratulations_page.png` confirms the password recovered in PM2.

---

## Key Takeaways
- A small or generic wordlist (like a default 100-word list) can fail against passwords that aren't in it — this is why choosing the right wordlist matters as much as the cracking tool itself.
- Both a dedicated desktop tool (JTR/Johnny) and a lightweight browser-based tool can recover the same password from the same hash, since both are running the same dictionary-attack logic.
- Hashing is one-way (used to validate), while encryption is two-way (used to protect data that must later be recovered) — this is why cracking a password hash means guessing until a match is found, rather than "decrypting" it directly.

## Tools Used
- John the Ripper (Jumbo) + Johnny GUI
- Online Hash Crack — PDF Hash Extractor
- NetworkWalks Hash Calculator
- NetworkWalks Password Cracker
