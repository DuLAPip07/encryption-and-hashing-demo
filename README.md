# Demonstrating Confidentiality and Integrity Using SHA256 and OpenSSL
This project demonstrates two core principles of cybersecurity:

- Confidentiality through encryption
- Integrity through hashing

Using OpenSSL and SHA256, a simulated hospital patient record was protected against unauthorized access and tampering.

## Objectives

- Demonstrate file integrity verification using SHA256
- Demonstrate file confidentiality using OpenSSL encryption
- Show how file tampering affects hash values
- Explain real-world cybersecurity relevance

  ## Tools Used

- OpenSSL
- Windows Command Prompt
- SHA256
- AES-256 Encryption

  ## Methodology

### 1. Create Patient Record
A sample patient file containing mock sensitive information was created.

### 2. Generate SHA256 Hash
The file hash was generated to establish integrity.

### 3. Verify Integrity
The file was modified slightly and hashed again to demonstrate how even minor changes produce a completely different hash.

### 4. Encrypt File
The file was encrypted using AES-256 encryption via OpenSSL.

### 5. Decrypt File
The encrypted file was decrypted successfully to recover the original data.

## Commands Used

### Generate SHA256 Hash

```bash
certutil -hashfile patient_record.txt SHA256
```

### Encrypt File

```bash
openssl enc -aes-256-cbc -salt -in patient_record.txt -out encrypted_record.enc
```

### Decrypt File

```bash
openssl enc -d -aes-256-cbc -in encrypted_record.enc -out decrypted_record.txt
```

## Hashing vs Encryption

| Feature | Hashing | Encryption |
|---|---|---|
| Purpose | Integrity | Confidentiality |
| Reversible | No | Yes |
| Requires Key | No | Yes |
| Output | Hash Value | Ciphertext |

## Security Analysis

Healthcare organizations handle sensitive Personally Identifiable Information (PII) and Protected Health Information (PHI). 

Without encryption, attackers who gain access to files may read confidential records. Without integrity verification, unauthorized modifications may go undetected.

This project demonstrates how encryption protects confidentiality while hashing helps detect tampering.

## Conclusion

This project demonstrates practical implementations of confidentiality and integrity using industry-standard cryptographic techniques. Encryption ensures sensitive data remains private, while hashing helps detect unauthorized modifications.
