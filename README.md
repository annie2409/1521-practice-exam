# 1521-practice-exam

---

### **Variation 1: Count One Bits**
Write a function `count_one_bits(uint32_t x)` that counts the number of one bits in a 32-bit unsigned integer. For example:

**Code Example:**
```c
#include <stdio.h>
#include <stdint.h>

int count_one_bits(uint32_t x) {
    // TODO
    return 0;
}
```

**Example Input and Output:**
```
Input: 0xFFFFFFFF (4294967295)
Output: 32

Input: 0x12345678 (305419896)
Output: 13

Input: 0x00000000 (0)
Output: 0
```

---

### **Variation 2: Count Alternating Bit Patterns**
Write a function `count_alternating_bits(uint32_t x)` that counts the number of alternating bit transitions (e.g., 01 or 10) in the binary representation of a 32-bit unsigned integer. For example:

**Code Example:**
```c
#include <stdio.h>
#include <stdint.h>

int count_alternating_bits(uint32_t x) {
    // TODO
    return 0;
}
```

**Example Input and Output:**
```
Input: 0xAAAAAAAA (2863311530)
Output: 31

Input: 0x55555555 (1431655765)
Output: 31

Input: 0xFFFFFFFF (4294967295)
Output: 0
```

---

### **Variation 3: Count Leading Zero Bits**
Write a function `count_leading_zero_bits(uint32_t x)` that counts the number of leading zero bits (from the most significant bit) in a 32-bit unsigned integer. For example:

**Code Example:**
```c
#include <stdio.h>
#include <stdint.h>

int count_leading_zero_bits(uint32_t x) {
    // TODO
    return 0;
}
```

**Example Input and Output:**
```
Input: 0x00000001 (1)
Output: 31

Input: 0x80000000 (2147483648)
Output: 0

Input: 0x12345678 (305419896)
Output: 3
```

---

### Problem Statement: Reverse Bytes of a 32-bit Integer
You need to reverse the order of bytes in a 32-bit integer without altering the order of bits within each byte.

---

### Corresponding C Code:
```c
#include <stdio.h>
#include <stdint.h>

uint32_t reverse_bytes(uint32_t value) {
    return ((value & 0x000000FF) << 24) |
           ((value & 0x0000FF00) << 8) |
           ((value & 0x00FF0000) >> 8) |
           ((value & 0xFF000000) >> 24);
}

int main(int argc, char *argv[]) {
    if (argc != 2) {
        fprintf(stderr, "Usage: %s <hexadecimal number>\n", argv[0]);
        return 1;
    }

    uint32_t input;
    sscanf(argv[1], "%x", &input);

    uint32_t result = reverse_bytes(input);

    printf("reverse_bytes(0x%08X) returned 0x%08X\n", input, result);
    return 0;
}
```

---

### Variations of the Problem:

---

### Variation 1: Reverse Every Nibble
Reverse the nibbles (4-bit chunks) in the 32-bit number instead of bytes.

**Example Input and Output:**
```
Input: 0x12345678
Output: 0x87654321

Input: 0xA0B1C2D3
Output: 0x3D2C1B0A
```

---

### Variation 2: Swap Endianness of a 64-bit Number
Reverse bytes in a 64-bit number to convert between little-endian and big-endian formats.

**Example Input and Output:**
```
Input: 0x123456789ABCDEF0
Output: 0xF0DEBC9A78563412

Input: 0x1122334455667788
Output: 0x8877665544332211
```

---

### Variation 3: Reverse Only the Lower 16 Bits
Reverse the bytes of only the lower 16 bits of a 32-bit number.

**Example Input and Output:**
```
Input: 0x12345678
Output: 0x12347856

Input: 0xAABBCCDD
Output: 0xAABBDDCC
```


### Questions: Translating C Code with 2D Arrays and Nested Loops to MIPS Assembly

---

### Question 1: Calculate the Sum of Elements in a 2D Array
Write the MIPS assembly code to compute the sum of all elements in a 2D array of size \( n \times m \). The C code is provided below:

```c
int sum_2D_array(int array[3][3]) {
    int sum = 0;
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (array[i][j] > 0) {
                sum += array[i][j];
            }
        }
    }
    return sum;
}
```

---

