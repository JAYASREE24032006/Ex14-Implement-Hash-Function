# EX14 - HASH ALGORITHM
## AIM :
To generate a simple hash of a given message using a custom hash function.
## THEORM :
A hash algorithm is a mathematical function that transforms input data into a fixed-size string of characters, which typically appears random. This output, known as a hash value, serves as a unique identifier for the original data. Hash algorithms are widely used in data integrity verification, digital signatures, and password storage.
## ALGORITHM :
### STEP 1 : 
Input a message from the user.

### STEP 2 : 
Use a basic custom hash function that applies simple operations like XOR and addition on the characters of the message.

### STEP 3 : 
Convert the resulting hash into a hexadecimal format.

### STEP 4 : 
Display the computed hash to the user.

### STEP 5 :
Optionally verify the hash by recomputing it and comparing it with a received hash.

## PROGRAM :
```
#include <stdio.h>
#include <string.h>
void computeSimpleHash(const char *message, unsigned char *hash) 
{
    unsigned char temp = 0;
    for (int i = 0; message[i] != '\0'; i++)
    {
        temp = temp ^ message[i]; 
        temp += message[i];     
    }
    *hash = temp;
}
int main()
{
    char message[256];     
    unsigned char hash;    
    char receivedHash[3]; 
    printf("Enter the message: ");
    scanf("%s", message);
    computeSimpleHash(message, &hash);
    printf("Computed Hash (in hex): %02x\n", hash);
    printf("Enter the received hash (in hex): ");
    scanf("%s", receivedHash);
    unsigned int receivedHashValue;
    sscanf(receivedHash, "%02x", &receivedHashValue);
    if (hash == receivedHashValue) 
    {
        printf("Hash verification successful. Message is unchanged.\n");
    }
    else 
    {
        printf("Hash verification failed. Message has been altered.\n");
    }
    return 0;
}
```

## OUTPUT :

![image](https://github.com/user-attachments/assets/7e2672c6-6874-4466-a35a-c63a12b46be2)

## RESULT :
The program for generating and verifying a simple hash of a given message using a custom hash function was executed successfully.
