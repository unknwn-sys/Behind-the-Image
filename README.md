# Challenge Instructions: Discovering the Encoded Value

This document outlines a programming challenge focused on discovering a hidden encoded value within a Python script. Participants are required to modify an incomplete script, iterate through encoding processes, and utilize various tools to uncover the final flag.

---

## 1. Initial Script Analysis

The provided Python script generates encoded values using a combination of cryptographic hashing and encoding techniques, specifically:

- **SHA256**: A secure hash algorithm producing a 256-bit (32-byte) hash value.
- **SHA512**: A more robust secure hash algorithm, generating a 512-bit (64-byte) hash value.
- **Base64 Encoding**: A method to encode binary data into an ASCII string format.

The correct, hidden value is embedded within the program's logic and will be revealed upon successful completion of the script modification.

---

## 2. Your Task

To successfully complete this challenge, follow these steps:

1.  **Inspect the Script**: Carefully review the provided Python script to understand its current functionality.
2.  **Implement Iteration**: Add a loop to the script to enable multiple iterations of the encoding process.
3.  **Increment Counter**: Ensure that an iteration counter is increased with each loop cycle.
4.  **Print Generated Value**: Modify the script to print the generated encoded value during every iteration.
5.  **Stop at Correct Value**: The loop should terminate when the correct encoded value is discovered.

> **Hint:** The correct value is expected to appear at **iteration 28**.

---

## 3. Data Extraction and Decoding

Once you have obtained the string from iteration 28, you must extract the salt and the hash.

- **Structure**: The first 8 bytes represent the **salt**, and the following 32 bytes represent the **hash**.
- **Hint for Extraction**: Use the **xxd** method to extract and decode these components if the output is saved to a file (e.g., `raw.bin`).

---

## 4. Hash Cracking and Image Access

After extracting the components, you will need to crack the SHA256 hash.

- **Hash Format**: `sha256:600000:<salt>:<hash>`
- **Iterations**: 600,000
- **Cracking Tool Hint**: If using Hashcat, the specific mode is **10900**.
- **Password Usage**: The password recovered from this process is the key to an image file.

---

## 5. Metadata and Final Flag

The final stage involves analyzing the image and decoding the hidden content.

1.  **Metadata Analysis**: Check the image metadata for further hints.
    - **Recommended Tool**: `exiftool`
2.  **File Decoding**: Use the hint found in the metadata to get file with flag hash.
3. **final flag**: Decode the final file and retrieve the flag.

---

## References

No external references were used in the creation of this document.