### Question 2: Find the Maximum Element in Each Row of a 2D Array
Write the MIPS assembly code to find the maximum value in each row of a \( n \times m \) array. Store the maximum values in a separate array. The C code is provided below:

```c
void max_in_rows(int array[4][4], int max_values[4]) {
    for (int i = 0; i < 4; i++) {
        int max = array[i][0];
        for (int j = 1; j < 4; j++) {
            if (array[i][j] > max) {
                max = array[i][j];
            }
        }
        max_values[i] = max;
    }
}
```

---

### Question 3: Count Positive Elements in a 2D Array
Write the MIPS assembly code to count the number of positive integers in a \( n \times m \) array. The C code is as follows:

```c
int count_positive(int array[2][5]) {
    int count = 0;
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 5; j++) {
            if (array[i][j] > 0) {
                count++;
            }
        }
    }
    return count;
}
```

---

### Question 4: Transpose a 2D Array
Write the MIPS assembly code to compute the transpose of a \( n \times m \) matrix. The C code is as follows:

```c
void transpose(int array[3][3], int result[3][3]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            result[j][i] = array[i][j];
        }
    }
}
```

---

### Question 5: Matrix Multiplication
Write the MIPS assembly code for multiplying two \( n \times n \) matrices. The C code is as follows:

```c
void multiply_matrices(int A[2][2], int B[2][2], int C[2][2]) {
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < 2; k++) {
                C[i][j] += A[i][k] * B[k][j];
            }
        }
    }
}
```


### Complex Translation Questions: C Code to MIPS Assembly

---

### Question 1: Sum of Elements Greater Than Threshold in a 2D Array

Write MIPS assembly code to compute the sum of all elements in a \( n \times m \) 2D array that are greater than a given threshold.

```c
int sum_greater_than_threshold(int array[4][5], int threshold) {
    int sum = 0;
    for (int i = 0; i < 4; i++) {
        for (int j = 0; j < 5; j++) {
            if (array[i][j] > threshold) {
                sum += array[i][j];
            } else {
                sum += 0;
            }
        }
    }
    return sum;
}
```

---

### Question 2: Categorize Elements in a 2D Array

Write MIPS assembly code to count how many elements in a 2D array are positive, negative, or zero. Store these counts in separate variables.

```c
void categorize_elements(int array[3][3], int *positive_count, int *negative_count, int *zero_count) {
    *positive_count = 0;
    *negative_count = 0;
    *zero_count = 0;

    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 3; j++) {
            if (array[i][j] > 0) {
                (*positive_count)++;
            } else if (array[i][j] < 0) {
                (*negative_count)++;
            } else {
                (*zero_count)++;
            }
        }
    }
}
```

---

### Question 3: Identify Diagonal Sum with Conditions

Write MIPS assembly code to calculate the sum of the diagonal elements of a square matrix, but only include those greater than a specific threshold.

```c
int diagonal_sum(int array[4][4], int threshold) {
    int sum = 0;
    for (int i = 0; i < 4; i++) {
        if (array[i][i] > threshold) {
            sum += array[i][i];
        } else if (array[i][i] == threshold) {
            sum += 1;
        }
    }
    return sum;
}
```

---

### Question 4: Copy and Replace Elements Based on Conditions

Write MIPS assembly code to copy one 2D array into another, replacing negative numbers with their absolute values.

```c
void copy_and_replace(int source[3][4], int destination[3][4]) {
    for (int i = 0; i < 3; i++) {
        for (int j = 0; j < 4; j++) {
            if (source[i][j] < 0) {
                destination[i][j] = -source[i][j];
            } else {
                destination[i][j] = source[i][j];
            }
        }
    }
}
```

---

### Question 5: Matrix Multiplication with Conditionals

Write MIPS assembly code for matrix multiplication, but only multiply elements if both are positive; otherwise, set the result to 0 for that entry.

```c
void conditional_matrix_multiply(int A[2][2], int B[2][2], int C[2][2]) {
    for (int i = 0; i < 2; i++) {
        for (int j = 0; j < 2; j++) {
            C[i][j] = 0;
            for (int k = 0; k < 2; k++) {
                if (A[i][k] > 0 && B[k][j] > 0) {
                    C[i][j] += A[i][k] * B[k][j];
                } else {
                    C[i][j] += 0;
                }
            }
        }
    }
}
```


