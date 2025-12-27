# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
## 5. Implementation of one-dimensional array and multidimensional array.
## 6. Implementation of string manipulation.
# Ex.No:11
  Formulate a C program to convert a given decimal number into its binary equivalent and display it.
# Date : 
# Aim:
To formulate a C program to convert a decimal number into its binary equivalent and display it.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare variables: num (input number), rem (remainder), binary[] (array to store binary digits), and loop counters i and k.
### Step 4: 
  Read the decimal number from the user.
### Step 5: 
  Initialize i = 0.
### Step 6: 
  Repeat while num > 0:
  Divide num by 2 and store the remainder in binary[i].
  Increment i.
  Update num = num / 2.
### Step 7: 
  Display the binary digits in reverse order (from i-1 down to 0).
### Step 8: 
   Stop
# Program:
#include <stdio.h>

int main()
{
    int num, binary[32], i = 0;

    printf("Enter a decimal number: ");
    scanf("%d", &num);

    if (num == 0)
    {
        printf("Binary equivalent: 0");
        return 0;
    }

    while (num > 0)
    {
        binary[i] = num % 2;
        num = num / 2;
        i++;
    }

    printf("Binary equivalent: ");
    for (int j = i - 1; j >= 0; j--)
    {
        printf("%d", binary[j]);
    }

    return 0;
}

# Output:
<img width="1627" height="652" alt="image" src="https://github.com/user-attachments/assets/6d801226-3fbe-444b-a7b7-c65a035a95ba" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:12
  Develop a C program to read a matrix and find its saddle point. A saddle point is an element that is the minimum in its row and also the maximum in its column. If such an element exists, display its position and value.
# Date : 
# Aim:
  To develop a C program that inputs a matrix, checks each row for its minimum element, verifies whether that element is also the maximum in its corresponding column, and displays the saddle point and its position if it exists.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
 Declare variables i, j, k, m, min, max and a position array pos[2][2].
### Step 4: 
 Read the order of the square matrix m.
### Step 5: 
 Declare an m × m matrix and read its elements.
### Step 6: 
 Display the matrix.
### Step 7: 
   For each row `i` from `0` to `m−1`:
- **Step 7.1:** Set `min` as the first element of the row.  
- **Step 7.2:** Scan the row to find its minimum element and store its position in `pos[0]`.  
- **Step 7.3:** Let `j` be the column of this minimum element.  
- **Step 7.4:** Set `max` as the first element of column `j`.  
- **Step 7.5:** Scan column `j` to find its maximum element and store its position in `pos[1]`.  
### Step 8: 
  Check if the row minimum equals the column maximum:
- If `min == max` **and their positions match**, then the element is a **saddle point**.
- Print the saddle point value and its position.
### Step 9: 
  Stop
# Program:
#include <stdio.h>

int main()
{
    int m, n;
    int matrix[10][10];
    int saddleFound = 0;

    printf("Enter number of rows and columns: ");
    scanf("%d %d", &m, &n);

    printf("Enter the matrix elements:\n");
    for (int i = 0; i < m; i++)
    {
        for (int j = 0; j < n; j++)
        {
            scanf("%d", &matrix[i][j]);
        }
    }

    for (int i = 0; i < m; i++)
    {
        int min = matrix[i][0];
        int col_index = 0;

        /* Find minimum in the current row */
        for (int j = 1; j < n; j++)
        {
            if (matrix[i][j] < min)
            {
                min = matrix[i][j];
                col_index = j;
            }
        }

        /* Check if it is maximum in its column */
        int isSaddle = 1;
        for (int k = 0; k < m; k++)
        {
            if (matrix[k][col_index] > min)
            {
                isSaddle = 0;
                break;
            }
        }

        if (isSaddle)
        {
            printf("Saddle point found at position (%d, %d) with value %d\n",
                   i, col_index, min);
            saddleFound = 1;
        }
    }

    if (!saddleFound)
    {
        printf("No saddle point found in the matrix.\n");
    }

    return 0;
}

# Output:
<img width="1628" height="658" alt="image" src="https://github.com/user-attachments/assets/113d7b90-4a25-4eed-9596-056f7cdc79e1" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:13
  Formulate a C program to reverse a string entered by the user and display the reversed string.
# Date : 
# Aim:
  To formulate a C program that reads a string from the user, reverses it, and prints the reversed string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare two character arrays: `s` to store the input string and `d` to store the reversed string.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]s", s);`
### Step 5: 
  Find the length of the string `s` by traversing it until the null character `'\0'` is encountered.
### Step 6: 
  Initialize a counter `j` for the reversed string.
### Step 7: 
  Copy characters from the end of `s` to the beginning of `d` using a loop until all characters are copied in reverse order.
