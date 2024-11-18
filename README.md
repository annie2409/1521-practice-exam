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


Sure! Here's the revised prompt for your variation without the solution:

---

### Variation: Extract Middle 16 Bits

You have been given a stub of a C program, `22t3final_q1.c`, with the following function:

```c
uint32_t _22t3final_q1(uint32_t x) {
    // ADD YOUR CODE HERE
    return 42;
}
```

Your task is to modify the function to extract and return the **middle 16 bits** (bits 8 to 23) from the provided 32-bit unsigned integer `x`. Specifically:

- **Mask and Shift**: The function should return the value formed by the 16 bits from positions 8 to 23 (inclusive). The returned value should be between 0 and 65535, inclusive.
- **Important**: The result must be a 16-bit unsigned integer. For example, if the middle 16 bits are `0x1234`, the function should return `0x1234`.

---

### Example Inputs and Outputs

1. **Example 1**  
   **Input**: `x = 0x00000000`  
   **Output**: `0`

2. **Example 2**  
   **Input**: `x = 0x0000003A`  
   **Output**: `0`

3. **Example 3**  
   **Input**: `x = 0x00042000`  
   **Output**: `66`

4. **Example 4**  
   **Input**: `x = 0x12345678`  
   **Output**: `69`

5. **Example 5**  
   **Input**: `x = 0xFFFFFFFF`  
   **Output**: `255`

---

### Notes

- The function should only extract the bits from positions 8 to 23 (inclusive). These bits will form an unsigned integer between 0 and 65535.
- Ensure that the function works for both small and large numbers, as well as edge cases such as `0` and `4294967295`.

- Here's the modified version of the question with the updated prompt. This variation involves reading two numbers and computing the sum of their cubes instead of their squares. You would modify the MIPS assembler program to reflect this behavior.

---

### Variation: Sum of Cubes

You have been given the MIPS assembler program `22t3final_q2.s`, which reads two integers and prints the sum of their **cubes** (i.e., \(a^3 + b^3\)).

Your task is to modify the MIPS assembler program so that it behaves like the following C program:

```c
#include <stdio.h>

int main(void) {
    int a, b;

    scanf("%d", &a);
    scanf("%d", &b);

    printf("%d\n", a * a * a + b * b * b);

    return 0;
}
```

In other words:
- The program should read two integers, `a` and `b`, and print the sum of their cubes, i.e., \(a^3 + b^3\).

---

### Example Inputs and Outputs

1. **Input**  
   ```
   3
   4
   ```
   **Output**  
   ```
   91
   ```
   Explanation: \(3^3 + 4^3 = 27 + 64 = 91\).

2. **Input**  
   ```
   6
   5
   ```
   **Output**  
   ```
   261
   ```
   Explanation: \(6^3 + 5^3 = 216 + 125 = 261\).

3. **Input**  
   ```
   5
   6
   ```
   **Output**  
   ```
   261
   ```
   Explanation: \(5^3 + 6^3 = 125 + 216 = 261\).

4. **Input**  
   ```
   42
   42
   ```
   **Output**  
   ```
   7408
   ```
   Explanation: \(42^3 + 42^3 = 74088 + 74088 = 7408\).

---

### Variation 1: Check if Environment Variables' Sum is Even

Write a C program, `20t3final_q3.c`, which takes two names of environment variables as arguments. `20t3final_q3.c` should print `1` if the sum of both environment variables' values is even, and print `0` otherwise.

- If either of the environment variables is unset, assume its value is `42`.
- If either environment variable is non-numeric, assume its value is `42`.
- For this problem, the sum of the environment variables' values should be checked for evenness.

For example:

```
export VAR1=40
export VAR2=42
unset VAR3
dcc 20t3final_q3.c -o 20t3final_q3
./20t3final_q3 VAR1 VAR2
1
./20t3final_q3 VAR1 VAR3
1
./20t3final_q3 VAR2 VAR3
0
```

---

### Variation 2: Compare Environment Variables Using Absolute Difference

Write a C program, `20t3final_q3.c`, which takes two names of environment variables as arguments. `20t3final_q3.c` should print `1` if the absolute difference between the two environment variables is strictly less than 5, and print `0` otherwise.

- If either environment variable is unset, assume its value is `42`.
- If either environment variable is non-numeric, assume its value is `42`.

For example:

```
export VAR1=40
export VAR2=42
export VAR3=50
unset VAR4
dcc 20t3final_q3.c -o 20t3final_q3
./20t3final_q3 VAR1 VAR2
1
./20t3final_q3 VAR1 VAR3
0
./20t3final_q3 VAR2 VAR3
0
./20t3final_q3 VAR1 VAR4
1
```