Here’s a variation of the exam question with expected input and outputs:

---

### Variation: Modify the function `print_bytes` in `final_q5.c`

You are provided with a partially implemented C program `final_q5.c` that contains an empty implementation of the function `print_bytes`. Modify the function so that it behaves as described below:

```c
#include <stdio.h>

void print_bytes(FILE *file, long n) {
    // TODO
}
```

#### Function Behavior:
1. **When `n >= 0`**:  
   The function should print the first `n` bytes of the file referenced by `file`.  
   If `n` is greater than the file size, it should print the entire file without any additional behavior.

2. **When `n < 0`**:  
   The function should print all but the last `|n|` (absolute value of `n`) bytes of the file.  
   If `|n|` exceeds the file size, it should print nothing.

3. **Additional Requirements**:  
   - The file may contain binary data, including `NUL` bytes (`\0`).  
   - Do not assume the file is a text file. Avoid using string-based functions such as `fgets`.  
   - The function should not add a newline at the end of the output.

#### Expected Behavior:
You are provided with a compiled program `22t2final_q5`, which reads a filename and a number `n` from the command-line arguments and invokes `print_bytes`.  
Here are examples of inputs and outputs:

```bash
# Create a sample file
echo -n 'Hello, World!' > test_file

# Example 1: Print the first 5 bytes
./22t2final_q5 test_file 5
Hello

# Example 2: Print the first 50 bytes (more than file size)
./22t2final_q5 test_file 50
Hello, World!

# Example 3: Print all but the last 5 bytes
./22t2final_q5 test_file -5
Hello, Wo

# Example 4: Print nothing when |n| exceeds file size
./22t2final_q5 test_file -50

# Example 5: Print all bytes when n = 0
./22t2final_q5 test_file 0
Hello, World!

# Example 6: Handle a binary file
echo -n -e '\x01\x02\x03\x04\x05\x06' > binary_file
./22t2final_q5 binary_file 4
<prints binary bytes 01 02 03 04>
```

#### Key Assumptions:
- The file is opened successfully before being passed to `print_bytes`.  
- It is guaranteed that the file handle `file` points to a valid file.  

---


### Variation 2: Alternating Increasing and Decreasing Sequence

**C Code:**
```c
#include <stdio.h>

int main(void) {
    int numbers[10] = {0};
    for (int i = 0; i < 10; i++) {
        scanf("%d", &numbers[i]);
    }

    int max_run = 1;
    int current_run = 1;

    for (int i = 1; i < 10; i++) {
        if ((i % 2 == 1 && numbers[i] > numbers[i - 1]) || 
            (i % 2 == 0 && numbers[i] < numbers[i - 1])) {
            current_run++;
        } else {
            current_run = 1;
        }
        if (current_run > max_run) {
            max_run = current_run;
        }
    }

    printf("%d\n", max_run);
    return 0;
}
```

**MIPS Code:**
```asm
.data
numbers: .space 40   # Reserve space for 10 integers
max_run: .word 1
current_run: .word 1
prompt: .asciiz "Enter 10 numbers: \n"

.text
main:
    li $v0, 4
    la $a0, prompt
    syscall
    
    # Read 10 integers
    la $t0, numbers
    li $t1, 10
read_loop:
    li $v0, 5
    syscall
    sw $v0, 0($t0)
    addiu $t0, $t0, 4
    subu $t1, $t1, 1
    bnez $t1, read_loop

    # Initialize variables
    la $t0, numbers
    lw $t2, max_run
    lw $t3, current_run
    li $t1, 1

check_loop:
    # Exit loop if i >= 10
    li $t4, 10
    bge $t1, $t4, done

    # Determine whether to check increase or decrease
    andi $t5, $t1, 1  # t5 = i % 2
    lw $t6, 0($t0)    # numbers[i]
    lw $t7, -4($t0)   # numbers[i-1]

    bnez $t5, check_increase  # Odd index -> check increase
    j check_decrease

check_increase:
    slt $t8, $t7, $t6
    beqz $t8, reset_run
    j increment_run

check_decrease:
    slt $t8, $t6, $t7
    beqz $t8, reset_run

increment_run:
    addiu $t3, $t3, 1
    j compare_runs

reset_run:
    li $t3, 1

compare_runs:
    # Update max_run if current_run > max_run
    slt $t9, $t2, $t3
    beqz $t9, skip_update
    move $t2, $t3

skip_update:
    # Increment array pointer and index
    addiu $t0, $t0, 4
    addiu $t1, $t1, 1
    j check_loop

done:
    # Print max_run
    move $a0, $t2
    li $v0, 1
    syscall

    # Exit program
    li $v0, 10
    syscall
```

