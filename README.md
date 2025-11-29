# EX.-NO-1-C-IMPLEMENTATION-OF-HILL-CIPHER

## Name : Janardhan P
## Reg no : 212224040128

## AIM:
To write a C program to implement the hill cipher substitution techniques.

## ALGORITHM:

STEP-1: Read the plain text and key from the user.

STEP-2: Split the plain text into groups of length three.

STEP-3: Arrange the keyword in a 3*3 matrix.

STEP-4: Multiply the two matrices to obtain the cipher text of length three.

STEP-5: Combine all these groups to get the complete cipher text.

## PROGRAM: 
```c
#include <stdio.h>
#include <string.h>

int main() {
    unsigned int key[3][3] = { {6,24,1}, {13,16,10}, {20,17,15} };     
    unsigned int invKey[3][3] = { {8,5,10}, {21,8,21}, {21,12,8} };   
    unsigned int num[3], res[3];
    char msg[4]; 
    int i, j, t;

    printf("Enter a 3-letter word: ");
    scanf("%3s", msg);

    if(strlen(msg)!=3){
        printf("Error: Input must be exactly 3 letters.\n");
        return 1;
    }

   
    for(i=0;i<3;i++) num[i] = msg[i]-'A';

    for(i=0;i<3;i++){
        t=0;
        for(j=0;j<3;j++) t += key[i][j]*num[j];
        res[i] = t%26;
    }
    printf("\nEncrypted Cipher Text: ");
    for(i=0;i<3;i++) printf("%c", res[i]+'A');

    for(i=0;i<3;i++){
        t=0;
        for(j=0;j<3;j++) t += invKey[i][j]*res[j];
        num[i] = t%26;
    }
    printf("\nDecrypted Plain Text: ");
    for(i=0;i<3;i++) printf("%c", num[i]+'A');

    printf("\n");
    return 0;
}
```

## OUTPUT:
<img width="570" height="265" alt="image" src="https://github.com/user-attachments/assets/13011134-6005-4088-9d10-8f1cbd0a522c" />


## RESULT:
  Thus the hill cipher substitution technique had been implemented successfully.