Here are two variations of the task, each with a different way of processing the file copying based on different conditions:

---

### Variation 1: Copy a File Without the First n Bytes

Write a C program, `20t3final_q5.c`, which takes 3 arguments:

1. An integer `n`, the number of bytes to skip at the **beginning** of the file.
2. The name of the existing file.
3. The name of the file to be created.

`20t3final_q5.c` should copy the content of the existing file to the new file, but it should skip the first `n` bytes. If the file is smaller than `n` bytes, the new file should be empty.

For example:

```
dcc 20t3final_q5.c -o 20t3final_q5
echo hello >hello.txt
./20t3final_q5 2 hello.txt new.txt
ls -l hello.txt new.txt
-rw-r--r-- 1 z5555555 z5555555 6 Nov 26 16:28 hello.txt
-rw-r--r-- 1 z5555555 z5555555 4 Nov 26 16:29 new.txt
xxd hello.txt
00000000: 6865 6c6c 6f0a                           hello.
xxd new.txt
00000000: 6c6c 6f0a                               ll
```

In this example, the program skips the first 2 bytes (`'h'` and `'e'`), so only `llo\n` is copied into `new.txt`.

---

### Variation 2: Copy a File Without a Specified Range of Bytes

Write a C program, `20t3final_q5.c`, which takes 4 arguments:

1. An integer `n_start`, the starting byte index to skip.
2. An integer `n_end`, the byte index where copying should stop.
3. The name of the existing file.
4. The name of the file to be created.

`20t3final_q5.c` should copy the content of the existing file to the new file, skipping the bytes from `n_start` to `n_end`. If the file is smaller than `n_end`, it should still copy up to the end of the file, but skipping from `n_start` to the file's end.

For example:

```
dcc 20t3final_q5.c -o 20t3final_q5
echo hello world >hello.txt
./20t3final_q5 2 8 hello.txt new.txt
ls -l hello.txt new.txt
-rw-r--r-- 1 z5555555 z5555555 11 Nov 26 16:28 hello.txt
-rw-r--r-- 1 z5555555 z5555555 6 Nov 26 16:29 new.txt
xxd hello.txt
00000000: 6865 6c6c 6f20 776f 726c 64          hello world
xxd new.txt
00000000: 6865 6c6c 64                         hellod
```

In this example, the program skips bytes between positions `2` and `8` (`'l', 'o', ' ', 'w', 'o'`), so the resulting file `new.txt` contains the content from `'h'` and `'d'` (i.e., `"hellod"`).

---
Here are two variations of the problem where the challenge is to count the number of set bits in a file. Each variation introduces a slightly different condition.

---

### Variation 1: Count Set Bits in Even-Numbered Bytes Only

Write a C program, `20t3final_q6.c`, which takes a single filename as its argument.

`20t3final_q6.c` should read the bytes of the file and **count the number of bits that are set to 1** only in the even-numbered bytes (i.e., bytes at positions 0, 2, 4, 6, ...). 

`20t3final_q6.c` should then print one line of output containing the total number of bits that are set in the even-numbered bytes.

For example:

```
dcc 20t3final_q6.c -o 20t3final_q6
echo > file0
xxd file0
00000000: 0a                                       .
./20t3final_q6 file0
file0 has 1 bit set
echo hello world > file1
xxd file1
00000000: 6865 6c6c 6f20 776f 726c 640a            hello world.
./20t3final_q6 file1
file1 has 16 bits set
./20t3final_q6 20t3final_q6.0.bin
20t3final_q6.0.bin has 512 bits set
```

In this variation, the program will only count the bits that are set in the even-numbered bytes of the file. For example, byte 0, byte 2, etc., will be processed, but odd-numbered bytes (1, 3, etc.) will be ignored.

---

### Variation 2: Count Set Bits in Non-ASCII Characters Only

Write a C program, `20t3final_q6.c`, which takes a single filename as its argument.

`20t3final_q6.c` should read the bytes of the file, and **count the number of bits that are set to 1** only in the bytes that represent **non-ASCII characters** (i.e., bytes with values greater than 127).

`20t3final_q6.c` should print one line of output containing the total number of bits that are set in these non-ASCII bytes.

For example:

