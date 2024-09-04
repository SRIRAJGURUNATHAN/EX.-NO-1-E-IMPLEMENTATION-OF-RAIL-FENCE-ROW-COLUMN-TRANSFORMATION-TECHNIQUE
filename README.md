# EX.-NO-1-E-IMPLEMENTATION-OF-RAIL-FENCE-ROW-COLUMN-TRANSFORMATION-TECHNIQUE

## AIM:
  To write a C program to implement the rail fence transposition technique.
  
## ALGORITHM:

STEP-1: Read the Plain text.

STEP-2: Arrange the plain text in row columnar matrix format.

STEP-3: Now read the keyword depending on the number of columns of the plain text.

STEP-4: Arrange the characters of the keyword in sorted order and the corresponding columns of the plain text.

STEP-5: Read the characters row wise or column wise in the former order to get the cipher text.

## PROGRAM:
```
#include <stdio.h>
#include <string.h>

int main() {
    int i, j, k, l;
    char a[20], c[20], d[20];

    printf("\n\t\t RAIL FENCE TECHNIQUE");
    printf("\n\nEnter the input string: ");
    fgets(a, sizeof(a), stdin);
    a[strcspn(a, "\n")] = '\0';  // Remove the newline character from fgets

    l = strlen(a);

    // Encrypt using Rail Fence technique
    for (i = 0, j = 0; i < l; i++) {
        if (i % 2 == 0) {
            c[j++] = a[i];
        }
    }
    for (i = 0; i < l; i++) {
        if (i % 2 == 1) {
            c[j++] = a[i];
        }
    }
    c[j] = '\0';  // Null-terminate the ciphertext

    printf("\nCipher text after applying rail fence: %s", c);

    // Decrypt the text
    if (l % 2 == 0) {
        k = l / 2;
    } else {
        k = (l / 2) + 1;
    }

    for (i = 0, j = 0; i < k; i++) {
        d[j] = c[i];
        j += 2;
    }
    for (i = k, j = 1; i < l; i++) {
        d[j] = c[i];
        j += 2;
    }
    d[l] = '\0';  // Null-terminate the decrypted text

    printf("\nText after decryption: %s\n", d);

    return 0;
}
```
## OUTPUT:
![image](https://github.com/user-attachments/assets/bd9acd28-accf-400b-a808-0e32a938a9af)

## RESULT:
  Thus the rail fence algorithm had been executed successfully.
