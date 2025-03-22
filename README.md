# RSA Hybrid Encryption Tool

A secure file encryption and decryption tool with graphical user interface that uses RSA public-key cryptography combined with AES symmetric encryption for optimal security and performance.

## Features

- **Hybrid Encryption**: Uses RSA (2048-bit) for secure key exchange and fast AES (256-bit) for file encryption
- **User-friendly GUI**: Easy-to-use graphical interface with tabs for key management, encryption, and decryption
- **Key Management**: Generate, save, and load RSA key pairs
- **File Operations**: Encrypt and decrypt files of any type with a few clicks
- **Security**: Industry-standard cryptographic algorithms from the Python cryptography library

## Installation

### Prerequisites

- Python 3.6 or higher
- Required Python packages:
  - cryptography
  - tkinter (usually comes with Python)

### Setup

1. Clone or download this repository
2. Install required dependencies:

```bash
pip install cryptography
```

3. Run the application:

```bash
python rsa_encryption_gui.py
```

## Usage

### Key Management

1. **Generate a Key Pair**:
   - Go to the "Key Management" tab
   - Specify paths for saving private and public keys
   - Click "Generate Keys"
   - Keep your private key secure and never share it

### Encrypting Files

1. Go to the "Encrypt" tab
2. Select a public key (yours or a recipient's)
3. Choose the file you want to encrypt
4. (Optional) Specify an output path for the encrypted file
5. Click "Encrypt"
6. The encrypted file will be saved (by default with .encrypted extension)

### Decrypting Files

1. Go to the "Decrypt" tab
2. Select your private key (you can only decrypt files encrypted with your corresponding public key)
3. Choose the encrypted file
4. (Optional) Specify an output path for the decrypted file
5. Click "Decrypt"
6. The decrypted file will be saved (by default with .decrypted extension)

## How It Works

This tool uses a hybrid encryption approach:

1. **Key Exchange**: RSA asymmetric encryption securely transfers the encryption key
2. **File Encryption**: Fast AES symmetric encryption for the actual file data
3. **Process**:
   - A random AES key is generated for each encryption
   - The file is encrypted with this AES key
   - The AES key is encrypted with the recipient's RSA public key
   - Both the encrypted file and encrypted key are stored together
   - Decryption requires the private RSA key to recover the AES key

## Security Considerations

- **Private Key Protection**: Keep your private key secure. Anyone with your private key can decrypt your files.
- **Key Size**: Uses 2048-bit RSA keys, which offers strong security for general use.
- **Modern Algorithms**: Uses OAEP padding for RSA and CBC mode with PKCS7 padding for AES.
- **Unencrypted Keys**: Note that private keys are stored unencrypted by default. For production use, consider implementing password protection.

## Command Line Interface

For advanced users, the application also supports command-line operation. Run the original script without GUI:

```bash
python rsa_hybrid_cipher.py --help
```

## License

[MIT License](LICENSE)

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## Acknowledgments

- This tool uses the [cryptography](https://cryptography.io/) library, which provides cryptographic recipes and primitives.
