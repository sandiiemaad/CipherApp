This Java program provides encryption and decryption for text using three classic cipher methods: Atbash, Affine, and Morse Code. It's structured into multiple classes with each cipher type having its own dedicated encryption/decryption class, and a main Cipher class that handles user interaction via console menus.

1. Atbash Cipher:
AtbashEncryption: Encrypts text using the Atbash cipher by reversing the alphabet (A ↔ Z, B ↔ Y, etc.).

DecryptionAtbash: Mirrors the same logic since Atbash is symmetric (same process for encryption and decryption).

2. Affine Cipher:
AffineCipherEncryption: Encrypts letters using the formula: E(x) = (key1 * x + key2) % 26.

AffineCipherDecryption: Decrypts using modular inverse of key1 and the formula: D(x) = key1⁻¹ * (x - key2) % 26.

Includes a method to compute the modular inverse (modInverse).

3. Morse Code:
MorseCodeEncryption: Converts each letter to its Morse code equivalent (e.g., A → ".-", B → "-...").

4. Cipher class:
Acts as the entry point with a console menu.

Handles user input and validates it.

Routes the user to appropriate cipher type for encryption or decryption.

The program performs input validation and continues looping until the user chooses to exit. It focuses on character-level transformations and avoids symbols or numbers beyond letters and spaces.
