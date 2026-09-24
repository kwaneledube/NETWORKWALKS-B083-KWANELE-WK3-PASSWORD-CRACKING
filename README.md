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

![John the Ripper installed and verified](W3-PM1/john%20exe.png)

**2. Johnny configured with the John the Ripper executable**
Johnny GUI pointed to `john.exe`, confirming detection of John the Ripper 1.9.0-jumbo-1.

![Johnny detecting the John the Ripper executable](W3-PM1/Detected%20John%20the%20Ripper.png)

**3. Hash extracted from the PDF**
Used the Online Hash Crack PDF Hash Extractor to pull the crackable `$pdf$...` hash from `My Locked PDF1.pdf`.

![PDF hash extracted via Online Hash Crack](W3-PM1/Hash%20of%20PDF1.png)

**4. Hash saved to a text file**
Hash saved locally as `hash1.txt` for import into Johnny.

![Hash saved in hash1.txt](W3-PM1/Hash%20Pasted.png)

**5. Attack run and password cracked**
Johnny ran the attack against the saved hash and successfully recovered the password.

![Johnny successfully cracking the password](W3-PM1/Password%20cracked.png)

**Result:** Password = `good-luck`

**6. PDF opened with the cracked password**
The decrypted PDF opened using the recovered password, confirming success.

![Decrypted PDF opened, confirming the correct password](W3-PM1/Congratulations%20page.png)

---

## PM2 — Password Cracking with NetworkWalks Tools

**Objective:** Crack the same PDF password using the NetworkWalks Hash Calculator and Password Cracker web tools.

### Steps & Evidence

