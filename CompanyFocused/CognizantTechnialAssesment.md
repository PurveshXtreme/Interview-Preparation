# 📚 Programming Questions & Solutions

---

<a id="table-of-contents"></a>
## 📖 Table of Contents

### 🖥️ C# Coding Questions
| # | Question |
|---|----------|
| 1 | [Programming Question — Subarray Count (Size 3 Condition Check)](#q-csharp-1) |
| 2 | [Programming Question — Lift Maximum People Problem](#q-csharp-2) |
| 3 | [Programming Question — ASCII Character Converter](#q-csharp-3) |
| 4 | [Programming Question — Lucky Number Calculator](#q-csharp-4) |
| 5 | [Programming Question — Display Current Date and Time](#q-csharp-5) |
| 6 | [Programming Question — Character Expansion by First Occurrence Index](#q-csharp-6) |
| 7 | [Programming Question — Longest Even-Length Vowel-Starting Word](#q-csharp-7) |
| 8 | [Programming Question — Maximum Levels & Concatenated Score](#q-csharp-8) |
| 9 | [Programming Question — Impact Sum With Threshold](#q-csharp-9) |
| 10 | [Programming Question — Lucky Number Calculation (ASCII × Index Rule)](#q-csharp-10) |
| 11 | [Programming Question — Reverse Array Based on Half-Sum Comparison](#q-csharp-11) |
| 12 | [Programming Question — Generate Bill for Vohra's Purchase](#q-csharp-12) |
| 13 | [Programming Question — Prime Number Check](#q-csharp-13) |
| 14 | [Programming Question — Print Left-Aligned Star Triangle](#q-csharp-14) |
| 15 | [Programming Question — Maximum Subarray Sum](#q-csharp-15) |
| 16 | [Programming Question — Check Buzz Number](#q-csharp-16) |
| 17 | [Programming Question — Minimum Operations to Form a Permutation](#q-csharp-17) |

### 🗄️ SQL Questions
| # | Question |
|---|----------|
| 1 | [SQL Question — Outstanding Amount](#q-sql-1) |
| 2 | [SQL Question — Second Highest Salary (2023)](#q-sql-2) |
| 3 | [SQL Question — Third Highest Salary](#q-sql-3) |
| 4 | [SQL Question — Names Ending With "ed"](#q-sql-4) |
| 5 | [SQL Question — Count Employees Department-Wise (2022)](#q-sql-5) |
| 6 | [SQL Question — Departments With More Than One Employee](#q-sql-6) |
| 7 | [SQL Question — Artist Followers (2018 or Later)](#q-sql-7) |
| 8 | [SQL Question — Users Following at Least 5 Others](#q-sql-8) |
| 9 | [SQL Question — Employees Joined Recently or Between Jan–Mar](#q-sql-9) |
| 10 | [SQL Question — Employee Leave Summary](#q-sql-10) |
| 11 | [SQL Question — Employee Details With House Rent Allowance](#q-sql-11) |
| 12 | [SQL Question — Album Reviews With Rating 5](#q-sql-12) |
| 13 | [SQL Question — Upcoming Flight Details (After 2024-02-06)](#q-sql-13) |
| 14 | [SQL Question — Patients With Outstanding Amount](#q-sql-14) |
| 15 | [SQL Question — Top 5 Users by Messages Sent](#q-sql-15) |
| 16 | [SQL Question — Staff Salary Filter](#q-sql-16) |
| 17 | [SQL Question — Combine Results of Multiple SELECT Statements](#q-sql-17) |
| 18 | [SQL Question — Retrieve Rows Within a Date Range](#q-sql-18) |
| 19 | [SQL Question — Retrieve Specific Columns From a Table](#q-sql-19) |
| 20 | [SQL Question — Create Employees Table](#q-sql-20) |
| 21 | [SQL Question — Delete All Rows but Keep Table Structure](#q-sql-21) |
| 22 | [SQL Question — Combine Rows Using LEFT JOIN](#q-sql-22) |
| 23 | [SQL Question — Artist Followers (2018 or Later)](#q-sql-23) |
| 24 | [SQL Question — Categories Starting With 'M'](#q-sql-24) |
| 25 | [SQL Question — Mid-Range Transactions (10k to 50k)](#q-sql-25) |
| 26 | [SQL Question — Customer Details by Account Type](#q-sql-26) |
| 27 | [SQL Question — Employees With Salary Between 60,000 and 80,000](#q-sql-27) |
| 28 | [SQL Question — Insert Values Into Employees Table](#q-sql-28) |
| 29 | [SQL Question — Average Salary by Job Title](#q-sql-29) |
| 30 | [SQL Question — Count Employees in Each Department](#q-sql-30) |
| 31 | [SQL Question — Retrieve Rows Matching Specific Values](#q-sql-31) |
| 32 | [SQL Question — Find the Sum of Values in a Column](#q-sql-32) |
| 33 | [SQL Question — Salary Difference Between Highest and Lowest Paid Employees](#q-sql-33) |
| 34 | [SQL Question — Join Employees With Their Departments](#q-sql-34) |
| 35 | [SQL Question — Increase Salary for Employees in Department 5](#q-sql-35) |
| 36 | [SQL Question — Remove Employees With Low Salary](#q-sql-36) |

### 🌐 Web UI Questions (HTML/CSS/JavaScript)
| # | Question |
|---|----------|
| 1 | [Fruit Chart — Web Development Task](#q-webui-1) |
| 2 | [Programming Question — Image Showcase Application](#q-webui-2) |
| 3 | [Programming Question — Interactive Animal Display Application](#q-webui-3) |
| 4 | [Programming Question — Build a Product Information Table](#q-webui-4) |
| 5 | [HTML Question — Create a Simple Input Form](#q-webui-5) |
| 6 | [HTML Question — Build a Basic Navigation Bar](#q-webui-6) |
| 7 | [HTML Question — Create a Basic HTML Page Structure](#q-webui-7) |
| 8 | [JavaScript Question — Change Paragraph Text on Button Click](#q-webui-8) |
| 9 | [HTML Question — Link to an External Website](#q-webui-9) |
| 10 | [CSS Question — Add and Center a Background Image](#q-webui-10) |
| 11 | [HTML Question — Create a Simple Webpage With Heading and Paragraph](#q-webui-11) |
| 12 | [HTML Question — Create an Ordered and Unordered List](#q-webui-12) |

---

# 🖥️ C# Coding Questions

---

<a id="q-csharp-1"></a>
# 🚀 Programming Question — Subarray Count (Size 3 Condition Check)

## 📌 Problem Description
Given an integer array, your task is to count how many **subarrays of size 3** satisfy:

> **first element + third element == second element**

A subarray must be **continuous**.

---

## 📥 Input Specification
- `input1`: Integer array `nums`
- `input2`: Integer `N`, the size of the array

---

## 📤 Output Specification
Return an integer representing the total number of valid subarrays of size 3.

---

## 🧠 Example
Array:
```
1 2 1 3 2
```

Valid subarrays:
- (1, 2, 1) → 1 + 1 = 2 ✔  
- (1, 3, 2) → 1 + 2 = 3 ✔  

Total → **2**

---

# ✅ C# Solution

```csharp
using System;

public class Solution
{
    public int CountSpecialSubarrays(int[] nums, int n)
    {
        if (n < 3)
            return 0;

        int count = 0;
        int i = 0;
        int j = 2;

        while (j < n)
        {
            if (nums[i] + nums[j] == nums[i + 1])
                count++;

            i++;
            j++;
        }

        return count;
    }
}
```

---

# 🧪 Test Code

```csharp
class Program
{
    static void Main(string[] args)
    {
        Solution sol = new Solution();

        int[] nums1 = { 1, 2, 1, 3, 2 };
        Console.WriteLine(sol.CountSpecialSubarrays(nums1, nums1.Length)); // Output: 2

        int[] nums2 = { 2, 4, 2, 6, 3, 9 };
        Console.WriteLine(sol.CountSpecialSubarrays(nums2, nums2.Length)); // Output: 1

        int[] nums3 = { 5, 10, 5 };
        Console.WriteLine(sol.CountSpecialSubarrays(nums3, nums3.Length)); // Output: 1
    }
}
```

---

# 🎯 Complexity
- **Time:** O(n)  
- **Space:** O(1)

---


---



<a id="q-csharp-2"></a>

<a id="q-csharp-3"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-2"></a>
# 🚀 Programming Question — Lift Maximum People Problem

## 📌 Problem Description
A lift in a building can carry people as long as the **total weight does not exceed a maximum limit X**.  
You are given:

- The number of people **N**  
- The lift’s maximum weight capacity **X**  
- An integer array **A** of size **N**, where each element represents the weight of a person  

Your task is to determine the **maximum number of people who can enter the lift together without exceeding the weight limit**.  
You may choose **any subset of people**, and they do **not** need to be consecutive.

---

## 📥 Input Specification
- `input1`: Integer `N` — number of people  
- `input2`: Integer `X` — maximum weight capacity of the lift  
- `input3`: Integer array `A` — weights of the people  

---

## 📤 Output Specification
Return an integer indicating the **maximum number of people** whose total weight does **not exceed** the value of **X**.

---

## 🧠 Example

### Example Input:
```
N = 5  
X = 100  
A = [30, 40, 50, 10, 20]
```

### Valid Selection (after sorting weights):
```
10 + 20 + 30 + 40 = 100  ✔
```

Maximum number of people = **4**

---

# ✅ C# Solution

```csharp
using System;

public class Solution
{
    public int MaxPeopleInLift(int[] A, int N, int X)
    {
        Array.Sort(A); 
        int totalWeight = 0;
        int count = 0;

        foreach (int w in A)
        {
            totalWeight += w;

            if (totalWeight <= X)
                count++;
            else
                return count;
        }

        return count;
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(N log N) — due to sorting  
- **Space Complexity:** O(1) — in-place computation  

---
---



<a id="q-csharp-3"></a>

<a id="q-csharp-4"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-3"></a>
# 🚀 Programming Question — ASCII Character Converter

## 📌 Problem Description
You are given **4 integer inputs**, each representing an ASCII value.  
Your task is to convert every integer into its corresponding **ASCII character** and display the output in the format:

```
<number> - <character>
```

The number of inputs will **always be 4**.

---

## 🧠 Example

### Sample Input:
```
65
66
67
68
```

### Sample Output:
```
65 - A
66 - B
67 - C
68 - D
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void ConvertASCII(int[] nums)
    {
        for (int i = 0; i < nums.Length; i++)
        {
            char ch = (char)nums[i];
            Console.WriteLine(nums[i] + " - " + ch);
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        int[] nums = new int[4];

        for (int i = 0; i < 4; i++)
        {
            nums[i] = Convert.ToInt32(Console.ReadLine());
        }

        Solution sol = new Solution();
        sol.ConvertASCII(nums);
    }
}
```

---

# 🎯 Complexity
- Time Complexity: **O(1)** (only 4 inputs)  
- Space Complexity: **O(1)**

---

---
---


<a id="q-csharp-4"></a>

<a id="q-csharp-5"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-4"></a>
# 🚀 Programming Question — Lucky Number Calculator

## 📌 Problem Description
Jack wants to compute a **lucky number** for a given word using numerology rules.

You are given a word, and you must calculate its lucky number as follows:

1. Each character has an **ASCII value**  
   Example: `'A' = 65`, `'B' = 66`, etc.

2. Each character has a **1-based index**  
   - 1st character → index **1**  
   - 2nd character → index **2**  
   - And so on…

3. For each character:
   - Compute the product:  
     **ASCII value × index**
   - **Add this product to the total ONLY IF:**  
     - The **index is odd**, OR  
     - The **ASCII value is odd**, OR  
     - Both are odd  

Return the final lucky number.

---

## 🧠 Example

### Sample Input:
```
ABC
```

### Calculation:
| Character | ASCII | Index | ASCII × Index | Odd Check | Included? |
|-----------|--------|--------|-----------------|-------------|------------|
| A         | 65     | 1      | 65              | both odd    | YES        |
| B         | 66     | 2      | 132             | even-even   | NO         |
| C         | 67     | 3      | 201             | both odd    | YES        |

### Sample Output:
```
266
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public int LuckyNumber(string word)
    {
        int total = 0;

        for (int i = 0; i < word.Length; i++)
        {
            int index = i + 1;               
            int ascii = (int)word[i];        
            int product = ascii * index;

            // Include when index or ASCII (or both) are odd
            if (index % 2 == 1 || ascii % 2 == 1)
            {
                total += product;
            }
        }

        return total;
    }
}

class Program
{
    static void Main(string[] args)
    {
        string input = Console.ReadLine();
        Solution sol = new Solution();

        int result = sol.LuckyNumber(input);
        Console.WriteLine(result);
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(N), where N = length of the word  
- **Space Complexity:** O(1)  

---


---
---



<a id="q-csharp-5"></a>

<a id="q-csharp-6"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-5"></a>
# 🚀 Programming Question — Display Current Date and Time

## 📌 Problem Description
Write a program to **display the current system date and time**.  
The output should show both the **current date** and **current time** in standard readable format.

You may use the built-in **DateTime** class in C#.

---

## 🧠 Example

### Sample Output:
```
Current Date and Time: 11/27/2025 10:52:30 AM
```

(Note: Actual output will vary based on the system date and time.)

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void DisplayDateTime()
    {
        DateTime now = DateTime.Now;
        Console.WriteLine("Current Date and Time: " + now);
    }
}

class Program
{
    static void Main(string[] args)
    {
        Solution sol = new Solution();
        sol.DisplayDateTime();
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(1)  
- **Space Complexity:** O(1)  

---


---
---



<a id="q-csharp-6"></a>

<a id="q-csharp-7"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-6"></a>
# 🚀 Programming Question — Character Expansion by First Occurrence Index

## 📌 Problem Description
You are given a string **s** consisting of lowercase English letters.  
For each character, you must repeat it based on the **1-based index of its first occurrence** in the string.

The final output must:
- Contain expanded character groups
- Join them using **hyphens (`-`)**
- Preserve the **original character order**

Example rule:
- If a character first appears at index 1 → repeat it once  
- If a character first appears at index 2 → repeat it twice  
- If first at index 3 → repeat it thrice  
…and so on.

Return the final formatted string.

---

## 🧠 Example

### Sample Input:
```
abca
```

### Explanation:
- `'a'` first appears at index **1** → repeat **1** time → `"a"`
- `'b'` first appears at index **2** → repeat **2** times → `"bb"`
- `'c'` first appears at index **3** → repeat **3** times → `"ccc"`
- `'a'` appears again, but its **first occurrence** is still index **1** → `"a"`

### Sample Output:
```
a-bb-ccc-a
```

---

# ✅ C# Solution
```csharp
using System;
using System.Collections.Generic;

public class Solution
{
    public string ExpandString(string s)
    {
        Dictionary<char, int> firstIndex = new Dictionary<char, int>();
        List<string> parts = new List<string>();

        for (int i = 0; i < s.Length; i++)
        {
            char ch = s[i];

            // Store first occurrence index if not stored
            if (!firstIndex.ContainsKey(ch))
                firstIndex[ch] = i + 1;  // 1-based index

            int repeat = firstIndex[ch];
            parts.Add(new string(ch, repeat));
        }

        return string.Join("-", parts);
    }
}

class Program
{
    static void Main(string[] args)
    {
        string s = Console.ReadLine();
        Solution sol = new Solution();
        Console.WriteLine(sol.ExpandString(s));
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(N²) — due to string repetition  
- **Space Complexity:** O(N)  

---



---


<a id="q-csharp-7"></a>

<a id="q-csharp-8"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-7"></a>
# 🚀 Programming Question — Longest Even-Length Vowel-Starting Word

## 📌 Problem Description
You are given a sentence consisting of words separated by spaces.  
Your task is to find the **longest word** that satisfies **both** conditions:

1. The word has an **even length**  
2. The word **starts with a vowel** (`A, E, I, O, U`, case-insensitive)

If multiple words have the **same maximum even length**, return the **first** such word.  
If **no word** satisfies the conditions, return:

```
0-0
```

Input format:
- A single string containing only **alphabetic characters and spaces**.

---

## 🧠 Example

### Sample Input:
```
apple code inside umbrella
```

### Valid Words:
- apple → starts with vowel, length 5 (odd) → ❌  
- code → even length, but starts with consonant → ❌  
- inside → starts with vowel, length 6 (even) → ✔  
- umbrella → starts with vowel, length 8 (even) → ✔  

Longest even-length vowel-starting word → **umbrella**

### Sample Output:
```
umbrella
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public string LongestVowelWord(string sentence)
    {
        string[] words = sentence.Split(' ');
        string vowels = "aeiouAEIOU";

        string best = "0-0";
        int maxLen = 0;

        foreach (string word in words)
        {
            if (word.Length % 2 == 0 && vowels.Contains(word[0]))
            {
                if (word.Length > maxLen)
                {
                    maxLen = word.Length;
                    best = word;
                }
            }
        }

        return best;
    }
}

class Program
{
    static void Main(string[] args)
    {
        string sentence = Console.ReadLine();
        Solution sol = new Solution();
        Console.WriteLine(sol.LongestVowelWord(sentence));
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(N × L) — splitting + checking each word  
- **Space Complexity:** O(1) — constant extra space  

---



---
---


<a id="q-csharp-8"></a>

<a id="q-csharp-9"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-8"></a>
# 🚀 Programming Question — Maximum Levels & Concatenated Score

## 📌 Problem Description
You are playing a game where you want to cross as many levels as possible.  
You start with an initial amount of **energy `n`**.

To move from one level to the next:

- You must spend the **highest power of 2 (x)** that is **less than or equal to** your current energy.
- After spending `x`, subtract it from your energy.
- Append `x` to your **score string**.
- Continue until your energy becomes **0** or you cannot spend any more energy.

Your task is to return the **final concatenated score** as an integer.

---

## 🧠 Example

### Sample Input:
```
18
```

### Calculation:
- Energy = 18 → highest power of 2 ≤ 18 is **16** → score = `"16"`
- Remaining energy = 2
- Energy = 2 → highest power of 2 ≤ 2 is **2** → score = `"162"`

Final score = **162**

### Sample Output:
```
162
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public int GetFinalScore(int n)
    {
        string score = "";

        while (n > 0)
        {
            int x = 1;

            // Find highest power of 2 <= n
            while (x * 2 <= n)
            {
                x *= 2;
            }

            score += x.ToString();
            n -= x;
        }

        return Convert.ToInt32(score);
    }
}

class Program
{
    static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine());
        Solution sol = new Solution();
        Console.WriteLine(sol.GetFinalScore(n));
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(log n)  
- **Space Complexity:** O(log n)

---



---




<a id="q-csharp-9"></a>

<a id="q-csharp-10"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-9"></a>
# 🚀 Programming Question — Impact Sum With Threshold

## 📌 Problem Description
In a factory assembly line, each product has a weight.  
Sensors calculate the **impact sum** of each product, defined as:

> Sum of the weights of **all other products** except the current one.

However, if the impact sum of a product exceeds the **maximum threshold `C`**,  
the sensor should display the value **C** instead.

You are given:

- An integer array where each element represents a product's weight  
- An integer `C` representing the maximum allowable impact value  

Return a **new array** where each element is the impact sum for that product (capped at C).

---

## 🧠 Example

### Sample Input:
```
weights = [2, 3, 5]
C = 7
```

### Calculation:
- For index 0 → sum of others = 3 + 5 = 8 → exceeds C → **7**
- For index 1 → sum = 2 + 5 = 7 → equals C → **7**
- For index 2 → sum = 2 + 3 = 5 → ≤ C → **5**

### Sample Output:
```
[7, 7, 5]
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public int[] ImpactSum(int[] arr, int C)
    {
        int n = arr.Length;
        int totalSum = 0;

        foreach (int x in arr)
            totalSum += x;

        int[] result = new int[n];

        for (int i = 0; i < n; i++)
        {
            int impact = totalSum - arr[i];
            result[i] = (impact > C) ? C : impact;
        }

        return result;
    }
}

class Program
{
    static void Main(string[] args)
    {
        int[] arr = { 2, 3, 5 };
        int C = 7;

        Solution sol = new Solution();
        int[] result = sol.ImpactSum(arr, C);

        foreach (int x in result)
            Console.Write(x + " ");
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(n)

---


---



<a id="q-csharp-10"></a>

<a id="q-csharp-11"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-10"></a>
# 🚀 Programming Question — Lucky Number Calculation (ASCII × Index Rule)

## 📌 Problem Description
Jack is interested in numerology and wants to calculate a **lucky number** for a given word using the rules below:

1. Each alphabet has an **ASCII value**  
   (Example: `'A' = 65`, `'B' = 66`, `'Z' = 90`, `'a' = 97`, etc.)

2. Each character in the word has a **1-based index**  
   - First character → index **1**  
   - Second character → index **2**  
   - And so on…

3. The **lucky number** is calculated as:
   - Multiply each character’s ASCII value by its 1-based index  
   - **Add this product to the total only if:**  
     - The **index is odd**, OR  
     - The **ASCII value is odd**, OR  
     - **Both** are odd  

Return the final lucky number.

---

## 🧠 Example

### Input:
```
Length = 5  
Word = JAMES
```

### Calculation:
```
J → ASCII 74, index 1 → 74*1 → included
A → ASCII 65, index 2 → 65*2 → included (ASCII odd)
M → ASCII 77, index 3 → 77*3 → included
E → ASCII 69, index 4 → 69*4 → included (ASCII odd)
S → ASCII 83, index 5 → 83*5 → included
```

Total = **1126**

### Output:
```
1126
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public int LuckyNumber(string word)
    {
        int total = 0;

        for (int i = 0; i < word.Length; i++)
        {
            int index = i + 1;
            int ascii = (int)word[i];
            int product = ascii * index;

            if (index % 2 == 1 || ascii % 2 == 1)
            {
                total += product;
            }
        }

        return total;
    }
}

class Program
{
    static void Main(string[] args)
    {
        int len = Convert.ToInt32(Console.ReadLine());
        string word = Console.ReadLine();

        Solution sol = new Solution();
        Console.WriteLine(sol.LuckyNumber(word));
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(N)  
- **Space Complexity:** O(1)

---
---


<a id="q-csharp-11"></a>

<a id="q-csharp-12"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-11"></a>
# 🚀 Programming Question — Reverse Array Based on Half-Sum Comparison

## 📌 Problem Description
Write a program that:

1. Calculates the **sum of the first half** of an array.  
2. Calculates the **sum of the second half** of the array.  
3. If the **first half sum is less than the second half sum**, the program must  
   **reverse the entire array**.  
4. Finally, print the resulting array.

Assume the array contains an **even number of elements**.

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void CheckAndReverse(int[] arr)
    {
        int n = arr.Length;
        int mid = n / 2;

        int sum1 = 0, sum2 = 0;

        for (int i = 0; i < mid; i++)
            sum1 += arr[i];

        for (int i = mid; i < n; i++)
            sum2 += arr[i];

        if (sum1 < sum2)
        {
            Array.Reverse(arr);
        }

        foreach (int x in arr)
        {
            Console.Write(x + " ");
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        int[] arr = { 1, 2, 3, 4, 5, 6 };
        Solution sol = new Solution();
        sol.CheckAndReverse(arr);
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(1)

---
---



<a id="q-csharp-12"></a>

<a id="q-csharp-13"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-12"></a>
# 🍕 Programming Question — Generate Bill for Vohra's Purchase

## 📌 Problem Description
Vohra went to a movie with his friends at Wave Theatre.  
During the break, he purchased the following items:

- **Pizza** — ₹100 each  
- **Puffs** — ₹20 each  
- **Cool Drink** — ₹10 each  

Write a program to **read the quantity** of pizzas, puffs, and cool drinks purchased and **generate the total bill**.

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void GenerateBill()
    {
        Console.Write("Enter number of Pizzas: ");
        int pizzas = Convert.ToInt32(Console.ReadLine());

        Console.Write("Enter number of Puffs: ");
        int puffs = Convert.ToInt32(Console.ReadLine());

        Console.Write("Enter number of Cool Drinks: ");
        int coolDrinks = Convert.ToInt32(Console.ReadLine());

        int total = (pizzas * 100) + (puffs * 20) + (coolDrinks * 10);

        Console.WriteLine("\n--- Bill Details ---");
        Console.WriteLine("Pizzas: " + pizzas);
        Console.WriteLine("Puffs: " + puffs);
        Console.WriteLine("Cool Drinks: " + coolDrinks);
        Console.WriteLine("Total Price = Rs." + total);
    }
}

class Program
{
    static void Main(string[] args)
    {
        Solution sol = new Solution();
        sol.GenerateBill();
    }
}
```

---

# 🎯 Sample Output
```
Enter number of Pizzas: 2
Enter number of Puffs: 3
Enter number of Cool Drinks: 4

--- Bill Details ---
Pizzas: 2
Puffs: 3
Cool Drinks: 4
Total Price = Rs. 280
```

---
---



<a id="q-csharp-13"></a>

<a id="q-csharp-14"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-13"></a>
# 🔢 Programming Question — Prime Number Check

## 📌 Problem Description
Write a program to check whether a given number is a **prime number** or not.

A number is prime if:
- It is greater than 1  
- It is divisible only by **1 and itself**

### Example:
**Input:**  
```
5
```

**Output:**  
```
Prime Number
```

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void CheckPrime(int n)
    {
        if (n <= 1)
        {
            Console.WriteLine("Not Prime");
            return;
        }

        for (int i = 2; i <= Math.Sqrt(n); i++)
        {
            if (n % i == 0)
            {
                Console.WriteLine("Not Prime");
                return;
            }
        }

        Console.WriteLine("Prime Number");
    }
}

class Program
{
    static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine());
        Solution sol = new Solution();
        sol.CheckPrime(n);
    }
}
```

---

# 🎯 Sample Output
```
Prime Number
```

---

---



<a id="q-csharp-14"></a>

<a id="q-csharp-15"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-14"></a>
# ⭐ Programming Question — Print Left-Aligned Star Triangle

## 📌 Problem Statement
Write a program to print the following **star pattern**, where each row contains an increasing number of stars:

```
*
* *
* * *
* * * *
* * * * *
```

The number of rows should be based on user input.

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void PrintPattern(int n)
    {
        for (int i = 1; i <= n; i++)
        {
            for (int j = 1; j <= i; j++)
            {
                Console.Write("* ");
            }
            Console.WriteLine();
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine());
        Solution sol = new Solution();
        sol.PrintPattern(n);
    }
}
```

---
---



<a id="q-csharp-15"></a>

<a id="q-csharp-16"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-15"></a>
# 🚀 Programming Question — Maximum Subarray Sum

## 📌 Problem Description
You are given an integer array **nums**.  
Your task is to find the **subarray with the largest sum** and return **that sum**.

A subarray is a **contiguous** part of the array.

### Example
Input:
```
nums = [-2, 1, -3, 4, -1, 2, 1, -5, 4]
```

Maximum sum subarray is:
```
[4, -1, 2, 1]
```

Output:
```
6
```

---

# ✅ C# Solution (Kadane’s Algorithm)
```csharp
using System;

public class Solution
{
    public int MaxSubArray(int[] nums)
    {
        int maxSum = nums[0];
        int currentSum = nums[0];

        for (int i = 1; i < nums.Length; i++)
        {
            currentSum = Math.Max(nums[i], currentSum + nums[i]);
            maxSum = Math.Max(maxSum, currentSum);
        }

        return maxSum;
    }
}

class Program
{
    static void Main(string[] args)
    {
        int[] nums = { -2, 1, -3, 4, -1, 2, 1, -5, 4 };
        Solution sol = new Solution();
        Console.WriteLine(sol.MaxSubArray(nums));  // Output: 6
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(n)  
- **Space Complexity:** O(1)

---
---



<a id="q-csharp-16"></a>

<a id="q-csharp-17"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-16"></a>
# 🔢 Programming Question — Check Buzz Number

## 📌 Problem Description
A **Buzz Number** is a number that satisfies **at least one** of the following conditions:

1. The number **ends with digit 7**  
2. The number is **divisible by 7**

Examples:
- **7** → Buzz number (divisible by 7)  
- **107** → Buzz number (ends with 7)  
- **147** → Buzz number (ends with 7 and divisible by 7)

Write a program to check whether a given number is a **Buzz Number** or not.

---

# ✅ C# Solution
```csharp
using System;

public class Solution
{
    public void CheckBuzz(int n)
    {
        if (n % 7 == 0 || n % 10 == 7)
        {
            Console.WriteLine("Buzz Number");
        }
        else
        {
            Console.WriteLine("Not a Buzz Number");
        }
    }
}

class Program
{
    static void Main(string[] args)
    {
        int n = Convert.ToInt32(Console.ReadLine());
        Solution sol = new Solution();
        sol.CheckBuzz(n);
    }
}
```

---

# 🎯 Sample Outputs
```
Input: 107
Output: Buzz Number
```

```
Input: 20
Output: Not a Buzz Number
```

---
---


---

<a id="q-csharp-18"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-csharp-17"></a>
# 🚀 Programming Question — Minimum Operations to Form a Permutation

## 📌 Problem Description
You are given an integer array **A** of length **N**, where **two integers are repeated** (i.e., exactly two numbers appear twice in the array).

Your goal is to transform the array into a **valid permutation of integers from 1 to N** using the following operation:

### **Allowed Operation**
- In one operation, you may **choose any element** of the array and **increase its value by 1**.

### **Task**
Return the **minimum number of operations** required to convert the array into a **valid permutation** of size **N**.

---

## 🧠 Example

### Sample Input:
```
A = [1, 1, 3, 3, 4]
```

### Required permutation:
```
[1, 2, 3, 4, 5]
```

### Explanation:
- Duplicate 1 → needs to become 2 (1 operation)
- Duplicate 3 → needs to become 5 (2 operations)

Total operations = **3**

### Sample Output:
```
3
```

---

# ✅ C# Solution
```csharp
using System;
using System.Linq;

public class Solution
{
    public int MinOperations(int[] A)
    {
        int n = A.Length;
        Array.Sort(A);

        int ops = 0;
        int expected = 1;

        for (int i = 0; i < n; i++)
        {
            if (A[i] < expected)
            {
                // Need to increase A[i] up to expected
                ops += (expected - A[i]);
            }
            else if (A[i] > expected)
            {
                // Move expected forward (A already sorted)
                expected = A[i];
            }

            expected++;
        }

        return ops;
    }
}

class Program
{
    static void Main(string[] args)
    {
        int[] A = { 1, 1, 3, 3, 4 };
        Solution sol = new Solution();
        Console.WriteLine(sol.MinOperations(A));  // Output: 3
    }
}
```

---

# 🎯 Complexity
- **Time Complexity:** O(N log N)  
- **Space Complexity:** O(1)  

---

---



<a id="q-webui-4"></a>

# 🗄️ SQL Questions

---

<a id="q-sql-1"></a>
# 🗄️ SQL Questions

---

<a id="q-sql-1"></a>

<a id="q-sql-2"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

# 🗄️ SQL Questions

---

<a id="q-sql-1"></a>
# 🏥 SQL Question — Outstanding Amount

Write a SQL query to display **PatientID, PaymentStatus, and OutstandingAmount**  
(where `OutstandingAmount = TotalAmount - PaidAmount`)  
for patients whose **PaidAmount < TotalAmount**.

# ✅ SQL Query
```sql
SELECT 
    PatientID,
    PaymentStatus,
    (TotalAmount - PaidAmount) AS OutstandingAmount
FROM Patient
WHERE PaidAmount < TotalAmount;
```

---

---


<a id="q-sql-2"></a>

<a id="q-sql-3"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-2"></a>
# 🧾 SQL Question — Second Highest Salary (2023)

Write a SQL query to find the **second highest salary** from the Employee table.

# ✅ SQL Query
```sql
SELECT MAX(salary) AS SecondHighestSalary
FROM Employee
WHERE salary < (SELECT MAX(salary) FROM Employee);
```

---
---


<a id="q-sql-3"></a>

<a id="q-sql-4"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-3"></a>
# 🧾 SQL Question — Third Highest Salary

Write a SQL query to find the **third highest salary** from the Employee table.

# ✅ SQL Query
```sql
SELECT MIN(salary) AS ThirdHighestSalary
FROM (
    SELECT DISTINCT salary
    FROM Employee
    ORDER BY salary DESC
    LIMIT 3
) AS t;
```

---
---



<a id="q-sql-4"></a>

<a id="q-sql-5"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-4"></a>
# 🧾 SQL Question — Names Ending With "ed"

Write a SQL query to display all names that **end with 'ed'**.

# ✅ SQL Query
```sql
SELECT Name
FROM Employees
WHERE Name LIKE '%ed';
```
---
--


<a id="q-sql-5"></a>

<a id="q-sql-6"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-5"></a>
# 🧾 SQL Question — Count Employees Department-Wise (2022)

Write a SQL query to count the **number of employees in each department**.

# ✅ SQL Query
```sql
SELECT 
    Department,
    COUNT(*) AS EmployeeCount
FROM Employees
GROUP BY Department;
```

---
---


<a id="q-sql-6"></a>

<a id="q-sql-7"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-6"></a>
# 🧾 SQL Question — Departments With More Than One Employee

Write a SQL query to display only those **departments that have more than one employee**.

# ✅ SQL Query
```sql
SELECT 
    Department
FROM Employees
GROUP BY Department
HAVING COUNT(*) > 1;
```


---
---



<a id="q-sql-7"></a>

<a id="q-sql-8"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-7"></a>
# 🎵 SQL Question — Artist Followers (2018 or Later)

## 📌 Problem Description
You are given two tables:

### **Artist**
- ArtistID  
- ArtistName  

### **Followers**
- FollowerID  
- ArtistID  
- FollowYear  

Write a SQL query to display:

- Each **artist's name**
- The **number of followers** who started following the artist in **2018 or later**

The output must include **all artists**, even those who have **zero followers** in that period.  
For artists with no followers since 2018, display the follower count as **0**.

### **Output Format**
```
ArtistName | Followers
```

---

# ✅ SQL Query
```sql
SELECT 
    a.ArtistName,
    COUNT(f.FollowerID) AS Followers
FROM Artist a
LEFT JOIN Followers f
    ON a.ArtistID = f.ArtistID
    AND f.FollowYear >= 2018
GROUP BY a.ArtistName;
```

---
---



<a id="q-sql-8"></a>

<a id="q-sql-9"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-8"></a>
# 👥 SQL Question — Users Following at Least 5 Others

## 📌 Problem Statement
Write an SQL query to display the **FollowerID**, **FirstName**, **LastName**, and the **count of users they follow**, but only for users who **follow at least 5 other users**.

Assume:
- `Users(UserID, FirstName, LastName)`
- `Followers(FollowerID, FollowingID)`  
  (FollowerID follows FollowingID)

---

# ✅ SQL Query
```sql
SELECT 
    u.UserID AS FollowerID,
    u.FirstName,
    u.LastName,
    COUNT(f.FollowingID) AS FollowingCount
FROM Users u
JOIN Followers f
    ON u.UserID = f.FollowerID
GROUP BY u.UserID, u.FirstName, u.LastName
HAVING COUNT(f.FollowingID) >= 5;
```


---
---



<a id="q-sql-9"></a>

<a id="q-sql-10"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-9"></a>
# 🧾 SQL Question — Employees Joined Recently or Between Jan–Mar

## 📌 Problem Statement
Write a MySQL query to find all employees who satisfy **either** of the following conditions:

1. They joined **within the last 2 months** from today's date.  
2. They joined **between January and March** (any year).

Assume the table:

```
Employees(EmployeeID, FirstName, LastName, JoinDate)
```

You must return all employees matching **either** condition.

---

# ✅ SQL Query
```sql
SELECT *
FROM Employees
WHERE 
    JoinDate >= DATE_SUB(CURDATE(), INTERVAL 2 MONTH)
    OR MONTH(JoinDate) BETWEEN 1 AND 3;
```

---


----



<a id="q-sql-10"></a>

<a id="q-sql-11"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-10"></a>
# 🧾 SQL Question — Employee Leave Summary

## 📌 Problem Statement
Write a single SQL query to return the **Employee ID**, **Leave Type**, and **Total Leaves** for employees who:

- Have taken **more than 10 leaves**
- Have a leave type of **'CL'** (Casual Leave) or **'ML'** (Medical Leave)

Your output must contain the columns:

```
EMPID | LEAVE_TYPE | TOTAL_LEAVES
```

Assume the table structure:
```
Leaves(EMPID, LeaveType, LeaveCount)
```

---

# ✅ SQL Query
```sql
SELECT 
    EMPID,
    LeaveType AS LEAVE_TYPE,
    SUM(LeaveCount) AS TOTAL_LEAVES
FROM Leaves
WHERE LeaveType IN ('CL', 'ML')
GROUP BY EMPID, LeaveType
HAVING SUM(LeaveCount) > 10;
```

---
---



<a id="q-sql-11"></a>

<a id="q-sql-12"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-11"></a>
# 🧾 SQL Question — Employee Details With House Rent Allowance

## 📌 Problem Statement
Write an SQL query to display the following for employees who work in departments located in **BANGALORE** or **COCHIN**:

- Employee ID  
- Employee Name  
- Department Name  
- House Rent Allowance  

Your output must have the following columns:

```
EMPID | EMPNAME | DEPTNAME | HOUSE_RENT_ALLOWANCE
```

Assume the tables:

```
employee (EMPID, EMPNAME, DEPTID, HOUSE_RENT_ALLOWANCE)
dept_info (DEPTID, DEPTNAME, LOCATION)
```

---

# ✅ SQL Query
```sql
SELECT 
    e.EMPID,
    e.EMPNAME,
    d.DEPTNAME,
    e.HOUSE_RENT_ALLOWANCE
FROM employee e
JOIN dept_info d
    ON e.DEPTID = d.DEPTID
WHERE d.LOCATION IN ('BANGALORE', 'COCHIN');
```

---
---


<a id="q-sql-12"></a>

<a id="q-sql-13"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-12"></a>
# 🧾 SQL Question — Album Reviews With Rating 5

## 📌 Problem Statement
Write an SQL query to display the following details **for albums that have a rating of 5**:

- User ID  
- Rating  
- Album Comment  

Your output must contain the following columns:

```
USER_ID | RATING | A_COMMENT
```

Assume the table:

```
AlbumReviews(USER_ID, RATING, A_COMMENT, ALBUM_ID)
```

---

# ✅ SQL Query
```sql
SELECT 
    USER_ID,
    RATING,
    A_COMMENT
FROM AlbumReviews
WHERE RATING = 5;
```

---

---



<a id="q-sql-13"></a>

<a id="q-sql-14"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-13"></a>
# 🛫 SQL Question — Upcoming Flight Details (After 2024-02-06)

## 📌 Problem Statement
Write an SQL query to display the following details for all flights **departing after `2024-02-06`**:

- FLIGHT_ID  
- DEPARTURE_DATE  
- DEPARTURE_TIME  
- FLIGHT_FROM  
- FLIGHT_TO  

Sort the result by **DEPARTURE_TIME** in **ascending** order.

Your output must contain the columns:

```
FLIGHT_ID | DEPARTURE_DATE | DEPARTURE_TIME | FLIGHT_FROM | FLIGHT_TO
```

Assume the table:

```
Flights(FLIGHT_ID, DEPARTURE_DATE, DEPARTURE_TIME, FLIGHT_FROM, FLIGHT_TO)
```

---

# ✅ SQL Query
```sql
SELECT 
    FLIGHT_ID,
    DEPARTURE_DATE,
    DEPARTURE_TIME,
    FLIGHT_FROM,
    FLIGHT_TO
FROM Flights
WHERE DEPARTURE_DATE > '2024-02-06'
ORDER BY DEPARTURE_TIME ASC;
```

---
---


<a id="q-sql-14"></a>

<a id="q-sql-15"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-14"></a>
# 🧾 SQL Question — Patients With Outstanding Amount

## 📌 Problem Statement
Write an SQL query to display the following details for patients **whose bill has not been fully paid**, meaning:

```
PaidAmount < TotalAmount
```

Your output must include:

- PATIENTID  
- PAYMENTSTATUS  
- OUTSTANDING AMOUNT (calculated as `TotalAmount - PaidAmount`)  
- Use the alias **OutstandingAmount** for the calculated column.

The final output format should be:

```
PATIENTID | PAYMENTSTATUS | OUTSTANDING_AMOUNT
```

Assume the table:

```
Patients(PatientID, PaymentStatus, TotalAmount, PaidAmount)
```

---

# ✅ SQL Query
```sql
SELECT 
    PatientID,
    PaymentStatus,
    (TotalAmount - PaidAmount) AS OutstandingAmount
FROM Patients
WHERE PaidAmount < TotalAmount;
```

---
---



<a id="q-sql-15"></a>

<a id="q-sql-16"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-15"></a>
# 💬 SQL Question — Top 5 Users by Messages Sent

## 📌 Problem Statement
Write an SQL query to display the **UserID**, **FirstName**, **LastName**, and the **number of messages sent** by the **top 5 users** who have sent the most messages.

Requirements:
- Count how many messages each user has sent  
- Sort the users by **UserID in descending order**  
- Output must include the following columns:

```
UserID | FirstName | LastName | MessagesSent
```

Assume the tables:

```
Users(UserID, FirstName, LastName)
Messages(MessageID, SenderID, Content)
```

---

# ✅ SQL Query
```sql
SELECT 
    U.UserID,
    U.FirstName,
    U.LastName,
    COUNT(M.MessageID) AS MessagesSent
FROM Users U
JOIN Messages M
    ON U.UserID = M.SenderID
GROUP BY U.UserID, U.FirstName, U.LastName
ORDER BY U.UserID DESC
LIMIT 5;
```

---
---


<a id="q-sql-16"></a>

<a id="q-sql-17"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-16"></a>
# 🧾 SQL Question — Staff Salary Filter

## 📌 Problem Statement
Write an SQL query to display the **first name**, **position**, and **salary** of staff members whose salary is **greater than $50,000**.

Use an alias **StaffFirstName** for the `FirstName` column.

Your result must include the following columns:

```
StaffFirstName | Position | Salary
```

Assume the table:

```
Staff(FirstName, Position, Salary)
```

---

# ✅ SQL Query
```sql
SELECT 
    FirstName AS StaffFirstName,
    Position,
    Salary
FROM Staff
WHERE Salary > 50000;
```

---
--



<a id="q-sql-17"></a>

<a id="q-sql-18"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-17"></a>
# 🧾 SQL Question — Combine Results of Multiple SELECT Statements

## 📌 Problem Statement
Write an SQL query to **combine the result sets** of two or more `SELECT` statements.  
Use the `UNION` operator to merge results while removing duplicate rows.

---

# ✅ SQL Query
```sql
SELECT columnName FROM Table1
UNION
SELECT columnName FROM Table2;
```

---
---

<a id="q-sql-18"></a>

<a id="q-sql-19"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-18"></a>
# 🧾 SQL Question — Retrieve Rows Within a Date Range

## 📌 Problem Statement
Write an SQL query to retrieve rows from a table where a **date column** falls within a **specified date range**.  
Use the `BETWEEN` operator to filter dates.

---

# ✅ SQL Query
```sql
SELECT columnName 
FROM tableName
WHERE columnName 
BETWEEN '2023-01-01' AND '2023-07-30';
```

---
---

<a id="q-sql-19"></a>

<a id="q-sql-20"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-19"></a>
# 🧾 SQL Question — Retrieve Specific Columns From a Table

## 📌 Problem Statement
Write an SQL query to retrieve **specific columns** (First Name and Last Name) from the `employees` table.

---

# ✅ SQL Query
```sql
SELECT first_name, last_name 
FROM employees;
```

---
--


<a id="q-sql-20"></a>

<a id="q-sql-21"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-20"></a>
# 🧾 SQL Question — Create Employees Table

## 📌 Problem Statement
Write an SQL query to create a table named **`employees`** with the following fields:

- `empld` — integer  
- `empName` — variable-length string  
- `empAge` — integer  
- `empAddress` — variable-length string  
- `empSalary` — integer  

---

# ✅ SQL Query
```sql
CREATE TABLE employees (
    empld INT,
    empName VARCHAR(50),
    empAge INT,
    empAddress VARCHAR(40),
    empSalary INT
);
```

---
---


<a id="q-sql-21"></a>

<a id="q-sql-22"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-21"></a>
# 🧾 SQL Question — Delete All Rows but Keep Table Structure

## 📌 Problem Statement
Write an SQL query to **remove all rows from a table** while **keeping the table structure intact** (i.e., the table should remain, but all data should be deleted).

---

# ✅ SQL Query
```sql
TRUNCATE TABLE tableName;
```

---
---


<a id="q-sql-22"></a>

<a id="q-sql-23"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-22"></a>
# 🧾 SQL Question — Combine Rows Using LEFT JOIN

## 📌 Problem Statement
Write an SQL query to combine data from two tables using a **LEFT JOIN**.  
Retrieve the employee’s **first name** along with the **department name**.

Assume the tables:

```
employees (emp_id, first_name, department_id)
departments (department_id, department_name)
```

The result should display employee details even if the employee does **not** belong to any department.

---

# ✅ SQL Query
```sql
SELECT 
    e.first_name,
    d.department_name
FROM employees e
LEFT JOIN departments d
    ON e.department_id = d.department_id;
```

---
---


<a id="q-sql-23"></a>

<a id="q-sql-24"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-23"></a>
# 🎵 SQL Question — Artist Followers (2018 or Later)

## 📌 Problem Statement
Write an SQL query to display:

- **Artist Name**
- **Number of followers** who started following the artist **in 2018 or later**

Requirements:
- Include **all artists**, even if they have **zero followers** in that period.
- Use **LEFT JOIN** to ensure artists without followers appear with count **0**.
- Output format:

```
ArtistName | Followers
```

Assume the tables:

```
Artist(ArtistID, ArtistName)
Followers(FollowerID, ArtistID, FollowYear)
```

---

# ✅ SQL Query
```sql
SELECT 
    a.ArtistName,
    COUNT(f.FollowerID) AS Followers
FROM Artist a
LEFT JOIN Followers f
    ON a.ArtistID = f.ArtistID
    AND f.FollowYear >= 2018
GROUP BY a.ArtistName;
```

---
---


<a id="q-sql-24"></a>

<a id="q-sql-25"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-24"></a>
# 🧾 SQL Question — Categories Starting With 'M'

## 📌 Problem Statement
Write an SQL query to display the **CategoryID** and **CategoryName** for all categories whose names **start with the letter 'M'**.

Your output should contain the columns:

```
CATEGORYID | CATEGORYNAME
```

Assume the table:

```
Categories(CategoryID, CategoryName)
```

---

# ✅ SQL Query
```sql
SELECT 
    CategoryID,
    CategoryName
FROM Categories
WHERE CategoryName LIKE 'M%';
```

---
---


<a id="q-sql-25"></a>

<a id="q-sql-26"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-25"></a>
# 🧾 SQL Question — Mid-Range Transactions (10k to 50k)

## 📌 Problem Statement
Write an SQL query to display the following details for all transactions where the **transaction amount is greater than 10,000 but less than 50,000**:

- **TransactionID**
- **TransactionAmount**
- **TransactionType**

Your output must contain the columns:

```
TRANSACTION_ID | TRANSACTION_AMOUNT | TRANSACTION_TYPE
```

Assume the table:

```
Transactions(TransactionID, TransactionAmount, TransactionType)
```

---

# ✅ SQL Query
```sql
SELECT 
    TransactionID AS TRANSACTION_ID,
    TransactionAmount AS TRANSACTION_AMOUNT,
    TransactionType AS TRANSACTION_TYPE
FROM Transactions
WHERE TransactionAmount > 10000
  AND TransactionAmount < 50000;
```

---

---


<a id="q-sql-26"></a>

<a id="q-sql-27"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-26"></a>
# 🧾 SQL Question — Customer Details by Account Type

## 📌 Problem Statement
Write an SQL query to display the **first name**, **contact number**, and **balance** of all customers whose **account type starts with 'SA'**.

The output must be **ordered by the customer's first name**.

Your result must contain the columns:

```
FirstName | Contact | Balance
```

Assume the table:

```
Customers(FirstName, Contact, Balance, AccountType)
```

---

# ✅ SQL Query
```sql
SELECT 
    FirstName,
    Contact,
    Balance
FROM Customers
WHERE AccountType LIKE 'SA%'
ORDER BY FirstName;
```

---
---


<a id="q-sql-27"></a>

<a id="q-sql-28"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-27"></a>
# 🧾 SQL Question — Employees With Salary Between 60,000 and 80,000

## 📌 Problem Statement
Write an SQL query to list all employees whose salary is **between 60,000 and 80,000** (inclusive).  
Your output should display the following columns:

```
employee_id | first_name | salary
```

Assume the table:

```
employees(employee_id, first_name, salary)
```

---

# ✅ SQL Query
```sql
SELECT employee_id, first_name, salary
FROM employees
WHERE salary BETWEEN 60000 AND 80000;
```

---
---


<a id="q-sql-28"></a>

<a id="q-sql-29"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-28"></a>
# 🧾 SQL Question — Insert Values Into Employees Table

## 📌 Problem Statement
Write an SQL query to **insert values** into the `employees` table, which contains the following columns:

- `empld`
- `empName`
- `empAge`
- `empAddress`
- `empSalary`

Insert one sample record into the table.

---

# ✅ SQL Query
```sql
INSERT INTO employees (empld, empName, empAge, empAddress, empSalary)
VALUES (1, 'John Doe', 30, 'New York', 55000);
```

---
---


<a id="q-sql-29"></a>

<a id="q-sql-30"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-29"></a>
# 🧾 SQL Question — Average Salary by Job Title

## 📌 Problem Statement
Write an SQL query to calculate the **average salary** for each **job title** in the `employees` table.  
Your output should include:

```
job_title | avg_salary
```

---

# ✅ SQL Query
```sql
SELECT 
    job_title, 
    AVG(salary) AS avg_salary
FROM employees
GROUP BY job_title;
```

---
---


<a id="q-sql-30"></a>

<a id="q-sql-31"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-30"></a>
# 🧾 SQL Question — Count Employees in Each Department

## 📌 Problem Statement
Write an SQL query to count the **number of employees in each department**.  
Your output should include:

```
department_id | employee_count
```

Assume the table:

```
employees(department_id, ...)
```

---

# ✅ SQL Query
```sql
SELECT department_id, COUNT(*) AS employee_count
FROM employees
GROUP BY department_id;
```

---
---


<a id="q-sql-31"></a>

<a id="q-sql-32"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-31"></a>
# 🧾 SQL Question — Retrieve Rows Matching Specific Values

## 📌 Problem Statement
Write an SQL query to retrieve rows from a table where a column matches **any value from a given list**.  
Use the **IN** operator to filter multiple values at once.

---

# ✅ SQL Query
```sql
SELECT columnName
FROM tableName
WHERE columnName IN (Value1, Value2, Value3);
```

---
---


<a id="q-sql-32"></a>

<a id="q-sql-33"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-32"></a>
# 🧾 SQL Question — Find the Sum of Values in a Column

## 📌 Problem Statement
Write an SQL query to calculate the **sum of all values** in a specific column of a table.

---

# ✅ SQL Query
```sql
SELECT SUM(columnName) 
FROM tableName;
```

---


--



<a id="q-sql-33"></a>

<a id="q-sql-34"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-33"></a>
# 🧾 SQL Question — Salary Difference Between Highest and Lowest Paid Employees

## 📌 Problem Statement
Write an SQL query to find the **difference between the highest salary and the lowest salary** among all employees.

The output should contain one column:

```
salary_difference
```

---

# ✅ SQL Query
```sql
SELECT MAX(salary) - MIN(salary) AS salary_difference
FROM employees;
```

---
--



<a id="q-sql-34"></a>

<a id="q-sql-35"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-34"></a>
# 🧾 SQL Question — Join Employees With Their Departments

## 📌 Problem Statement
You are given two tables:

### **employees**
- employee_id  
- first_name  
- last_name  
- department_id  

### **departments**
- department_id  
- department_name  

Write an SQL query to retrieve the **first name**, **last name**, and **department name** of all employees by joining the two tables.

---

# ✅ SQL Query
```sql
SELECT 
    e.first_name,
    e.last_name,
    d.department_name
FROM employees e
JOIN departments d
    ON e.department_id = d.department_id;
```

---
---



<a id="q-sql-35"></a>

<a id="q-sql-36"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-35"></a>
# 🧾 SQL Question — Increase Salary for Employees in Department 5

## 📌 Problem Statement
Write an SQL query to **increase the salary of all employees in department 5 by 10%**.

That means every employee whose `department_id` is **5** should have their salary updated using:

```
new salary = old salary × 1.10
```

---

# ✅ SQL Query
```sql
UPDATE employees
SET salary = salary * 1.10
WHERE department_id = 5;
```

---
---


<a id="q-sql-36"></a>

<a id="q-sql-37"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-sql-36"></a>
# 🧾 SQL Question — Remove Employees With Low Salary

## 📌 Problem Statement
Write an SQL query to **delete all employees** whose salary is **less than 30,000** from the `employees` table.

---

# ✅ SQL Query
```sql
DELETE FROM employees
WHERE salary < 30000;
```

---
--



---

# 🌐 Web UI Questions (HTML/CSS/JavaScript)

---

<a id="q-webui-1"></a>
# 🌐 Web UI Questions (HTML/CSS/JavaScript)

---

<a id="q-webui-1"></a>

<a id="q-webui-2"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

# 🌐 Web UI Questions (HTML/CSS/JavaScript)

---

<a id="q-webui-1"></a>
# 🍎 Fruit Chart — Web Development Task

## 📌 Problem Description
You are developing an interactive **Fruit Chart** to help students learn fruit names.  
The chart includes a **dropdown menu** of fruit names, and when a fruit is selected, the **appropriate fruit image** must appear.

Your task is to complete the HTML, CSS, and JavaScript parts of this feature.

---

## 🎯 Objectives
1. Create a `<select>` dropdown with **id = "fruit-dropdown"** containing exactly these options:
   - Value: `"Apple"` → Text: `apple`
   - Value: `"Banana"` → Text: `banana`
   - Value: `"Cherry"` → Text: `cherry`

2. All fruit images must have:
   ```
   max-width: 300px;
   ```

3. Complete the JavaScript `switch` statement so that selecting:
   - `"Apple"` shows an apple image  
   - `"Banana"` shows a banana image  
   - `"Cherry"` shows a cherry image  

4. **Do NOT change any existing `id` or `name` attributes** in the HTML.

---

# 📄 index.html

```html
<!DOCTYPE html>
<html>
<head>
    <title>Fruit Chart</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>

    <h2>Fruit Chart</h2>

    <select id="fruit-dropdown">
        <option value="">-- Select a fruit --</option>
        <option value="Apple">apple</option>
        <option value="Banana">banana</option>
        <option value="Cherry">cherry</option>
    </select>

    <br><br>

    <img id="fruit-image" src="" alt="Fruit image will appear here">

    <script src="script.js"></script>
</body>
</html>
```

---

# 🎨 styles.css

```css
img {
    max-width: 300px;
}
```

---

# 🧠 script.js

```javascript
const dropdown = document.getElementById("fruit-dropdown");
const fruitImage = document.getElementById("fruit-image");

dropdown.addEventListener("change", function () {
    const selected = dropdown.value;

    switch (selected) {
        case "Apple":
            fruitImage.src = "https://upload.wikimedia.org/wikipedia/commons/1/15/Red_Apple.jpg";
            break;

        case "Banana":
            fruitImage.src = "https://upload.wikimedia.org/wikipedia/commons/8/8a/Banana-Single.jpg";
            break;

        case "Cherry":
            fruitImage.src = "https://upload.wikimedia.org/wikipedia/commons/b/bb/Cherry_Stella444.jpg";
            break;

        default:
            fruitImage.src = "";
            break;
    }
});
```

---

# ✅ Summary
This project demonstrates:
- Dropdown selection handling  
- DOM manipulation using JavaScript  
- Dynamic image updates  
- Basic CSS styling  



----
---


<a id="q-webui-2"></a>

<a id="q-webui-3"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-2"></a>
# 🖼️ Programming Question — Image Showcase Application

## 📌 Problem Description
You are tasked with creating an **Image Showcase Application** where users can view and interact with a set of thumbnail images.

Your job is to complete the HTML, CSS, and JavaScript with the following requirements:

1. Create a division with class **`Image-Display`** where the **selected large image** will be shown.
2. All images with the class **`Thumbnail`** must have:
   - Width: **100px**
   - Height: **70px**
3. When a user **clicks a thumbnail**, the clicked image must be displayed in a larger view with the class **`Selected-Image`**.
4. The application must work successfully using HTML, CSS, and JavaScript.

---

# 📄 index.html
```html
<!DOCTYPE html>
<html>
<head>
    <title>Image Showcase</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>

    <h2>Image Showcase</h2>

    <!-- Thumbnail Gallery -->
    <div class="Gallery">
        <img src="https://via.placeholder.com/400x250/ff7f7f" class="Thumbnail">
        <img src="https://via.placeholder.com/400x250/7fafff" class="Thumbnail">
        <img src="https://via.placeholder.com/400x250/7fff7f" class="Thumbnail">
    </div>

    <!-- Large Image Display -->
    <div class="Image-Display">
        <img id="selectedImage" class="Selected-Image" src="">
    </div>

    <script src="script.js"></script>
</body>
</html>
```

---

# 🎨 styles.css
```css
.Thumbnail {
    width: 100px;
    height: 70px;
    cursor: pointer;
    margin: 5px;
}

.Image-Display {
    margin-top: 20px;
}

.Selected-Image {
    width: 400px;
    height: auto;
    border: 2px solid black;
    display: block;
}
```

---

# 🧠 script.js
```javascript
const thumbnails = document.querySelectorAll(".Thumbnail");
const display = document.getElementById("selectedImage");

thumbnails.forEach(img => {
    img.addEventListener("click", function () {
        display.src = this.src;
    });
});
```

---

# 🎯 Summary
This solution meets all requirements:
- Separate HTML, CSS, JS files  
- Thumbnails styled correctly  
- Large image updates dynamically on click  
- Uses required class names (`Thumbnail`, `Image-Display`, `Selected-Image`)

---
---



<a id="q-webui-3"></a>

<a id="q-webui-4"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-3"></a>
# 🐶🐱 Programming Question — Interactive Animal Display Application

## 📌 Problem Description
You are building an **interactive animal display application** that shows adorable animal images and fun facts.  
The structure is already in place, but functionality must be added so that:

### ✅ Objectives
1. Add the ID **`animal-fact`** to the paragraph element that displays the fun fact.  
2. Add **15px gap** between the buttons using CSS.  
3. Ensure that clicking **Puppy** or **Kitten** buttons updates:
   - The **animal image**
   - The **animal fun fact**

### ⚠️ Constraints
- Do **NOT** modify any existing IDs or class names.  
- Keep all existing styles and features intact.

---

# 📄 index.html
```html
<!DOCTYPE html>
<html>
<head>
    <title>Animal Display</title>
    <link rel="stylesheet" href="styles.css">
</head>

<body>

    <h2>Animal Display</h2>

    <!-- Buttons -->
    <div class="button-container">
        <button id="puppy-btn">Puppy</button>
        <button id="kitten-btn">Kitten</button>
    </div>

    <!-- Image Display -->
    <div class="image-display">
        <img id="animal-image" src="" alt="Animal will appear here">
    </div>

    <!-- Fun Fact Display -->
    <p id="animal-fact">Click a button to see a fun fact!</p>

    <script src="script.js"></script>
</body>
</html>
```

---

# 🎨 styles.css
```css
.button-container {
    display: flex;
    gap: 15px; /* Required spacing */
    margin-bottom: 20px;
}

.image-display img {
    width: 300px;
    height: auto;
    border: 2px solid black;
    display: block;
    margin-top: 20px;
}
```

---

# 🧠 script.js
```javascript
const puppyBtn = document.getElementById("puppy-btn");
const kittenBtn = document.getElementById("kitten-btn");
const animalImg = document.getElementById("animal-image");
const animalFact = document.getElementById("animal-fact");

// Puppy button functionality
puppyBtn.addEventListener("click", function() {
    animalImg.src = "https://place-puppy.com/300x300";
    animalFact.textContent = "Puppies are born blind and deaf but quickly develop their senses!";
});

// Kitten button functionality
kittenBtn.addEventListener("click", function() {
    animalImg.src = "https://placekitten.com/300/300";
    animalFact.textContent = "Kittens start dreaming when they are about one week old!";
});
```

---

---
---


<a id="q-webui-5"></a>

<a id="q-webui-5"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-4"></a>
# 🛒 Programming Question — Build a Product Information Table

## 📌 Problem Statement
Create an HTML table that displays information about products.  
The table must include the following columns:

- **Product Name**  
- **Price**  
- **Availability**

Add sample rows such as:

- *Product A* — *₹1000* — *In Stock*  
- *Product B* — *₹750* — *Out of Stock*

---

# ✅ HTML Code
```html
<table border="1" cellpadding="8">
    <tr>
        <th>Product Name</th>
        <th>Price</th>
        <th>Availability</th>
    </tr>

    <tr>
        <td>Product A</td>
        <td>₹1000</td>
        <td>In Stock</td>
    </tr>

    <tr>
        <td>Product B</td>
        <td>₹750</td>
        <td>Out Of Stock</td>
    </tr>
</table>
```

---
---


<a id="q-webui-6"></a>

<a id="q-webui-6"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-5"></a>
# 📝 HTML Question — Create a Simple Input Form

## 📌 Problem Statement
Design a simple HTML form that contains:

- An input field for **Name**  
- An input field for **Email**  
- An input field for **Age**  
- A **Submit** button  

The form should use proper labels and input types.

---

# ✅ HTML Code
```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Form</title>
</head>

<body>

    <form action="#">
        <label for="name">Name:</label><br>
        <input type="text" id="name" name="name"><br><br>

        <label for="email">Email:</label><br>
        <input type="email" id="email" name="email"><br><br>

        <label for="age">Age:</label<br>
        <input type="number" id="age" name="age"><br><br>

        <input type="submit" value="Submit">
    </form>

</body>
</html>
```

---
---


<a id="q-webui-7"></a>

<a id="q-webui-7"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-6"></a>
# 🌐 HTML Question — Build a Basic Navigation Bar

## 📌 Problem Statement
Create a simple navigation bar that contains links to the following pages:

- **Home**
- **About**
- **Services**
- **Contact**

Use the respective file names in the `href` attributes:
- Home → `index.html`
- About → `about.html`
- Services → `services.html`
- Contact → `contact.html`

---

# ✅ HTML Code
```html
<!DOCTYPE html>
<html>
<head>
    <title>Navigation Bar</title>
</head>

<body>

    <nav>
        <a href="index.html">Home</a> |
        <a href="about.html">About</a> |
        <a href="services.html">Services</a> |
        <a href="contact.html">Contact</a>
    </nav>

</body>
</html>
```

---


---


<a id="q-webui-8"></a>

<a id="q-webui-8"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-7"></a>
# 🌐 HTML Question — Create a Basic HTML Page Structure

## 📌 Problem Statement
Create a simple HTML page with the basic structure including:

- `<!DOCTYPE html>`
- `<html>`
- `<head>` section with meta tags
- `<title>`
- `<body>` section displaying a heading **"Welcome to HTML"**

---

# ✅ HTML Code
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Basic HTML Structure</title>
</head>

<body>
    <h1>Welcome to HTML</h1>
</body>
</html>
```

---
--



<a id="q-webui-9"></a>

<a id="q-webui-9"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-8"></a>
# 📝 JavaScript Question — Change Paragraph Text on Button Click

## 📌 Problem Statement
Write an HTML + JavaScript program to **change the text of a paragraph** when a button is clicked.

---

# ✅ HTML + JavaScript Code
```html
<!DOCTYPE html>
<html>
<head>
    <title>Change Paragraph Text</title>
</head>

<body>

    <p id="myPara">Original Text</p>

    <button onclick="changeText()">Change Text</button>

    <script>
        function changeText() {
            document.getElementById("myPara").innerText = "New Text";
        }
    </script>

</body>
</html>
```

---
---


<a id="q-webui-10"></a>

<a id="q-webui-10"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-9"></a>
# 🌐 HTML Question — Link to an External Website

## 📌 Problem Statement
Write an HTML code snippet to create a link that opens an external website in a **new browser tab**.

---

# ✅ HTML Code
```html
<a href="https://www.example.com" target="_blank">Visit Example</a>
```

---
---



<a id="q-webui-11"></a>

<a id="q-webui-11"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-10"></a>
# 🌄 CSS Question — Add and Center a Background Image

## 📌 Problem Statement
Write a CSS snippet to set a background image for the entire page, ensure it covers the whole screen, and keep it centered.

---

# ✅ CSS Code
```css
body {
    background-image: url('background.jpg');
    background-size: cover;
    background-position: center;
}
```

---
---


<a id="q-webui-12"></a>

<a id="q-webui-12"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-11"></a>
# 🌐 HTML Question — Create a Simple Webpage With Heading and Paragraph

## 📌 Problem Statement
Create a basic HTML page that displays:

- A **heading**  
- A **paragraph**

The page should include the standard HTML structure such as `<!DOCTYPE html>`, `<html>`, `<head>`, `<title>`, and `<body>` tags.

---

# ✅ HTML Code
```html
<!DOCTYPE html>
<html>
<head>
    <title>Simple Page</title>
</head>

<body>
    <h1>Welcome to My Website</h1>
    <p>This is a simple paragraph.</p>
</body>
</html>
```

---
---


<a id="q-webui-13"></a>

<a id="q-webui-13"></a>

[⬆️ Back to Table of Contents](#table-of-contents)

---

<a id="q-webui-12"></a>
# 📝 HTML Question — Create an Ordered and Unordered List

## 📌 Problem Statement
Create an HTML page section that includes:

- An **ordered list (numbered list)**  
- An **unordered list (bullet list)**  

Both lists should contain sample items.

---

# ✅ HTML Code
```html
<h2>Ordered List</h2>
<ol>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
</ol>

<h2>Unordered List</h2>
<ul>
    <li>Item A</li>
    <li>Item B</li>
    <li>Item C</li>
</ul>
```
---
---



---

# 📝 MCQs (C# Multiple Choice Questions)

---

<a id="q-mcq-1"></a>
# 📝 MCQs (C# Multiple Choice Questions)

---

<a id="q-mcq-1"></a>

<a id="q-mcq-2"></a>
# 📝 C# Multiple Choice Questions (MCQs)

---

### **1. What is C# primarily used for in the .NET ecosystem?**  
A) System programming  
B) Web development  
C) Mobile apps  
D) **All of the above**  
**Correct Answer: D**

---

### **2. Who developed C#?**  
A) **Microsoft**  
B) Google  
C) Apple  
D) IBM  
**Correct Answer: A**

---

### **3. Which of the following is a feature of C#?**  
A) Platform dependent  
B) **Garbage collection**  
C) Weakly typed  
D) None of the above  
**Correct Answer: B**

---

### **4. In which year was C# first released?**  
A) **2000**  
B) 2005  
C) 1998  
D) 2010  
**Correct Answer: A**

---

### **5. What type of language is C#?**  
A) Procedural  
B) Functional  
C) **Object-oriented**  
D) All of the above  
**Correct Answer: C**

---

### **6. Which of the following best describes the .NET framework?**  
A) A hardware component  
B) An operating system  
C) **A development platform**  
D) A database management system  
**Correct Answer: C**

---

### **7. Which language influenced the development of C# the most?**  
A) **Java**  
B) Python  
C) C++  
D) PHP  
**Correct Answer: A**

---

### **8. What is the primary runtime used to execute C# programs?**  
A) JVM  
B) **CLR**  
C) Python interpreter  
D) None of the above  
**Correct Answer: B**

---

### **9. Which of the following is the correct way to start a C# console application?**  
A) **public static void Main**  
B) public void Main  
C) static void Main  
D) void Main  
**Correct Answer: A**

---

### **10. If you receive a "namespace not found" error, what is the likely cause?**  
A) Incorrect file extension  
B) **Missing using directive**  
C) Typo in the class name  
D) Missing semicolon  
**Correct Answer: B**

---

### **11. Which keyword is used to define a constant in C#?**  
A) constant  
B) **const**  
C) readonly  
D) static  
**Correct Answer: B**

---

### **12. What is the correct syntax for a single-line comment in C#?**  
A) **// This is a comment**  
B) /* This is a comment */  
C) # This is a comment  
D) -- This is a comment  
**Correct Answer: A**

---

### **13. Which of the following is a valid identifier in C#?**  
A) 1variable  
B) **_variable**  
C) variable#  
D) @variable  
**Correct Answer: B**

---

### **14. How do you declare an integer variable in C#?**  
A) **int number;**  
B) integer number;  
C) var number;  
D) int: number;  
**Correct Answer: A**

---

### **15. Which keyword prevents a class from being inherited?**  
A) **sealed**  
B) static  
C) final  
D) private  
**Correct Answer: A**

---

### **16. What is the output of `Console.WriteLine(10 % 3)`?**  
A) **1**  
B) 3  
C) 0  
D) 10  
**Correct Answer: A**

---

### **17. How do you define a method in C#?**  
A) **void methodName()**  
B) method methodName()  
C) void methodName  
D) function methodName()  
**Correct Answer: A**

