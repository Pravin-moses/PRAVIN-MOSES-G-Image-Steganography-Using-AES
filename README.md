Image Steganography with AES Encryption
What is Steganography?
Steganography is the art of hiding secret information inside a non-secret medium to prevent detection. Unlike cryptography, which scrambles data to make it unreadable, steganography conceals the very existence of the message. It is commonly used for secure communication, watermarking, and digital forensics.

History of Steganography
Ancient Methods
Steganography has been used for centuries, dating back to ancient Greece.

Early methods included:

Writing messages on wooden tablets and covering them with wax.

Hiding secret messages under new layers of ink on parchment.

Tattoo Steganography
One of the most fascinating historical uses of steganography was tattooing messages onto a messenger’s body.

Example: Greek ruler Histiaeus sent secret messages by tattooing them onto a slave’s shaved head. Once the hair grew back, the message remained hidden until the recipient shaved the messenger’s head again.

This method was an early form of biological steganography, using the human body as a medium for secret communication.

World War Tactics
During World War II, microdots—tiny photographs containing entire pages of information—were used to send secret messages hidden inside innocent-looking documents or letters.

Invisible inks and coded music notes were also employed to conceal messages from enemies.

Digital Steganography in Modern Times
With the rise of digital media, steganography evolved to hide information within images, videos, and audio files.

Today, it is used in cybersecurity, forensics, and covert communication.

What is AES Encryption?
AES (Advanced Encryption Standard) is a symmetric encryption algorithm widely used for securing sensitive data.

It is based on the Rijndael algorithm, designed by Vincent Rijmen and Joan Daemen.

Key Features:

Operates on fixed 128-bit blocks.

Supports 128-bit, 192-bit, or 256-bit keys.

Uses a combination of substitution, permutation, and key expansion to transform plaintext into an unreadable cipher.

Trusted by governments, financial institutions, and security professionals due to its resistance to brute-force attacks and efficiency.

AES Modes
AES operates in multiple modes, with Cipher Block Chaining (CBC) being one of the most commonly used for security.

In CBC mode:

Encryption is performed block by block.

Each block depends on the previous one, adding an extra layer of security compared to simpler modes like ECB (Electronic Codebook).

Least Significant Bit (LSB) Steganography
LSB Steganography is a technique used to hide data within digital images by modifying the least significant bits of pixel values.

Since these bits contribute the least to the overall color of a pixel, altering them has a negligible visual impact, making the changes imperceptible to the human eye.

How This Project Works
This project combines AES encryption with Least Significant Bit (LSB) steganography to securely hide messages inside images.

Encryption:

The input message is encrypted using AES-CBC mode.

A key is derived from a password using SHA-256 hashing.

Hiding in Image:

The encrypted message is embedded into an image using LSB steganography, ensuring minimal visual distortion.

Decryption:

The message is extracted from the image and decrypted using the correct password.

Why Use LSB When AES Alone Is Not Enough?
AES Alone:

Encrypts the message but doesn’t hide it.

If intercepted, attackers know that hidden communication exists.

Attackers can use brute-force methods to decrypt it if they suspect encryption.

LSB Alone:

Provides stealth by hiding the message in an image.

Even if someone accesses the image, they won’t notice that it contains hidden data.

The image looks the same because LSB changes only the least significant bits, which are imperceptible to the human eye.

AES + LSB = Security + Stealth:

AES secures the data (making it unreadable without a key).

LSB hides the encrypted data (so no one even suspects there’s a hidden message).

How AES and LSB Work Together in Steganography
AES Encryption
The secret message is encrypted using the AES-CBC (or AES-ECB) algorithm.

Padding is applied to make the message fit the AES block size (16 bytes).

The encrypted message is converted to binary format.

LSB Steganography
The encrypted binary data is embedded into the Least Significant Bits (LSB) of the image pixels.

Each pixel consists of Red, Green, and Blue (RGB) values.

The last bit of each channel (R, G, B) is replaced with a bit from the encrypted message.

Extraction and Decryption
The binary data is retrieved from the image’s pixel LSBs.

It is converted back into ciphertext and decrypted using AES, revealing the original message.

Why Combine AES with LSB?
AES provides security: Even if the image is accessed, the message remains encrypted.

LSB ensures stealth: Hidden data is imperceptible in the image.

Installation
Clone the Repository:

bash
Copy
git clone https://github.com/your-username/Image-Steganography-AES.git
cd Image-Steganography-AES
Install Dependencies:
Ensure Python is installed, then run:

bash
Copy
pip install pillow pycryptodome tkinter
Benefits of Using AES with LSB Steganography
Dual-Layer Security:

AES-CBC ensures the message is encrypted before being hidden, making it unreadable even if extracted.

LSB steganography provides covert transmission, preventing detection by attackers.

Enhanced Privacy & Confidentiality:

No Suspicion: Unlike normal encryption, where the presence of ciphertext is obvious, steganography keeps messages hidden in plain sight.

Protected Key Generation: SHA-256 is used to generate a strong encryption key from a password, preventing brute-force attacks.

Data Integrity & Authenticity:

AES encryption ensures that data remains unaltered during transmission.

Any modification to the image can corrupt the hidden message, alerting the receiver of tampering attempts.

Universal Compatibility & Easy Sharing:

Images appear normal, allowing safe sharing on social media, emails, and cloud storage.

Base64 encoding helps in embedding encrypted data without affecting image compatibility.

Efficient & Lossless Retrieval:

The original hidden message can be fully recovered without degrading the cover image.

Unlike watermarking, steganography preserves visual quality while ensuring data secrecy.

Summary
This project combines Advanced Encryption Standard (AES-CBC) encryption with Least Significant Bit (LSB) steganography to securely hide messages within images.

AES-CBC Encryption: Encrypts messages before embedding them to prevent unauthorized access.

LSB Steganography: Hides encrypted data within image pixels, making the message undetectable.

SHA-256 Hashing: Derives a strong encryption key from the user’s password.

Base64 Encoding: Converts encrypted data into a text format suitable for embedding.
