# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm
## Name : VARUN JC
## Reg No : 21224240179
##
## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```C

#include <stdio.h>

int power(int a, int b, int p) {
    int result = 1;

    for (int i = 0; i < b; i++) {
        result = (result * a) % p;
    }

    return result;
}

int main() {
    int p = 23, g = 5;
    int a = 6, b = 15;
    int A, B, key1, key2;

    // Public keys
    A = power(g, a, p);
    B = power(g, b, p);

    // Secret key calculation
    key1 = power(B, a, p);
    key2 = power(A, b, p);

    printf("Public Key of A: %d\n", A);
    printf("Public Key of B: %d\n", B);

    printf("Secret Key of A: %d\n", key1);
    printf("Secret Key of B: %d\n", key2);

    return 0;
}

```


## Output:

<img width="1445" height="683" alt="image" src="https://github.com/user-attachments/assets/7d1012e0-73ea-4516-baa5-486edb75a43f" />


## Result:
  The program is executed successfully