---

### **18. How do you write a for loop in C#?**  
A) **for (int i = 0; i < 10; i++)**  
B) for (int i = 0; i < 10)  
C) for i in range 10  
D) for i = 0 to 9  
**Correct Answer: A**

---

### **19. How do you create a new instance of a class?**  
A) **MyClass obj = new MyClass();**  
B) MyClass obj;  
C) MyClass obj = MyClass;  
D) new MyClass obj;  
**Correct Answer: A**

---

### **20. A "missing semicolon" error means:**  
A) **A line is missing a semicolon at the end**  
B) Incorrect class definition  
C) Invalid variable declaration  
D) Incorrect keyword  
**Correct Answer: A**

---

### **21. What can cause a syntax error?**  
A) Missing brackets  
B) Misspelled keywords  
C) Incorrect operators  
D) **All of the above**  
**Correct Answer: D**

---

### **22. Which of the following is a value type?**  
A) string  
B) object  
C) **int**  
D) array  
**Correct Answer: C**

---

### **23. Default value of a boolean variable?**  
A) true  
B) **false**  
C) zero  
D) null  
**Correct Answer: B**

---

### **24. Which is a reference type?**  
A) int  
B) float  
C) double  
D) **string**  
**Correct Answer: D**

---

### **25. Size of int in C#?**  
A) 2 bytes  
B) **4 bytes**  
C) 8 bytes  
D) 16 bytes  
**Correct Answer: B**

