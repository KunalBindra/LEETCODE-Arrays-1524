# LEETCODE-Arrays-1524
**Explanation:**

**Key Idea:**

- The code maintains two counters:
    - `Ecount`: Counts the number of subarrays ending at the current index with an even sum.
    - `Ocount`: Counts the number of subarrays ending at the current index with an odd sum.
- The code iterates through the array and updates `Ecount` and `Ocount` based on the running sum `sum`.
- If the running sum is even, it means all odd-sum subarrays ending at the previous index are now odd-sum subarrays ending at the current index.
- If the running sum is odd, it means all even-sum subarrays ending at the previous index are now odd-sum subarrays ending at the current index.
- The `count` variable accumulates the number of odd-sum subarrays.
- The modulo operation `% M` is used to prevent integer overflow.

**Dry Run Example:**

Let's consider the input array `arr = [1, 3, 5]`

1. **Initialization:**
   - `n = 3`, `count = 0`, `Ecount = 1`, `Ocount = 0`, `sum = 0`, `M = 1000000007`

2. **Iteration:**
   - **i = 0:**
      - `sum = 0 + 1 = 1`
      - `sum % 2 != 0` (odd)
      - `count = (0 + 1) % M = 1`
      - `Ocount = 0 + 1 = 1`
   - **i = 1:**
      - `sum = 1 + 3 = 4`
      - `sum % 2 == 0` (even)
      - `count = (1 + 1) % M = 2`
      - `Ecount = 1 + 1 = 2`
   - **i = 2:**
      - `sum = 4 + 5 = 9`
      - `sum % 2 != 0` (odd)
      - `count = (2 + 2) % M = 4`
      - `Ocount = 1 + 1 = 2`

3. **Return Result:**
   - `return count = 4`

**Explanation of the Logic:**

- For `arr = [1]`, the odd-sum subarray is `[1]`.
- For `arr = [1, 3]`, the odd-sum subarrays are `[1]`, `[1, 3]`.
- For `arr = [1, 3, 5]`, the odd-sum subarrays are `[1]`, `[1, 3]`, `[5]`, `[3, 5]`.
