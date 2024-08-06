# Steganography Project

This project demonstrates how to encode and decode a secret message into an image using steganography and encryption. The project uses the Python libraries `cryptography` and `opencv-python` for encryption and image processing, respectively.

## Features

- Encrypts a message using a key derived from a password.
- Embeds the encrypted message into an image.
- Extracts and decrypts the message from the image using the same password.

## Requirements

- Python 3.x
- `cryptography` library
- `opencv-python` library

## Installation

1. Clone the repository or download the script.
2. Install the required libraries using pip:

   ```bash
   pip install cryptography opencv-python
   ```

## Usage

1. Place the image you want to use for embedding the message in the same directory as the script and name it `dn.jpg`.

2. Run the script:

   ```bash
   python stego.py
   ```

3. Follow the prompts:

   - Enter the secret message you want to send.
   - Enter a password for encryption.

4. The script will generate a key from the password, encrypt the message, and embed it in the image. The modified image will be saved as `Encryptedmsg.jpg` and will open automatically.

5. To decrypt the message, run the script again and follow the prompts:

   - Enter the password used for encryption.

## Example

### Encryption

```
Enter the secret message you want to send: Hello, World!
Enter the password: mypassword
*********
Starting decryption....
```

### Decryption

```
Enter passcode for Decryption: mypassword
Decrypted message: Hello, World!
```

## Notes

- Ensure the image `dn.jpg` is available in the same directory as the script.
- The password must be the same for both encryption and decryption processes to successfully retrieve the message.
- The modified image will have the same dimensions as the original image.

## File Description

- `stego.py`: Main script file containing the encryption, embedding, extraction, and decryption functions.

## How It Works

1. **Encryption**:
   - The message is encrypted using the `Fernet` module from the `cryptography` library.
   - The password is used to generate an encryption key.
   - The encrypted message is converted into a byte array.

2. **Embedding**:
   - The image is read and flattened into a 1D array.
   - The encrypted byte array is embedded into the flattened image array.
   - The image is reshaped back to its original dimensions and saved as `Encryptedmsg.jpg`.

3. **Decryption**:
   - The password is verified.
   - The encrypted byte array is extracted from the flattened image array.
   - The byte array is decrypted using the same key generated from the password.
   - The original message is displayed.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

- [cryptography](https://cryptography.io/en/latest/) library for encryption.
- [OpenCV](https://opencv.org/) library for image processing.
