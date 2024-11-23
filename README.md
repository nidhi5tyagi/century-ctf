# century-ctf


---

# Century CTF Solution Guide

This repository provides a structured way to solve challenges in the Century CTF, securely store the passwords you find, and encrypt them using GPG for security.

## Requirements
Before you start, ensure you have the following installed:
- Powershell
- GPG (GNU Privacy Guard) for encryption
- A text editor (e.g., VSCode, Nano, or Vim)

## Steps to Solve Challenges and Save Passwords

### 1. Solve CTF Challenges
1. Visit the Century CTF platform and log in.
2. Begin solving challenges, one at a time.
3. For each challenge:
   - Analyze the provided resources or hints.
   - Execute the powershell commands to solve the challenge.
   - Once you retrieve the password, note it down.

### 2. Store Passwords in a Text File
1. Create a text file named `passwords.txt` in this directory.
2. Save each password/flag in the file in the format:

   ```
   [Challenge Name]: [Password]
   ```

   Example:
   ```
   Century2: example_password_123
   Cemyury2: another_password_456
   ```

### 3. Encrypt the Password File
1. Install GPG if not already installed:
   ```
   sudo apt-get install gpg  # For Debian/Ubuntu
   brew install gpg          # For macOS
   ```
2. Generate a GPG keypair if you don't have one:
   ```
   gpg --full-generate-key
   ```
   - Choose RSA and RSA (default).
   - Use at least 2048-bit encryption for security.
   - Provide a name, email, and passphrase when prompted.

3. Encrypt the `passwords.txt` file using your GPG key:
   ```
   gpg -e -r "Your Name or Email" passwords.txt
   ```
   This will create an encrypted file named `passwords.txt.gpg`.

4. Verify the encrypted file:
   ```
   gpg -d passwords.txt.gpg
   ```
   You'll be prompted for your passphrase to decrypt and view the file.

5. Delete the plaintext file for security:
   ```
   rm passwords.txt
   ```

### 4. Decrypt the File When Needed
To view the passwords, decrypt the file using GPG:
   ```
   gpg -d passwords.txt.gpg > passwords.txt
   ```
   This will output the decrypted content into a new `passwords.txt` file.

## Tips for Solving CTF Challenges
- Use online resources and tools (like Burp Suite, nmap, or hashcat) as needed.
- Document your methodology for each challenge.
- Work with teammates if the competition allows collaboration.

## Notes
- Ensure the encrypted `passwords.txt.gpg` file is backed up securely.
- Do not share your private GPG key; it is used to decrypt the file.

Happy hacking and good luck with the Century CTF!

--- 

### File Structure
```
.
├── README.md        # This file
└── Nidhi_Century_Pass_encrypted_file.gpg
