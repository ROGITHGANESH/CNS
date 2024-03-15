## EX. NO: 1(A) : IMPLEMENTATION OF CAESAR CIPHER
 

## AIM:

To implement the simple substitution technique named Caesar cipher using C language.

## DESCRIPTION:

To encrypt a message with a Caesar cipher, each letter in the message is changed using a simple rule: shift by three. Each letter is replaced by the letter three letters ahead in the alphabet. A becomes D, B becomes E, and so on. For the last letters, we can think of the
alphabet as a circle and "wrap around". W becomes Z, X becomes A, Y bec mes B, and Z
becomes C. To change a message back, each letter is replaced by the one three before it.

## EXAMPLE:



![image](https://github.com/Hemamanigandan/CNS/assets/149653568/eb9c6c43-8c80-4cdd-b9d4-91705a311c79)


## ALGORITHM:

### STEP-1: Read the plain text from the user.
### STEP-2: Read the key value from the user.
### STEP-3: If the key is positive then encrypt the text by adding the key with each character in the plain text.
### STEP-4: Else subtract the key from the plain text.
### STEP-5: Display the cipher text obtained above.


PROGRAM :-
#include <stdio.h>
#include <string.h>

// Function to perform Caesar cipher encryption
void encrypt(char message[], int key) {
    int i;
    char ch;
    
    for(i = 0; message[i] != '\0'; ++i) {
        ch = message[i];
        
        if(ch >= 'a' && ch <= 'z') {
            ch = ch + key;
            
            if(ch > 'z') {
                ch = ch - 'z' + 'a' - 1;
            }
            
            message[i] = ch;
        }
        else if(ch >= 'A' && ch <= 'Z') {
            ch = ch + key;
            
            if(ch > 'Z') {
                ch = ch - 'Z' + 'A' - 1;
            }
            
            message[i] = ch;
        }
    }
}

// Function to perform Caesar cipher decryption
void decrypt(char message[], int key) {
    int i;
    char ch;
    
    for(i = 0; message[i] != '\0'; ++i) {
        ch = message[i];
        
        if(ch >= 'a' && ch <= 'z') {
            ch = ch - key;
            
            if(ch < 'a') {	
                ch = ch + 'z' - 'a' + 1;
            }
            
            message[i] = ch;
        }
        else if(ch >= 'A' && ch <= 'Z') {
            ch = ch - key;
            
            if(ch < 'A') {
                ch = ch + 'Z' - 'A' + 1;
            }
            
            message[i] = ch;
        }
    }
}

int main() {
    char message[100];
    int key;
    
    printf("Enter a message: ");
    gets(message); // Input message
    
    printf("Enter key: ");
    scanf("%d", &key); // Input key
    
    // Encrypt the message
    encrypt(message, key);
    printf("Encrypted message: %s\n", message);
    
    // Decrypt the message
    decrypt(message, key);
    printf("Decrypted message: %s\n", message);
    
    return 0;
}



OUTPUT :-
![Screenshot (5)](https://github.com/kanmanikannu/CNS/assets/114866367/655f13b6-8505-4013-8d14-6fab04a9856c)

RESULT :
Thus, encryption and decryption of the given message by using Ceaser Cipher encryption algorithm is implemented successfully.


