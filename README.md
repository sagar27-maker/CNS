#include <stdio.h>


long long power(long long base, long long exp, long long mod) {
    long long result = 1;
       while (exp > 0) {
        result = (result * base) % mod;
        exp--;
    }
return result;
}

int main() {
    int p = 61, q = 53;
    int n = p * q;             
    int phi = (p - 1) * (q - 1);
    int e = 7;   
    int d = 1783;   

    int message = 42;

    long long encrypted = power(message, e, n);


    long long decrypted = power(encrypted, d, n);

    printf("Public Key: (%d, %d)\n", e, n);
    printf("Private Key: (%d, %d)\n", d, n);
    printf("Original Message: %d\n", message);
    printf("Encrypted Message: %lld\n", encrypted);
    printf("Decrypted Message: %lld\n", decrypted);

    return 0;
}
