# Ex-4 Rail-Fence-Program

# IMPLEMENTATION OF RAIL FENCE – ROW & COLUMN TRANSFORMATION TECHNIQUE

# AIM:

# To write a C program to implement the rail fence transposition technique.

# DESCRIPTION:

In the rail fence cipher, the plain text is written downwards and diagonally on successive "rails" of an imaginary fence, then moving up when we reach the bottom rail. When we reach the top rail, the message is written downwards again until the whole plaintext is written out. The message is then read off in rows.

# ALGORITHM:

STEP-1: Read the Plain text.
STEP-2: Arrange the plain text in row columnar matrix format.
STEP-3: Now read the keyword depending on the number of columns of the plain text.
STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.
STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

# PROGRAM
```

#include <stdio.h>
#include <stdlib.h>
#include <string.h>

// Function to perform Caesar Cipher encryption
void caesarEncrypt(char *text, int key) {
    for (int i = 0; text[i] != '\0'; i++) {
        char c = text[i];
        if (c >= 'A' && c <= 'Z') {
            text[i] = 'A' + ((c - 'A' + key) % 26 + 26) % 26;
        } else if (c >= 'a' && c <= 'z') {
            text[i] = 'a' + ((c - 'a' + key) % 26 + 26) % 26;
        }
    }
}

// Function to perform Caesar Cipher decryption
void caesarDecrypt(char *text, int key) {
    caesarEncrypt(text, -key);
}

int main() {
    char message[100];
    int key;

    printf("Enter the message to encrypt: ");
    fgets(message, sizeof(message), stdin);

    // Remove trailing newline from fgets
    message[strcspn(message, "\n")] = '\0';

    printf("Enter the Caesar Cipher key (an integer): ");
    if (scanf("%d", &key) != 1) {
        printf("Invalid input! Please enter an integer.\n");
        return 1;
    }

    caesarEncrypt(message, key);
    printf("Encrypted Message: %s\n", message);

    caesarDecrypt(message, key);
    printf("Decrypted Message: %s\n", message);

    return 0;
}

```
# OUTPUT
<img width="661" height="161" alt="image" src="https://github.com/user-attachments/assets/26ecaac3-f55d-41e1-ab7b-11b575057f92" />

# RESULT
Rail-Fence-Program is performed successfully
