# Classical-Cryptanalysis-Lab

## Overview
This project analyzes and decrypts multiple classical cryptographic ciphers using both manual cryptanalysis techniques and automated tools. The lab focuses on identifying cipher types, applying decryption strategies, and using cryptographic tools to recover plaintext messages.

The exercises progress from basic Caesar ciphers to more complex monoalphabetic substitution ciphers, demonstrating how classical encryption methods can be broken using frequency analysis, pattern recognition, and cryptographic software tools.

Additionally, the lab includes a programming challenge involving AES encryption, where the correct key was identified through a brute-force approach.

## Objectives
The objectives of this lab were to:
- Identify different types of classical ciphers
- Apply systematic cryptanalysis techniques
- Use cryptographic tools to assist with decryption
- Analyze ciphertext patterns and frequency distributions
- Recover plaintext messages from encrypted text
- Demonstrate understanding of classical encryption weaknesses

## Tools Used
- CrypTool 2
- dcode.fr
- Hexdump
- Strings
- OpenSSL
- Frequency analysis tools

## Cipher Decryption Exercises
**Basic Level - Caesar Cipher (1-6)**
The first set of ciphertexts used Caesar shift ciphers, where each letter is shifted by a fixed number in the alphabet.

Using frequency analysis and brute-force shift testing, the correct plaintext messages were recovered.
| Cipher # | Cipher Type     | Key (Shift) | Tool Used     |
| -------- | --------------- | ----------- | ------------- |
| 1        | Caesar Cipher   | 23          | CrypTool      |
| 2        | Caesar Cipher   | 23          | CrypTool      |
| 3        | Caesar Cipher   | 23          | CrypTool      |
| 4        | Caesar Cipher   | 25          | CrypTool      |
| 5        | Caesar Cipher   | 25          | CrypTool      |
| 6        | Beaufort Cipher | —           | Beaufort Tool |

These examples demonstrate how simple substitution-based ciphers are vulnerable to brute-force attacks due to the small keyspace.

**Intermediate Level - Caesar Cipher with Longer Text (7-9)**
The second set contained longer ciphertext messages encrypted with Caesar shifts.
| Cipher # | Shift | Result                 |
| -------- | ----- | ---------------------- |
| 7        | 5     | Decrypted successfully |
| 8        | 20    | Decrypted successfully |
| 9        | 13    | Decrypted successfully |

Even though the ciphertext appeared more complex, the underlying encryption was still a simple rotational substitution, making it easy to break.

**Example**

Ciphertext:
QEBXO OJVFP LKQEB JLSB

Method:
Caesar Cipher (Shift 23)

Plaintext:
THE ARMY IS ON THE MOVE
**Advanced Level - Monoalphabetic Substitution (10-14)**
The final group of ciphertexts used monoalphabetic substitution ciphers, which require letter mapping rather than simple shifts.

**Decryption Process**
1. Frequency analysis was performed to identify common English letters.
2. Letter mapping was gradually constructed using:
      - common digraphs (TH, HE)
      - trigrams (THE, ING)
      - word pattern recognition
3. CrypTool’s automatic substitution analyzer generated candidate mappings.
4. The mappings were refined manually using known English word patterns.
This approach allowed the ciphertext instructions to be reconstructed into a coherent plaintext narrative describing the overall puzzle-solving process.

## AES Programming Puzzle
The final challenge involved decrypting a file protected with AES encryption.
**Key Discovery**
The AES key was partially known, with the final byte missing.

The correct key was recovered by brute-forcing the final byte and checking each decrypted output for the Windows PE file header ("MZ").

Recovered AES key (hex): 6c7578696f5f756e6c6f636b735f34e3
**Encryption Details**
- Encryption Mode: AES-CBC
- IV: 16 null bytes
- Ciphertext Encoding: Base64
After successful decryption, the output file was identified as a UPX-compressed PE32 executable.

**File Analysis Tools**
- hexdump
- file
- strings
These tools confirmed the executable structure and provided insight into the decrypted binary.

## Cryptanalysis Concepts Demonstrated
**Substitution vs Transposition Ciphers**
Substitution ciphers replace characters while preserving position, meaning letter frequency distributions remain similar to plaintext.

Transposition ciphers rearrange characters without altering them, meaning letter frequencies remain identical to the original text, but word structure is disrupted.

Techniques used to identify cipher types included:
- Frequency analysis
- Index of coincidence (IC)
- Pattern recognition

## Breaking Simple Ciphers
The general approach to breaking classical ciphers includes:
1. Identifying cipher type using statistical analysis
2. Performing frequency analysis
3. Testing common cipher techniques (Caesar, substitution, Vigenère)
4. Using automated cryptanalysis tools
5. Refining results through manual pattern recognition
This structured approach allows analysts to efficiently narrow down possible encryption methods and recover plaintext.

## Skills Demonstrated
- Cryptanalysis techniques
- Classical cipher decryption
- Frequency analysis
- Use of cryptographic analysis tools
- AES encryption analysis
- Binary inspection and reverse engineering basics

## Author
Durga Sai Sri Ramireddy </br>
Master’s Student - Cybersecurity </br>
University of Houston