---

### **26. Difference between int and double?**  
A) **int is integer, double is floating-point**  
B) int is smaller, double is larger  
C) int is reference type, double is value type  
D) int is immutable, double is mutable  
**Correct Answer: A**

---

### **27. Which data type stores large text efficiently?**  
A) char  
B) string  
C) **StringBuilder**  
D) text  
**Correct Answer: C**

---

### **28. How to define a constant integer?**  
A) constant int x = 10;  
B) **const int x = 10;**  
C) readonly int x = 10;  
D) static int x = 10;  
**Correct Answer: B**

---

### **29. Which is the correct variable assignment?**  
A) **int x = 10;**  
B) int x == 10;  
C) int x: = 10;  
D) int x -> 10;  
**Correct Answer: A**

---

### **30. DIY Question: How do you declare a character variable?**  
A) **char myChar = 'A';**  
B) char myChar = "A";  
C) char myChar = A;  
D) char myChar = 65;  
**Correct Answer: A**

---

----




---

## **1️⃣ Check if a number is a palindrome**
```csharp
public bool IsPalindrome(int n)
{
    int original = n, rev = 0;
    while (n > 0)
    {
        rev = rev * 10 + (n % 10);
        n /= 10;
    }
    return original == rev;
}
```

---

## **2️⃣ Reverse a string without using Reverse()**
```csharp
public string ReverseString(string s)
{
    string rev = "";
    for (int i = s.Length - 1; i >= 0; i--)
        rev += s[i];
    return rev;
}
```

