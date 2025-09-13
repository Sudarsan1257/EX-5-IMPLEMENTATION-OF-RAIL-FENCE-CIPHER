## EX : 5 IMPLEMENTATION OF RAIL FENCE CIPHER

## AIM:

To develop a simple C program to implement Rail Fence Cipher.


## ALGORITHM:
#### 1.	To perform the Encryption Process
#### •	Input the plaintext string from the user.
#### •	Calculate the length of the plaintext.
#### •	Create the ciphertext using two rails:
#### a.	First, collect characters at even indices (i.e., 0, 2, 4, …).
#### b.	Then, collect characters at odd indices (i.e., 1, 3, 5, …).
#### c.	Combine both parts to form the ciphertext.
#### •	Display the encrypted ciphertext.

#### 2.	To perform the Decryption Process:
#### •	Calculate the length of the ciphertext.
#### •	Find the midpoint:
#### ◦	a. If the length is even, midpoint = length / 2.
#### ◦	b. If the length is odd, midpoint = (length / 2) + 1.
#### •	Reconstruct the original message:
#### a.	Take the first half as characters from even positions.
#### b.	Take the second half as characters from odd positions.
#### c.	Merge both using alternating positions.

#### 3.	Display the decrypted plaintext.



## PROGRAM:
```
#include <stdio.h>
#include <string.h>

int main()
{
    int i, j = 0, k, l;
    char a[20], c[20], d[20];

    printf("\n\t\tRAIL FENCE TECHNIQUE\n");
    printf("\nEnter the input string: ");
    fgets(a, sizeof(a), stdin);
    a[strcspn(a, "\n")] = '\0'; // Remove newline if present

    l = strlen(a);

    // Encryption: collect even indices first
    for (i = 0; i < l; i++) {
        if (i % 2 == 0) {
            c[j++] = a[i];
        }
    }
    // Then collect odd indices
    for (i = 0; i < l; i++) {
        if (i % 2 == 1) {
            c[j++] = a[i];
        }
    }
    c[j] = '\0';

    printf("\nCipher text after applying rail fence: %s\n", c);

    // Decryption
    if (l % 2 == 0)
        k = l / 2;
    else
        k = (l / 2) + 1;

    for (i = 0, j = 0; i < k; i++) {
        d[j] = c[i];
        j += 2;
    }
    for (i = k, j = 1; i < l; i++) {
        d[j] = c[i];
        j += 2;
    }
    d[l] = '\0';

    printf("\nText after decryption: %s\n", d);

    return 0;
}
```
## OUTPUT:
<img width="931" height="520" alt="Screenshot 2025-09-13 133444" src="https://github.com/user-attachments/assets/25c5a479-d480-4677-bf88-9efe992cb43d" />

## RESULT:
The program implementing the Rail Fence cipher for encryption and decryption has been successfully	executed,	and	the	results	have	been	verified.