---

### Variation 3: Longest Non-Decreasing Sequence

**C Code:**
```c
#include <stdio.h>

int main(void) {
    int numbers[10] = {0};
    for (int i = 0; i < 10; i++) {
        scanf("%d", &numbers[i]);
    }

    int max_run = 1;
    int current_run = 1;

    for (int i = 1; i < 10; i++) {
        if (numbers[i] >= numbers[i - 1]) {
            current_run++;
        } else {
            current_run = 1;
        }
        if (current_run > max_run) {
            max_run = current_run;
        }
    }

    printf("%d\n", max_run);
    return 0;
}
```

**MIPS Code:**
```asm
.data
numbers: .space 40   # Reserve space for 10 integers
max_run: .word 1
current_run: .word 1
prompt: .asciiz "Enter 10 numbers: \n"

.text
main:
    li $v0, 4
    la $a0, prompt
    syscall
    
    # Read 10 integers
    la $t0, numbers
    li $t1, 10
read_loop:
    li $v0, 5
    syscall
    sw $v0, 0($t0)
    addiu $t0, $t0, 4
    subu $t1, $t1, 1
    bnez $t1, read_loop

    # Initialize variables
    la $t0, numbers
    lw $t2, max_run
    lw $t3, current_run
    li $t1, 1

check_loop:
    # Exit loop if i >= 10
    li $t4, 10
    bge $t1, $t4, done

    # Compare numbers[i] >= numbers[i-1]
    lw $t5, 0($t0)
    lw $t6, -4($t0)
    slt $t7, $t6, $t5
    bnez $t7, increment_run

    # Reset current_run
    li $t3, 1
    j compare_runs

increment_run:
    addiu $t3, $t3, 1

compare_runs:
    # Update max_run if current_run > max_run
    slt $t7, $t2, $t3
    beqz $t7, skip_update
    move $t2, $t3

skip_update:
    # Increment array pointer and index
    addiu $t0, $t0, 4
    addiu $t1, $t1, 1
    j check_loop

done:
    # Print max_run
    move $a0, $t2
    li $v0, 1
    syscall

    # Exit program
    li $v0, 10
    syscall
```


Here is a variation of the question, modifying the problem to handle UTF-16 encoding instead of UTF-8:

---

### Variation: Handling UTF-16 Strings

You are provided with a partially implemented C program `22t2final_q6.c` that contains a function `_22t2final_q6`. Modify the function so that it works with **UTF-16** encoded strings instead of UTF-8.

The function takes the following parameters:

1. **`uint16_t *utf16_string`**: A pointer to a UTF-16 encoded string (terminated by a null character `\0`).  
2. **`unsigned int range_start`**: The inclusive starting index (in terms of **UTF-16 code units**).  
3. **`unsigned int range_end`**: The exclusive ending index (in terms of **UTF-16 code units**).  

The function must return a new UTF-16 string that includes all code points in the range `[range_start, range_end)`.

---

### Function Signature

```c
#include <stdint.h>
#include <stdlib.h>

/**
 * given a UTF-16 encoded string,
 * return a new string that includes only
 * the code units within the provided range.
 *
 * Note:
 * `range_start` is INCLUSIVE
 * `range_end`   is EXCLUSIVE
 *
 * eg:
 * L"hello world", 0, 5
 * would return L"hello"
 *
 * L"🍓🍇🍈🍍🍐", 2, 5
 * would return L"🍈🍍🍐"
 */
uint16_t *_22t2final_q6(uint16_t *utf16_string, unsigned int range_start, unsigned int range_end) {
    uint16_t *new_string = malloc(2 * (range_end - range_start + 1)); // Placeholder
    return new_string;
}
```

---

### Requirements

1. **Memory Allocation**:
   - The function must allocate new memory using `malloc` or similar.
   - The returned string must be a new string and not modify the provided `utf16_string`.
   - Ensure the returned string is null-terminated.