### Step 8: 
  Terminate the reversed string `d` with the null character `'\0'`.
### Step 9: 
  Print the reversed string.
### Step 10: 
  Stop
# Program:
#include <stdio.h>

int main()
{
    char str[100];
    int i, length = 0;
    char temp;

    printf("Enter a string: ");
    scanf("%s", str);  
    while (str[length] != '\0')
    {
        length++;
    }

    for (i = 0; i < length / 2; i++)
    {
        temp = str[i];
        str[i] = str[length - i - 1];
        str[length - i - 1] = temp;
    }

    printf("Reversed string: %s", str);

    return 0;
}

# Output:
<img width="1627" height="651" alt="image" src="https://github.com/user-attachments/assets/85853177-fbf4-4613-aafb-2fe103c98179" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:14
  Formulate a C program to count the frequency of each character in a given string and display the count of every character.
# Date : 
# Aim:
  To formulate a C program that accepts a string from the user and calculates the frequency of each character in the string.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `s[100]` to store the input string, an integer array `visited[256]` initialized to `0`, and variables `i`, `n`, and `count`.
### Step 4: 
  Read the string from the user using `scanf("%[^\n]", s);`
### Step 5: 
  Calculate the length of the string using `strlen(s)` and store it in `n`.
### Step 6: 
 For each character `s[i]` in the string (from `i = 0` to `n - 1`):
 - If `visited[(unsigned char)s[i]] == 0` (character not yet counted):  
  - Initialize `count = 0`.  
  - Loop through the string again and increment `count` for every occurrence of `s[i]`.  
  - Print `s[i]` and its count.  
  - Set `visited[(unsigned char)s[i]] = 1` to mark it as counted.
### Step 7: 
  Repeat Step 6 for all characters.
### Step 8:
  Stop
# Program:
#include <stdio.h>

int main()
{
    char str[200];
    int freq[256] = {0};
    int i;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    
    for (i = 0; str[i] != '\0'; i++)
    {
        freq[(unsigned char)str[i]]++;
    }

    printf("\nCharacter Frequency:\n");
    for (i = 0; i < 256; i++)
    {
        if (freq[i] > 0 && i != '\n')
        {
            printf("'%c' = %d\n", i, freq[i]);
        }
    }

    return 0;
}

# Output:
<img width="1635" height="647" alt="image" src="https://github.com/user-attachments/assets/7a2a5849-c364-460d-8166-e10d33151563" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.


# 19AI304-Fundamentals-of-C-Programming-2025-Odd-M3
# IAPR-3- Module 3 - FoC
# Ex.No:15
  Formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Date : 
# Aim:
  To formulate a C program to remove duplicate words from a given string and display the string with only unique words.
# Algorithm:
### Step 1:
  Start
### Step 2: 
  Include the standard input-output library: #include<stdio.h>.
### Step 3: 
  Declare a character array `str` to store the input string and a 2D array `words` to store individual words.
### Step 4: 
  Read the input string using `scanf("%[^\n]s", str);`
### Step 5: 
 Split the string into words:
 - Traverse the string character by character.  
 - When a space is encountered, terminate the current word with `'\0'` and move to the next row in `words`.  
 - Otherwise, copy the character into the current word.
### Step 6: 
  Compare each word with all other words to detect duplicates:
  - If a duplicate is found, mark it by setting the first character to `'\0'`.
### Step 7: 
  Print all words that are not marked as duplicates.
### Step 8: 
  Stop
# Program:
#include <stdio.h>
#include <string.h>

int main()
{
    char str[200], temp[200];
    char *words[100];
    int wordCount = 0;
    int i, j, isDuplicate;

    printf("Enter a string: ");
    fgets(str, sizeof(str), stdin);

    
    str[strcspn(str, "\n")] = '\0';

   
    char *token = strtok(str, " ");
    while (token != NULL)
    {
      
        isDuplicate = 0;
        for (i = 0; i < wordCount; i++)
        {
            if (strcmp(words[i], token) == 0)
            {
                isDuplicate = 1;
                break;
            }
        }

        if (!isDuplicate)
        {
            words[wordCount] = token;
            wordCount++;
        }

        token = strtok(NULL, " ");
    }

    printf("\nString with unique words:\n");
    for (i = 0; i < wordCount; i++)
    {
        printf("%s ", words[i]);
    }

    return 0;
}

# Output:
<img width="1628" height="648" alt="image" src="https://github.com/user-attachments/assets/ed820ab1-d39b-45a0-a851-14c3c7c67ef6" />

# Result: 
Thus, the program was implemented and executed successfully, and the required output was obtained.