---

## **3️⃣ Find frequency of each character**
```csharp
public void CharFrequency(string s)
{
    Dictionary<char, int> freq = new Dictionary<char, int>();
    foreach (char c in s)
    {
        if (freq.ContainsKey(c))
            freq[c]++;
        else
            freq[c] = 1;
    }

    foreach (var x in freq)
        Console.WriteLine(x.Key + " = " + x.Value);
}
```

---

## **4️⃣ Remove duplicates from an array**
```csharp
public int[] RemoveDuplicates(int[] arr)
{
    return arr.Distinct().ToArray();
}
```

---

## **5️⃣ Find second largest element**
```csharp
public int SecondLargest(int[] arr)
{
    Array.Sort(arr);
    return arr[arr.Length - 2];
}
```

---

## **6️⃣ Check if two strings are anagrams**
```csharp
public bool IsAnagram(string a, string b)
{
    char[] s1 = a.ToCharArray();
    char[] s2 = b.ToCharArray();
    Array.Sort(s1);
    Array.Sort(s2);
    return new string(s1) == new string(s2);
}
```

---

## **7️⃣ Count vowels & consonants**
```csharp
public void CountVowels(string s)
{
    int v = 0, c = 0;
    string vowels = "aeiouAEIOU";

    foreach (char ch in s)
    {
        if (Char.IsLetter(ch))
        {
            if (vowels.Contains(ch)) v++;
            else c++;
        }
    }
    Console.WriteLine("Vowels=" + v + " Consonants=" + c);
}
```