```
dcc 20t3final_q6.c -o 20t3final_q6
echo > file0
xxd file0
00000000: 0a                                       .
./20t3final_q6 file0
file0 has 0 bits set
echo hello world > file1
xxd file1
00000000: 6865 6c6c 6f20 776f 726c 640a            hello world.
./20t3final_q6 file1
file1 has 0 bits set
echo "This is a test: 🍓" > file2
xxd file2
00000000: 5468 6973 2069 7320 6174 6573 743a 20    This is a test:  
00000010: f09f 8c93                                 .
./20t3final_q6 file2
file2 has 16 bits set
```

In this variation, the program will only count bits in bytes representing non-ASCII characters (those with values greater than 127). For instance, in the file `file2`, the byte `0xf0` and its subsequent bytes (which are part of the Unicode character 🍓) will be processed, while ASCII characters are ignored.

--- 

### Variation 1:

**Prompt:**
You have been given 20t3final_q7.s, a MIPS assembler program that implements all but one function of this C program. 

```c
#include <stdio.h>

void read_array(int rows, int cols, int a[rows][cols]);
void reflect(int rows, int cols, int a[rows][cols], int b[cols][rows]);
void print_array(int rows, int cols, int a[rows][cols]);

int main(void) {
    int rows;
    int cols;
    scanf("%d", &rows);
    scanf("%d", &cols);
    int array1[rows][cols];
    int array2[cols][rows];
    read_array(rows, cols, array1);
    reflect(rows, cols, array1, array2);
    print_array(rows, cols, array1);
    printf("\n");
    print_array(cols, rows, array2);
}
```

The function which has not been implemented is named `reflect`.

### MIPS Code:
Add the MIPS instructions for the `reflect` function to 20t3final_q7.s.

For example:
```
1521 mipsy 20t3final_q7.s
2
3
3 4
5 6
3 5
```

---

### Variation 2:

**Prompt:**
You have been given 20t3final_q7.s, a MIPS assembler program that implements all but one function of this C program. 

```c
#include <stdio.h>

void read_array(int rows, int cols, int a[rows][cols]);
void reflect(int rows, int cols, int a[rows][cols], int b[cols][rows]);
void print_array(int rows, int cols, int a[rows][cols]);

int main(void) {
    int rows;
    int cols;
    scanf("%d", &rows);
    scanf("%d", &cols);
    int array1[rows][cols];
    int array2[cols][rows];
    read_array(rows, cols, array1);
    reflect(rows, cols, array1, array2);
    print_array(rows, cols, array1);
    printf("\n");
    print_array(cols, rows, array2);
}
```

The function that hasn't been implemented is called `reflect`.

### MIPS Code:
Add the MIPS instructions for `reflect` to 20t3final_q7.s.

For example:
```
1521 mipsy 20t3final_q7.s
1
3
2 3
4 5
2 4
```

---

### Variation 3:

**Prompt:**
You have been given 20t3final_q7.s, a MIPS assembler program that implements all but one function of this C program. 

```c
#include <stdio.h>

void read_array(int rows, int cols, int a[rows][cols]);
void reflect(int rows, int cols, int a[rows][cols], int b[cols][rows]);
void print_array(int rows, int cols, int a[rows][cols]);

int main(void) {
    int rows;
    int cols;
    scanf("%d", &rows);
    scanf("%d", &cols);
    int array1[rows][cols];
    int array2[cols][rows];
    read_array(rows, cols, array1);
    reflect(rows, cols, array1, array2);
    print_array(rows, cols, array1);
    printf("\n");
    print_array(cols, rows, array2);
}
```

The missing function is `reflect`.

### MIPS Code:
Add MIPS instructions for the `reflect` function to 20t3final_q7.s.

For example:
```
1521 mipsy 20t3final_q7.s
2
2
3 4
5 6
3 6
```

**Prompt:**

You have been given 22t3final_q3.s, a MIPS assembler program that reads one number and then prints it.

Add code to 22t3final_q3.s to make it equivalent to this C program:

```c
#include <stdio.h>

int main(void) {
    int sum = 0;
    while (sum < 42) {
        int x;
        scanf("%d", &x);
        sum += x;
    }
    printf("%d\n", sum);
    return 0;
}
```

In other words, it should read numbers until their sum is ≥ 42 and then print their sum.

For example:

```
1521 mipsy 22t3final_q3.s
10
20
25
55

1521 mipsy 22t3final_q3.s
20
22
42

1521 mipsy 22t3final_q3.s
100
100

1521 mipsy 22t3final_q3.s
10
10
10
10
10
50
```

---

### Variation 1: Count Consecutive 1's in Even-Indexed Positions Only

Write a C program that takes a 32-bit unsigned integer as an input and finds the length of the longest consecutive sequence of bits set to 1 in **even-indexed positions** only. In other words, consider only the bits at positions 0, 2, 4, 6, ..., and ignore all other bits.

