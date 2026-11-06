# Image Steganography Using C

## 1. Project Overview

Image Steganography is a technique used to hide secret information inside an image without making noticeable changes to its appearance.

This project is developed using the C programming language. It allows users to hide text messages inside BMP images and retrieve those messages whenever required.

The project uses the **Least Significant Bit (LSB) technique** to embed secret data into image pixels.

## 2. Features

- Hide secret text messages inside BMP images.
- Extract hidden messages from encoded images.
- Uses LSB-based image steganography.
- Uses a magic string to validate the decoding process.
- Supports command-line execution.
- Preserves the original image format.

## 3. Technologies Used

- Programming Language: C
- Compiler: GCC
- Image Format: BMP
- Concepts: File Handling, Bitwise Operations, LSB Steganography

## 4. Project Files

| File | Description |
|---|---|
| `test_encode.c` | Main program for encoding and decoding |
| `encode.c` | Contains encoding functions |
| `encode.h` | Encoding function declarations |
| `decode.c` | Contains decoding functions |
| `decode.h` | Decoding function declarations |
| `types.h` | Defines data types and status values |
| `beautiful.bmp` | Original image used for encoding |
| `secret.txt` | Contains the secret message |
| `steganography.exe` | Compiled executable |
| `stego.bmp` | Generated image containing the hidden message |
| `output.txt` | Recovered secret message after decoding |

## 5. How the Project Works

The project has two main operations:

1. Encoding – Hides a secret text file inside an image.
2. Decoding – Extracts the hidden text from the encoded image.

### A. Encoding Process

**Step 1: Prepare the files**

Make sure the following files are available in the project folder:

- `beautiful.bmp`
- `secret.txt`
- `steganography.exe`

Write your secret message inside `secret.txt` and save it.

**Step 2: Open PowerShell**

Open the project folder in File Explorer.

Click the address bar, type `powershell`, and press Enter.

**Step 3: Run the encoding command**

```powershell
.\steganography.exe -e beautiful.bmp secret.txt
```

**Step 4: Enter the magic string**

When prompted:

```text
Enter the secret code:
```

Enter:

```text
Ajnabee
```

**Step 5: Encoding output**

If encoding is successful, the program generates:

```text
stego.bmp
```

This image contains the hidden secret message.

### B. Decoding Process

**Step 1: Prepare the encoded image**

Make sure the following files are available in the same project folder:

- `steganography.exe`
- `stego.bmp`

**Step 2: Run the decoding command**

```powershell
.\steganography.exe -d stego.bmp output
```

**Step 3: Enter the magic string**

When prompted:

```text
Enter the secret code:
```

Enter the same magic string used during encoding:

```text
Ajnabee
```

**Step 4: Decoding output**

If decoding is successful, the terminal displays something similar to:

```text
Decode
Enter the secret code: Vedha
Decoded secret file size: 295 bytes
Decoding completed successfully
```

The recovered secret message is saved in:

```text
output.txt
```

## 6. How to View the Secret Message

The program saves the recovered message into `output.txt`. It does not automatically print the complete message in the terminal.

**Method 1: Open using Notepad**

Run this command in PowerShell:

```powershell
notepad output.txt
```

Notepad opens and displays the recovered secret message.

**Method 2: Display directly in the terminal**

Run:

```powershell
Get-Content output.txt
```

This prints the recovered secret message directly in PowerShell.

## 7. Compilation Instructions

If `steganography.exe` is not available, compile the source files using GCC.

Open PowerShell inside the folder containing the C source files and execute:

```powershell
gcc test_encode.c encode.c decode.c -o steganography.exe
```

Make sure GCC is installed and configured in the system PATH.

After successful compilation, use the encoding and decoding commands explained above.

## 8. Important Commands

| Operation | Command |
|---|---|
| Compile | `gcc test_encode.c encode.c decode.c -o steganography.exe` |
| Encode | `.\steganography.exe -e beautiful.bmp secret.txt` |
| Decode | `.\steganography.exe -d stego.bmp output` |
| View secret in Notepad | `notepad output.txt` |
| View secret in terminal | `Get-Content output.txt` |
| Check current directory | `pwd` |
| List files | `dir` |

## 9. Project Workflow

```text
secret.txt + beautiful.bmp
          |
          v
      ENCODING
          |
          v
      stego.bmp
          |
          v
       DECODING
          |
          v
       output.txt
          |
          v
  View Secret Message
```

## 10. Important Notes

- Use the same magic string during encoding and decoding.
- Keep the original BMP image and secret text file available for encoding.
- Share `stego.bmp` as a document or file attachment to avoid image compression.
- The receiver needs the compatible executable and the encoded BMP image to decode the message.
- The magic string is a validation mechanism, not strong encryption. This project demonstrates data hiding rather than secure encryption.

## 11. Conclusion

This project demonstrates how secret text messages can be embedded into BMP images and retrieved using C programming and the LSB steganography technique. It provides practical experience with file handling, bitwise operations, binary data processing, and command-line applications.