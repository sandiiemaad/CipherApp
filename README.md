# **🔐 Java Text Encryption & Decryption Program**

This **Java program** provides **encryption and decryption** for text using **three classic cipher methods**: **Atbash**, **Affine**, and **Morse Code**.  
The project is structured into multiple classes, with each cipher type having its own **dedicated encryption/decryption class**, and a **main `Cipher` class** that handles user interaction via a console-based menu.

---

## **🔑 Cipher Methods**

### **1. Atbash Cipher**
- **AtbashEncryption**: Encrypts text by **reversing the alphabet** (A ↔ Z, B ↔ Y, etc.).  
- **DecryptionAtbash**: Uses the **same logic** since Atbash is symmetric (encryption and decryption are identical).

---

### **2. Affine Cipher**
- **AffineCipherEncryption**: Encrypts letters using the formula:  
  `E(x) = (key1 * x + key2) % 26`
- **AffineCipherDecryption**: Decrypts text using the modular inverse of `key1` and the formula:  
  `D(x) = key1⁻¹ * (x - key2) % 26`
- Includes a method to **compute the modular inverse (`modInverse`)** for decryption.

---

### **3. Morse Code**
- **MorseCodeEncryption**: Converts each letter to its **Morse code equivalent** (e.g., `A → ".-"`, `B → "-..."`).

---

## **🖥 Main Cipher Class**
- Acts as the **entry point** for the program.
- Provides a **console-based menu** for user interaction.
- Validates user input and routes the user to the **appropriate cipher type** for encryption or decryption.
- The program **loops continuously** until the user chooses to exit.

---

## **📌 Notes**
- Focuses on **character-level transformations**.
- Handles **letters and spaces only** (ignores numbers and symbols).
- Performs **input validation** for clean and predictable behavior.