2. **Handle Surrogate Pairs**:
   - The input UTF-16 string may contain surrogate pairs. Treat a high surrogate (`D800` to `DBFF`) followed by a low surrogate (`DC00` to `DFFF`) as one code point. Ensure that surrogate pairs are not split.

3. **Index Validity**:
   - If `range_start` or `range_end` exceeds the length of the string, handle it gracefully:
     - If `range_start` ≥ string length, return an empty string.
     - If `range_end` > string length, include up to the end of the string.
   - `range_start` should always be ≤ `range_end`. If not, return an empty string.

---

### Examples

#### Example 1: Simple Text
Input:
```bash
./22t2final_q6 "hello world" 3 8
```
Output:
```bash
22t2final_q6("hello world", 3, 8) returned "lo wo"
```

#### Example 2: UTF-16 with Surrogate Pairs
Input:
```bash
./22t2final_q6 "🍓🍇🍈🍍🍐🍖" 2 5
```
Output:
```bash
22t2final_q6("🍓🍇🍈🍍🍐🍖", 2, 5) returned "🍈🍍🍐"
```

#### Example 3: Exceeding Range
Input:
```bash
./22t2final_q6 "⇜⇿↴↛⇳⇙↜↧⇥↖⇸⇋⇈" 10 15
```
Output:
```bash
22t2final_q6("⇜⇿↴↛⇳⇙↜↧⇥↖⇸⇋⇈", 10, 15) returned "⇋⇈"
```

#### Example 4: Empty Range
Input:
```bash
./22t2final_q6 "hello world" 7 7
```
Output:
```bash
22t2final_q6("hello world", 7, 7) returned ""
```

---

### Key Differences Between UTF-8 and UTF-16

| Feature            | UTF-8                                    | UTF-16                         |
|--------------------|------------------------------------------|--------------------------------|
| Code unit size     | 8 bits                                   | 16 bits                       |
| Encoding range     | 1–4 bytes per character                  | 1–2 code units per character  |
| Handling surrogate pairs | Not applicable                        | High and low surrogates form one character |
| Endianness         | Always big-endian                        | Can be little- or big-endian  |

This variation tests the student’s understanding of how UTF-16 differs from UTF-8 in memory layout and encoding complexities, especially handling surrogate pairs.


---

### Variation 1: Match files with specific extensions and depth criteria
**Question Prompt:**

You have been given 22t2final_q7.c: a C program with an empty implementation of the function 22t2final_q7.

```c
void _22t2final_q7(char *directory, char *extension, int min_depth, int max_depth);
```

Add code to the function 22t2final_q7 such that it recursively looks through the provided directory for files and directories that match the given criteria. If a file or directory is found that matches the given criteria, the path to that file should be printed out. In this variation, you are specifically asked to match files based on their extension. 

The parameters are:
- `extension`: the extension to match files against. If it's NULL, this criterion does not apply.

---

### Variation 2: Exclude directories containing a specific keyword and match files at exact depths
**Question Prompt:**

You have been given 22t2final_q7.c: a C program with an empty implementation of the function 22t2final_q7.

```c
void _22t2final_q7(char *directory, char *name, int min_depth, int max_depth, char *exclude_keyword);
```

Add code to the function 22t2final_q7 such that it recursively looks through the provided directory for files and directories that match the given criteria. If a file or directory is found that matches the given criteria, the path to that file should be printed out. In this variation, you are asked to exclude directories containing a certain keyword in their name.

The parameters are:
- `name`: the name to match files and directories against.
- `exclude_keyword`: If a directory's name contains this keyword, it should not be processed further.

---

### Variation 3: Match hidden files only, ignoring directory names
**Question Prompt:**

You have been given 22t2final_q7.c: a C program with an empty implementation of the function 22t2final_q7.

```c
void _22t2final_q7(char *directory, char *name, int min_depth, int max_depth, bool match_hidden);
```

Add code to the function 22t2final_q7 such that it recursively looks through the provided directory for files and directories that match the given criteria. If a file or directory is found that matches the given criteria, the path to that file should be printed out. In this variation, you are asked to match only hidden files (files starting with a dot `.`) while ignoring directory names.

The parameters are:
- `name`: the name to match files and directories against.
- `match_hidden`: If true, the search should consider hidden files. If false, hidden files should be ignored.

---