**1. Hash extracted via NetworkWalks Hash Calculator**
Uploaded `My Locked PDF1.pdf` to the [NetworkWalks Hash Calculator](https://networkwalks.com/hash-calculator/), which parsed the file locally and returned the `$pdf$...` hash.

![Hash extracted via the NetworkWalks Hash Calculator](W3-PM2/Hash%20showing%20on%20the%20Hash%20Calculator.png)

**2. Initial attack with the built-in wordlist**
Pasted the hash into the [NetworkWalks Password Cracker](https://networkwalks.com/password-cracker/) and ran the attack using the tool's built-in 100-word list.

![Password Cracker running against the built-in 100-word list](W3-PM2/cracking%20in%20progress.png)

**3. Built-in wordlist exhausted — no match**
The 100-word list ran to completion without finding a match, and a larger wordlist was uploaded (`JTR_default_password.txt`) in response.

![Larger wordlist uploaded and attack restarted](W3-PM2/Added%20JTR%20default%20password%20txt.png)

**4. Wordlist verified in Notepad**
Opened the uploaded wordlist in Notepad and confirmed the correct password was present in the list before re-running the attack.

![JTR_default_password.txt opened in Notepad, confirming the password is present](W3-PM2/Notepad%20txt%20check%20of%20password.png)

**5. Second attack in progress with the larger wordlist**
Re-ran the attack using the uploaded `JTR_default_password.txt` (3,556 words).

![Second attack in progress using the uploaded wordlist](W3-PM2/Password%20Cracking%20in%20Progress.png)

**6. Password cracked successfully**
The attack matched the password on this run.

![Password cracked successfully via NetworkWalks Password Cracker](W3-PM2/Password%20cracked%20successfully.png)

**Result:** Password = `good-luck`

The same decrypted PDF and Congratulations page shown above (PM1, Step 6) confirms the password recovered in PM2.

---

## PM1 (PDF2) — Password Cracking with JTR (John the Ripper + Johnny GUI)

**Objective:** Crack the password of `My Locked PDF2.pdf` using JTR John and Johnny on Windows.

### Steps & Evidence

**1. Hash extracted from the PDF**
Used the Online Hash Crack PDF Hash Extractor to pull the crackable `$pdf$...` hash from `My Locked PDF2.pdf`.

![PDF2 hash extracted via Online Hash Crack](PDF2-W3-PM1/Locked%20PDF2%20Online%20Hash%20Cracked.png)

**2. Attack run and password cracked in Johnny**
The hash was loaded into Johnny and the attack was run against it, successfully recovering the password.

![Johnny successfully cracking the PDF2 password](PDF2-W3-PM1/Password%20Cracked%20from%20Johnny.png)

**Result:** Password = `password1`

**3. PDF opened with the cracked password**
The recovered password was used to unlock `My Locked PDF2.pdf`, revealing the flag: `nw{networkwalks_persistence_jtr_270521}`.

![Decrypted PDF2 opened, confirming the correct password and flag](PDF2-W3-PM1/Locked%20PDF2%20opened.png)

---

## PM2 (PDF2) — Password Cracking with NetworkWalks Tools

**Objective:** Crack the password of `My Locked PDF2.pdf` using the NetworkWalks Hash Calculator and Password Cracker web tools.

### Steps & Evidence

**1. Hash extracted via NetworkWalks Hash Calculator**
Uploaded `My Locked PDF2.pdf` to the NetworkWalks Hash Calculator, which parsed the file locally and returned the `$pdf$...` hash.

![PDF2 hash extracted via the NetworkWalks Hash Calculator](PDF2-W3-PM2/Hash%20in%20Hash%20Calculator.png)

**2. Attack run with the built-in wordlist**
Pasted the hash into the NetworkWalks Password Cracker and ran the attack using the tool's built-in 100-word list.

![Password Cracker sifting through the built-in wordlist](PDF2-W3-PM2/Password%20Cracker%20sifting%20passwords.png)

**3. Password cracked successfully**
The built-in 100-word list matched the password on this run, without needing a larger wordlist.

![PDF2 password cracked successfully via NetworkWalks Password Cracker](PDF2-W3-PM2/Password%20Cracked.png)

**Result:** Password = `password1`

**4. PDF opened with the cracked password**
The recovered password was used to unlock the PDF, confirming the same result reached independently via PM1.

![Decrypted PDF2 opened via NetworkWalks tools](PDF2-W3-PM2/locked%20pdf2%20opened.png)

---

## PM1 (PDF3) — Password Cracking with JTR (John the Ripper + Johnny GUI)

**Objective:** Crack the password of `My Locked PDF3.pdf` using JTR John and Johnny on Windows.

### Steps & Evidence

**1. Hash extracted from the PDF**
Used the Online Hash Crack PDF Hash Extractor to pull the crackable `$pdf$...` hash from `My Locked PDF3.pdf`.

![PDF3 hash extracted via Online Hash Crack](PDF3-W3-PM1/PDF3%20OnlineHasCrack.png)

**2. Issue encountered — hash file failed to load in Johnny**
The hash was manually copied into a text file and opened in Johnny, but the tool reported "No hashes loaded" with no format detected — even after re-saving the file with different encodings (UTF-8, ANSI). Comparing the pasted hash against the original revealed the manual copy-paste had introduced a corrupted/extra character into the hash string.

![Johnny failing to load a corrupted hash file](PDF3-W3-PM1/No%20Hashes%20in%20Johnny.png)

**3. Fix — hash re-obtained via direct file download**
Rather than manually copying the hash text again, the PDF was uploaded to the NetworkWalks Hash Calculator, and the hash was retrieved using its **Download** button instead of copy-paste. This produced a clean hash file with no manual transcription involved, which loaded correctly into Johnny.

**4. Attack run and password cracked**
With the clean hash file loaded, Johnny ran the attack and successfully recovered the password.

![Johnny successfully cracking the PDF3 password](PDF3-W3-PM1/Password%20Cracked%20in%20Johnny.png)

**Result:** Password = `1qaz2wsx`

**5. PDF opened with the cracked password**
The recovered password was entered to unlock `My Locked PDF3.pdf`.

![Entering the cracked password into My Locked PDF3.pdf](PDF3-W3-PM1/Inserting%20Password.png)

![Decrypted PDF3 opened, confirming the correct password and flag](PDF3-W3-PM1/PDF%20opened.png)

**Flag:** `nw{networkwalks_flag_260821_1}`

---

## PM2 (PDF3) — Password Cracking with NetworkWalks Tools

**Objective:** Crack the password of `My Locked PDF3.pdf` using the NetworkWalks Hash Calculator and Password Cracker web tools.

### Steps & Evidence

**1. Hash extracted via NetworkWalks Hash Calculator**
Uploaded `My Locked PDF3.pdf` to the NetworkWalks Hash Calculator, which parsed the file locally and returned the `$pdf$...` hash.

![PDF3 hash extracted via the NetworkWalks Hash Calculator](PDF3-W3-PM2/PDF3%20uploaded%20in%20Hash%20Calculator.png)

**2. Hash pasted into the Password Cracker**
The extracted hash was pasted into the NetworkWalks Password Cracker, initially set to the built-in 100-word list.

![PDF3 hash pasted into the NetworkWalks Password Cracker](PDF3-W3-PM2/Password%20Cracker%20with%20Hash%20visible.png)

**3. Built-in wordlist exhausted — no match**
The built-in 100-word list ran to completion without finding a match.

![Built-in 100-word list exhausted with no match](PDF3-W3-PM2/Password%20Access%20Denied%20100%20wordlist.png)

**4. Second attempt with a larger wordlist — also failed**
A `fasttrack.txt` wordlist (221 words) was uploaded and run, but also exhausted with no match.

![fasttrack.txt (221 words) also exhausted with no match](PDF3-W3-PM2/Fasttrack%20ran-failed%20too.png)

**5. Third attempt with a larger wordlist — also failed**
A `JTR_default_password.txt` wordlist (3,556 words) was uploaded and run, but this too failed to find a match.

![JTR_default_password.txt (3,556 words) running and ultimately failing to match](PDF3-W3-PM2/JTR%20wordlist%20running-failed.png)

**6. Loading rockyou.txt — the full 14.3 million word list**
Since none of the smaller lists contained the password, the full `rockyou.txt` wordlist (14,344,380 words) was uploaded to the Password Cracker.

![rockyou.txt (14,344,380 words) loaded into the Password Cracker](PDF3-W3-PM2/Inserted%20rockyou%20wordlist.png)

**7. Issue encountered — browser tool froze on the full wordlist**
Running rockyou.txt directly in the browser-based Password Cracker caused the page to become unresponsive. Since the tool runs entirely client-side in JavaScript rather than as a compiled program, attempting to process 14.3 million candidate passwords overwhelmed the browser tab.

![Browser tab becoming unresponsive when running the full rockyou.txt wordlist](PDF3-W3-PM2/Rockyou%20is%20too%20much%20for%20cracker.png)

**8. Fix — cracked natively using John the Ripper in Kali Linux**
Rather than forcing the browser tool past its limits, the same hash was moved into a Kali Linux VirtualBox VM (via a VirtualBox shared folder) and cracked using John the Ripper running natively against Kali's built-in `rockyou.txt`, which runs at full CPU speed rather than being throttled by the browser:

```bash
cp /media/sf_Downloads/"My Locked PDF3.hash.txt" ~/Desktop/hash3.txt
cd ~/Desktop
john --wordlist=/usr/share/wordlists/rockyou.txt --format=PDF hash3.txt
```

The password was recovered almost instantly once run natively.

![PDF3 password cracked successfully in Kali Linux using native John the Ripper](PDF3-W3-PM2/Kali%20linux%20cracked%20password.png)

**Result:** Password = `1qaz2wsx`

**9. PDF opened with the cracked password**
The same decrypted PDF and flag shown above (PM1, Step 5) confirms the password recovered independently in PM2.

---

## Key Takeaways
- A small or generic wordlist (like a default 100-word list) can fail against passwords that aren't in it — this is why choosing the right wordlist matters as much as the cracking tool itself. On `My Locked PDF2.pdf`, the built-in 100-word list was actually enough to find the password on the first attempt.
- Both a dedicated desktop tool (JTR/Johnny) and a lightweight browser-based tool can recover the same password from the same hash, since both are running the same dictionary-attack logic.
- Hashing is one-way (used to validate), while encryption is two-way (used to protect data that must later be recovered) — this is why cracking a password hash means guessing until a match is found, rather than "decrypting" it directly.
- Password strength varies significantly between files: `My Locked PDF1.pdf` needed a larger, targeted wordlist, while `My Locked PDF2.pdf` fell to the default 100-word list almost immediately — reinforcing that common or short passwords are cracked quickly regardless of the tool used.
- Manually copying and pasting a long hash string is error-prone — a single corrupted or duplicated character (as happened with `My Locked PDF3.pdf`) will silently break the hash format and cause tools like Johnny to report "No hashes loaded" with no clear reason why. Downloading the hash directly as a file, rather than copy-pasting it, avoids this failure mode entirely.
- Browser-based cracking tools are convenient for small-to-medium wordlists, but they run entirely client-side in JavaScript and can freeze when asked to process very large wordlists (like the 14.3-million-entry `rockyou.txt`). Native tools like John the Ripper, run directly on the OS (in this case, inside Kali Linux), handle the same wordlist at full CPU speed without issue — reinforcing why real-world password auditing is typically done with native tools rather than browser demos at scale.

## Tools Used
- John the Ripper (Jumbo) + Johnny GUI
- Online Hash Crack — PDF Hash Extractor
- NetworkWalks Hash Calculator
- NetworkWalks Password Cracker

---

## Author
**Kwanele Dube** — Cybersecurity Intern, NetworkWalks Academy (Batch B083)
[LinkedIn post for this project](https://www.linkedin.com/feed/update/urn:li:activity:7508865950633373696/)
