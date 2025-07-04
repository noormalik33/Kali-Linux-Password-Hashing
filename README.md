# 🔐 Kali Linux Password Hashing & Cracking

A Kali Linux-based project demonstrating how to crack MD5 and SHA-1 hashes using john and the rockyou.txt wordlist. Includes hash samples, attack strategies, and explanations for unsuccessful attempts.

This project demonstrates how to extract and crack password hash values using **Kali Linux** and **John the Ripper** with the popular `rockyou.txt` wordlist. The objective is to understand password security, hashing algorithms, and brute-force dictionary attacks.

## 🧪 Project Overview

The project includes:

- Password hash examples in **MD5** and **SHA-1**
- Step-by-step cracking procedure using `john`
- Common issues encountered (e.g., encoding, incomplete wordlists)
- Analysis of why certain hashes were not cracked

---

## 🛠 Tools Used

- 🐧 **Kali Linux**
- 🛠️ **John the Ripper**
- 📂 **rockyou.txt** dictionary (`/usr/share/wordlists/rockyou.txt`)
- 📄 Text file containing password hashes (`hash.txt`)

---

## ⚙️ Step-by-Step Procedure

### 1. Extract the rockyou.txt Wordlist
cd /usr/share/wordlists/
sudo unzip rockyou.txt.zip

2. Create a File with Hashes
cd ~/Desktop
nano hash.txt

# Paste the provided hash values into this file and save it
3. Run John the Ripper

john hash.txt --wordlist=/usr/share/wordlists/rockyou.txt
🔍 Sample Hashes Analyzed
Hash #	Hash Value	Algorithm
1	0ceb1fd260c35bd50005341532748de6	MD5
2	a448017aaf21d8525fc10ae87aa6729d	MD5
3	8cb2237d0679ca88db6464eac60da96345513964	SHA-1
4	40bd001563085fc35165329ea1ff5c5ecbdbbeef	SHA-1
5	742f40cbb203f3b2c879a72a2828dac1	MD5
6	8192344dc6a7b0eb14fb11b805d3faf78e97130a	SHA-1
7	a192fae8d85616e3862283d09290d858	MD5
8	be7fba901f88b83f5164674813d607439e72b39f	SHA-1
9	f865b53623b121fd34ee5426c792e5c33af8c227	SHA-1
10	d033e22ae348aeb5660fc2140aec35850c4da997	SHA-1
11	21232f297a57a5a743894a0e4a801fc3	MD5 (→ password: admin) ✅

## ⚠️ Common Issues
❌ Encoding Errors: rockyou.txt may be in ISO-8859-1, while terminal uses UTF-8. Use:

iconv -f ISO-8859-1 -t UTF-8 rockyou.txt -o rockyou-utf8.txt
🕒 Cracking Still Running: If no output, check with:

john --show hash.txt
❌ Hash Format Mismatch: Ensure hashes are correctly formatted and valid

❌ Wordlist Limitation: The password might not exist in rockyou.txt. Consider using custom or larger wordlists.

## 📌 Outcome
✅ Some hashes (like 21232f297a57a5a743894a0e4a801fc3) were successfully cracked.

❌ Others remain uncracked due to dictionary limitations or encoding issues.

## 📚 Demonstrated real-world limitations of dictionary-based hash cracking.

 ## 👩‍💻 Author

**Noor Malik**  
IT Student  
📍 Islamabad, Pakistan  
📧 Email: noormalik56500@gmail.com  
🔗 [LinkedIn](https://www.linkedin.com/in/noormalik56500/)


🔐 Educational purpose only. Always use ethical hacking skills responsibly.

