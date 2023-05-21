# StegClone

## Project Description

This script will embed secret images into source images. It uses the LSB technique presented in Steghide, a popular steganography tool that supports this operation. For more information regarding Steghide, please refer to this [link](https://github.com/StefanoDeVuono/steghide).

### Algorithm steps:
1. Compress the secret image. This is to ensure as little size gap as possible between the input image and the secret image.
   - Compression is done by using the zlib standard algorithm. This can be further optimized or implemented from scratch, depending on the project requirements. (TODO: Ask for clarification)

2. Encrypt the secret image. This adds a layer of security to the embedding process.
   - Right now, encryption is handled simply by using a XOR byte-wise function. (TODO: Add more complex security mechanisms, like RSA, public-private key)

3. Embed the image using the LSB technique.

4. Save the new file.

* For retrieval, the algorithm steps are reversed.


## Requirements

- Python 3.x
- OpenCV (opencv-python)
- NumPy (numpy)
- Argparse (argparse)
- Pyfiglet (pyfiglet)



## Installation

1. Make sure you have Python 3.x installed on your system. If not, you can download it from the official Python website: [Python.org](https://www.python.org/downloads/).

2. Install the required dependencies by running the following command:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

To run the script, use the following command:
   
   ```bash
       python3 StegClone.py <action> <image_path> <secret_path> 
            [--key <encryption_key>] [--output <output_path>]
   ```


## Examples

- Embedding a secret image:

```bash
python3 StegClone.py embed cover_image.png secret_image.png --key myencryptionkey --output stego_image.png
```

- Decoding a secret image:
```bash
python3 StegClone.py decode stego_image.png --output decoded.png
```


## Credits

This script was developed as part of school assignment for Image Processing.. It utilizes the LSB technique and is inspired by Steghide, a popular steganography tool. 
