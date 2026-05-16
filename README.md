# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

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
```
#include <stdio.h>
#include <math.h>

// Function for modular exponentiation
long long power(long long base, long long exp, long long mod)
{
    long long result = 1;

    while(exp > 0)
    {
        result = (result * base) % mod;
        exp--;
    }

    return result;
}

int main()
{
    long long p, g;
    long long a, b;
    long long A, B;
    long long keyA, keyB;

    // Public values
    p = 23;
    g = 5;

    // Private keys
    a = 6;
    b = 15;

    // Calculate public keys
    A = power(g, a, p);
    B = power(g, b, p);

    // Calculate shared secret keys
    keyA = power(B, a, p);
    keyB = power(A, b, p);

    printf("Public Prime Number (p) = %lld\n", p);
    printf("Primitive Root (g) = %lld\n", g);

    printf("\nPrivate Key of User A = %lld\n", a);
    printf("Private Key of User B = %lld\n", b);

    printf("\nPublic Key of User A = %lld\n", A);
    printf("Public Key of User B = %lld\n", B);

    printf("\nSecret Key computed by User A = %lld\n", keyA);
    printf("Secret Key computed by User B = %lld\n", keyB);

    return 0;
}
```


## Output:
<img width="1918" height="1088" alt="image" src="https://github.com/user-attachments/assets/aff3c7b9-d2b7-4800-848f-a219e4b0a9d2" />



## Result:
  The program is executed successfully

