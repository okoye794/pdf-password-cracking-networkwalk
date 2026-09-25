# pdf-password-cracking-networkwalk
Dictionary attack against password-protected PDFs- Networkwalks Academy internship project 
# Cracking Password-Protected PDFs with Dictionary Attacks
**Networkwalks Academy Internship Project — Cybersecurity & Ethical Hacking**

## 📌 Overview

As part of my cybersecurity internship at **Networkwalks Academy**, I completed a hands-on Capture-The-Flag (CTF) style exercise focused on password security. The goal was to understand, from an attacker's perspective, how weak and commonly reused passwords make password-protected files trivial to break into — and why this matters for real-world security awareness.

I used Networkwalks' own browser-based tools to:
1. Extract a crackable hash from a password-protected PDF
2. Run a dictionary attack against that hash
3. Recover the plaintext password
4. Capture the CTF flags awarded for each successful crack

## 🛠️ Tools Used

- **Hash Calculator** (Networkwalks) — parses a PDF locally in the browser and extracts a `$pdf$` formatted hash (nothing is uploaded to a server)
- **Password Cracker through Dictionary Attacks** (Networkwalks) — hashes every word in a wordlist and compares it against the extracted PDF hash, following the same principle used by tools like **John the Ripper**

## 🔎 Step-by-Step Process

### Step 1: Extract the hash from the locked PDF
I uploaded the password-protected PDF to the Hash Calculator tool. It parsed the file entirely client-side and generated a `$pdf$...` formatted hash — the same format John the Ripper uses for PDF cracking.

### Step 2: Run the dictionary attack
I pasted the extracted hash into the Password Cracker tool and ran the attack. The tool hashed each word from a common password wordlist (things like `123456`, `starwars`, `shadow`, `superman`) and compared it against the target hash.

Within 35 attempts, it found a match:

**Cracked password:** `1qaz2wsx`

### Step 3: Capture the flag
Successfully cracking the password unlocked the first flag in the challenge.

### Step 4: Repeat on a second PDF
I repeated the process on a second locked PDF. This time the tool worked through 91 attempts before landing a match on a very common password:

**Cracked password:** `password1`

### Step 5: Capture the final flag
Completing this second crack captured the final flag for the exercise.

## 💡 Lessons Learned

- **Weak passwords fall fast.** Both target passwords were cracked in under 100 attempts using nothing more than a basic common-password wordlist — no brute force, no GPU cluster required.
- **Reused/common passwords are the #1 weak point.** `password1` and `1qaz2wsx` are both fixtures on "most common passwords" lists, which is exactly why they were guessed so quickly.
- **Hash extraction matters.** Understanding how a `$pdf$` hash is structured helped me see why PDF encryption strength depends heavily on the password chosen, not just the encryption algorithm.
- **Dictionary attacks vs. brute force.** This exercise reinforced why attackers prefer wordlist-based (dictionary) attacks first — they're dramatically faster than brute-forcing every possible combination when users pick predictable passwords.
- **Real-world takeaway:** This is exactly why security policies push for passphrases, password managers, and minimum complexity/length requirements — a "simple to remember" password is often trivially simple to crack.

## 🎯 Skills Practiced

- PDF file structure & hash extraction
- Dictionary/wordlist attack methodology (John the Ripper-style approach)
- Password security analysis
- CTF-style problem solving under Networkwalks Academy's guided labs

---

**Internship:** Networkwalks Academy — Cybersecurity & Ethical Hacking
**Instructor:** Waqas Karim (CCIE)

*This project was completed using Networkwalks' free, browser-based security tools for educational purposes only. No unauthorized systems or files were accessed — all targets were provided as part of the training curriculum.*
