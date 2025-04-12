## RAIL FENCE CIPHER 
## AIM: 
To develop a simple C program to implement Rail fence Cipher. 
## ALGORITHM: 
STEP-1: 
Design the Rail fence cipher algorithm. 
STEP-2: 
Implementation using c program. 
STEP-3: 
1.Initialize a 2D array to store the encoded message. 
2.Fill the array by moving diagonally down and up in a zigzag pattern. 
3.Place characters in the rails as per the pattern until the message is fully encoded. 
4.Read characters row-wise to form the encrypted text. 
5.Print the encoded message. 
## PROGRAM: 
```

#include <stdio.h> 
#include <string.h> 
#include <stdlib.h> 
int main() { 
int i, j, len, rails, count; 
int code[100][1000]; 
char str[1000]; 
printf("Enter a Secret Message: "); 
fgets(str, sizeof(str), stdin); 
str[strcspn(str, "\n")] = '\0';  
len = strlen(str); 
printf("Enter number of rails: "); 
scanf("%d", &rails); 
for (i = 0; i < rails; i++) { 
        for (j = 0; j < len; j++) { 
            code[i][j] = 0; 
        } 
    } 
    count = 0; 
    j = 0; 
    while (j < len) { 
        if (count % 2 == 0) { 
            for (i = 0; i < rails && j < len; i++) { 
                code[i][j] = (int)str[j]; 
                j++; 
            } 
        } else { 
            for (i = rails - 2; i > 0 && j < len; i--) { 
                code[i][j] = (int)str[j]; 
                j++; 
            } 
        } 
        count++; 
    } 
    printf("\nEncoded Message: "); 
    for (i = 0; i < rails; i++) { 
        for (j = 0; j < len; j++) { 
            if (code[i][j] != 0) { 
                printf("%c", code[i][j]); 
            } 
        } 
    } 
 
    printf("\n"); 
    return 0; 
}
```
## OUTPUT: 

![Screenshot 2025-04-07 160553](https://github.com/user-attachments/assets/53a224f8-70db-4b53-b146-39ab87d72941)


## RESULT: 
The program is executed successfully. 