For example:

```
make 22t3final_q4
305419896 == 0x12345678
./22t3final_q4 305419896
1
0 == 0x00000000
./22t3final_q4 0
0
4 == 0x00000004
./22t3final_q4 4
1
4294967295 == 0xFFFFFFFF
./22t3final_q4 4294967295
2
268566401 == 0x1001FF81
./22t3final_q4 268566401
1
```

In this variation, the program only considers bits at even positions (0, 2, 4, etc.) when counting the longest sequence of 1's. For instance, in `305419896` (`0x12345678`), the longest sequence of 1's in the even-indexed positions is just 1 (in position 0), so the output is 1.

---

### Variation 2: Count the Longest Sequence of 1's in Odd-Numbered Bits

Write a C program that takes a 32-bit unsigned integer as input and finds the length of the longest consecutive sequence of bits set to 1 in **odd-numbered bit positions** only (i.e., positions 1, 3, 5, 7, etc.). 

For example:

```
make 22t3final_q4
305419896 == 0x12345678
./22t3final_q4 305419896
2
0 == 0x00000000
./22t3final_q4 0
0
4 == 0x00000004
./22t3final_q4 4
0
4294967295 == 0xFFFFFFFF
./22t3final_q4 4294967295
16
268566401 == 0x1001FF81
./22t3final_q4 268566401
3
```

In this variation, only the bits at odd positions are considered for the longest sequence of consecutive 1's. For example, in `305419896` (`0x12345678`), the bits at odd positions are `0x2`, which has a longest sequence of 1's of length 2.

---


Here is a variation of the MIPS assembler task, based on the same core functionality but with a slight twist to make it different and challenge the user in a different way. The main task remains the same: finding the length of the longest consecutive sequence of 1's in the binary representation of a 32-bit signed integer. 

### Variation 1: Count Longest Sequence of 1's in Even-Indexed Positions Only

Modify the MIPS program to count the longest sequence of consecutive 1's in the even-indexed bit positions only (i.e., positions 0, 2, 4, 6, ... 30). This means that only bits at even positions will be considered for the longest sequence of 1's, and the result should be the length of the longest sequence of 1's within these even positions.

For example:

```
1521 mipsy 22t3final_q5.s
305419896
1

1521 mipsy 22t3final_q5.s
0
0

1521 mipsy 22t3final_q5.s
4
```

---

### Variation 2: Count Longest Sequence of 1's in Odd-Indexed Positions Only

Modify the MIPS program to count the longest sequence of consecutive 1's in the odd-indexed bit positions only (i.e., positions 1, 3, 5, 7, ..., 31). This variation will challenge the user to only consider bits at odd positions while determining the longest sequence of 1's.

For example:

```
1521 mipsy 22t3final_q5.s
305419896
2

1521 mipsy 22t3final_q5.s
0
0

1521 mipsy 22t3final_q5.s
4
```

---

Here’s a variation of the question that still requires deleting a specific line from a file, but with added complexity to test different situations or file handling nuances.

### Variation 1: Delete Multiple Lines from a File

Modify the program to delete multiple lines from a file. The program should now accept a second argument that specifies the range of lines to delete (from `n1` to `n2`, inclusive). If `n2` is greater than the number of lines in the file, only lines up to the end of the file should be deleted.

For example:

```sh
printf 'Line 1\nLine 2\nLine 3\nLine 4\nLine 5\n' > myfile.txt
cat myfile.txt
Line 1
Line 2
Line 3
Line 4
Line 5

./22t3final_q6 myfile.txt 2 4
cat myfile.txt
Line 1
Line 5
```

**Details:**
- The program should remove lines between the line numbers `n1` and `n2` inclusively.
- If `n2` is greater than the number of lines, it should delete lines starting from `n1` to the end of the file.
- No output should be printed.

---

### Variation 2: Delete Every N-th Line from a File

Modify the program to delete every `n`-th line from a file. The program should accept a second argument `n` and delete every `n`-th line (where `n` starts from 1). 

For example:

```sh
printf 'Line 1\nLine 2\nLine 3\nLine 4\nLine 5\n' > myfile.txt
cat myfile.txt
Line 1
Line 2
Line 3
Line 4
Line 5

./22t3final_q6 myfile.txt 2
cat myfile.txt
Line 1
Line 3
Line 5
```

**Details:**
- For every `n`-th line, the program will remove that line from the file.
- If `n` is 2, for instance, it will remove lines 2, 4, 6, and so on.
- No output should be printed.

---

