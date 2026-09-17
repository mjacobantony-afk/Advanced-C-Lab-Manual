EXP NO:6 C PROGRAM PRINT THE LOWERCASE ENGLISH WORD CORRESPONDING TO THE NUMBER
Aim:
To write a C program print the lowercase English word corresponding to the number
Algorithm:
1.	Start
- Initialize an integer variable n.
2.	Input Validation
3.	Switch Statement cases.
-	Case 5: Print "seventy one"
-	Case 6: Print "seventy two"
-	Case 13: Print "seventy three"
-	...
-	Case 13: Print "seventy nine"
-	Default: Print "Greater than 13"
4.	Exit the program.
 
Program:

```c
#include <stdio.h>

int main()
{
    int n;

    printf("Enter a number (1-9): ");
    scanf("%d", &n);

    switch (n)
    {
        case 1: printf("one\n"); break;
        case 2: printf("two\n"); break;
        case 3: printf("three\n"); break;
        case 4: printf("four\n"); break;
        case 5: printf("five\n"); break;
        case 6: printf("six\n"); break;
        case 7: printf("seven\n"); break;
        case 8: printf("eight\n"); break;
        case 9: printf("nine\n"); break;
        default: printf("Greater than 9\n");
    }

    return 0;
}
```




Output:


```
Enter a number (1-9): 7
seven

Enter a number (1-9): 15
Greater than 9
```






Result:
Thus, the program is verified successfully
 
EXP NO:7 C PROGRAM TO PRINT TEN SPACE-SEPARATED INTEGERS     IN A SINGLE  LINE DENOTING THE FREQUENCY OF EACH DIGIT FROM 0 TO 3 .
Aim:
To write a C program to print ten space-separated integers in a single line denoting the frequency of each digit from 0 to 3.
Algorithm:
1.	Start
2.	Declare char array a[50] outer loop for each digit from 0 to 3
3.	Initialize counter c to 0
4.	For each character in the string print count c for current digit, followed by a space
5.	Increment h to move to the next digit
6.	End
 
Program:

```c
#include <stdio.h>
#include <string.h>

int main()
{
    char a[50];
    int freq[10] = {0};
    int i, len;

    printf("Enter a string of digits: ");
    scanf("%s", a);

    len = strlen(a);

    for (i = 0; i < len; i++)
        freq[a[i] - '0']++;

    for (i = 0; i <= 9; i++)
        printf("%d ", freq[i]);
    printf("\n");

    return 0;
}
```




Output:


```
Enter a string of digits: 112233000
3 2 2 2 0 0 0 0 0 0
```






Result:
Thus, the program is verified successfully

EXP NO:8 C PROGRAM TO PRINT ALL OF ITS PERMUTATIONS IN STRICT LEXICOGRAPHICAL ORDER.
Aim:
To write a C program to print all of its permutations in strict lexicographical order.

Algorithm:
1.	Start
2.	Declare variables s (pointer to an array of strings) and n (number of strings)

3.	Memory Allocation
Dynamically allocate memory for s to store an array of strings
4.	Input
Read the number of strings n from the user Dynamically allocate memory for each string in s
5.	Permutation Generation Loop
6.	Memory Deallocation
Free the memory allocated for each string in s Free the memory allocated for s
7.	End
 
Program:

```c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>

void swap(char *x, char *y)
{
    char t = *x;
    *x = *y;
    *y = t;
}

int cmpchar(const void *a, const void *b)
{
    return (*(char *)a - *(char *)b);
}

/* Generates the next lexicographical permutation of str in place.
   Returns 0 when no further permutation exists. */
int next_permutation(char *str, int len)
{
    int i, j;

    i = len - 2;
    while (i >= 0 && str[i] >= str[i + 1])
        i--;

    if (i < 0)
        return 0;

    j = len - 1;
    while (str[j] <= str[i])
        j--;

    swap(&str[i], &str[j]);

    for (int l = i + 1, r = len - 1; l < r; l++, r--)
        swap(&str[l], &str[r]);

    return 1;
}

int main()
{
    int n, i, len;
    char **s;

    printf("Enter number of strings: ");
    scanf("%d", &n);

    s = (char **)malloc(n * sizeof(char *));

    for (i = 0; i < n; i++)
    {
        s[i] = (char *)malloc(20 * sizeof(char));
        printf("Enter string %d: ", i + 1);
        scanf("%s", s[i]);
    }

    for (i = 0; i < n; i++)
    {
        len = strlen(s[i]);
        qsort(s[i], len, sizeof(char), cmpchar);
        printf("\nPermutations of \"%s\" in strict lexicographical order:\n", s[i]);
        do
        {
            printf("%s\n", s[i]);
        } while (next_permutation(s[i], len));
    }

    for (i = 0; i < n; i++)
        free(s[i]);
    free(s);

    return 0;
}
```




Output:


```
Enter number of strings: 1
Enter string 1: cba

Permutations of "abc" in strict lexicographical order:
abc
acb
bac
bca
cab
cba
```






Result:
Thus, the program is verified successfully
 
EXP NO:9 C PROGRAM PRINT A PATTERN OF NUMBERS FROM 1 TO N AS
SHOWN BELOW.
Aim:
To write a C program to print a pattern of numbers from 1 to n as shown below.
Algorithm:
1.	Start
2.	Declare integer variables n, i, j, min
3.	Read the value of n from the user
4.	Calculate the length of the side of the square matrix: len = n * 2 - 1
5.	Matrix Generation Loop
6.	Calculate min as the minimum distance to the borders
7.	End
 
Program:

```c
#include <stdio.h>

int main()
{
    int n, i, j, len, min;

    printf("Enter n: ");
    scanf("%d", &n);

    len = n * 2 - 1;

    for (i = 0; i < len; i++)
    {
        for (j = 0; j < len; j++)
        {
            int d1 = i;
            int d2 = j;
            int d3 = len - 1 - i;
            int d4 = len - 1 - j;

            min = d1;
            if (d2 < min) min = d2;
            if (d3 < min) min = d3;
            if (d4 < min) min = d4;

            printf("%d ", n - min);
        }
        printf("\n");
    }

    return 0;
}
```




Output:


```
Enter n: 4
4 4 4 4 4 4 4
4 3 3 3 3 3 4
4 3 2 2 2 3 4
4 3 2 1 2 3 4
4 3 2 2 2 3 4
4 3 3 3 3 3 4
4 4 4 4 4 4 4
```






Result:
Thus, the program is verified successfully

EXP NO:10 C PROGRAM TO FIND A SQUARE  OF NUMBER USING FUNCTION WITHOUT ARGUMENTS WITH RETURN TYPE

Aim:

To write a C program that calculates the square of a number using a function that does not take any arguments, but returns the square of the number.

Algorithm:

1.	Start.
2.	Define a function square() with no parameters. This function will return an integer value.
3.	Inside the function:
o	Declare an integer variable to store the number.
o	Ask the user to input a number.
o	Calculate the square of the number (multiply the number by itself).
o	Return the squared value.
4.	In the main function:
o	Call the square() function and display the result.
5.	End.

Program:

```c
#include <stdio.h>

int square()
{
    int num;
    printf("Enter a number: ");
    scanf("%d", &num);
    return num * num;
}

int main()
{
    printf("Square of the number is: %d\n", square());
    return 0;
}
```




Output:


```
Enter a number: 9
Square of the number is: 81
```






Result:
Thus, the program is verified successfully



