---

## **8️⃣ Fibonacci series up to N**
```csharp
public void Fibonacci(int n)
{
    int a = 0, b = 1, c;
    Console.Write(a + " " + b + " ");
    for (int i = 2; i < n; i++)
    {
        c = a + b;
        Console.Write(c + " ");
        a = b;
        b = c;
    }
}
```

---

## **9️⃣ Sum of digits of a number**
```csharp
public int SumDigits(int n)
{
    int sum = 0;
    while (n > 0)
    {
        sum += n % 10;
        n /= 10;
    }
    return sum;
}
```

---

## **🔟 Implement Linear Search**
```csharp
public int LinearSearch(int[] arr, int target)
{
    for (int i = 0; i < arr.Length; i++)
        if (arr[i] == target)
            return i;
    return -1;
}
```

---

## **1️⃣1️⃣ Implement Binary Search**
```csharp
public int BinarySearch(int[] arr, int x)
{
    int l = 0, r = arr.Length - 1;
    while (l <= r)
    {
        int mid = (l + r) / 2;
        if (arr[mid] == x) return mid;
        else if (arr[mid] < x) l = mid + 1;
        else r = mid - 1;
    }
    return -1;
}
```

---

## **1️⃣2️⃣ Missing number in array (1…N)**
```csharp
public int MissingNumber(int[] nums, int n)
{
    int expected = n * (n + 1) / 2;
    int actual = nums.Sum();
    return expected - actual;
}
```

---

## **1️⃣3️⃣ Move all zeros to end**
```csharp
public int[] MoveZeros(int[] arr)
{
    int index = 0;
    foreach (int num in arr)
        if (num != 0)
            arr[index++] = num;

    while (index < arr.Length)
        arr[index++] = 0;

    return arr;
}
```

---

## **1️⃣4️⃣ Check leap year**
```csharp
public bool IsLeapYear(int year)
{
    return (year % 400 == 0) || 
           (year % 4 == 0 && year % 100 != 0);
}
```

---
---







---


[⬆️ Back to Table of Contents](#table-of-contents)

---

