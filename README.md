# Diagonal Difference

## 📌 Problem Statement
Given a square matrix `arr` of size `n × n`, calculate the **absolute difference** between the sums of its two diagonals:
- **Primary diagonal** (left to right)
- **Secondary diagonal** (right to left)

---

## 📥 Input
- An integer `n`, the number of rows and columns.
- A 2D integer matrix `arr` of size `n × n`.

---

## 📤 Output
- Return a single integer representing the absolute diagonal difference.

---

## 🧠 Approach
To solve this problem efficiently:

- Traverse the matrix **once** using a single loop.
- For each index `i`:
  - Add `arr[i][i]` to the **primary diagonal sum**
  - Add `arr[i][n - 1 - i]` to the **secondary diagonal sum**
- Return the absolute difference between the two sums.

This approach avoids unnecessary nested loops and works for **any square matrix size**.

---

## 🧮 Algorithm
1. Initialize two variables `sum1` and `sum2` to `0`.
2. Let `n` be the size of the matrix.
3. Loop from `i = 0` to `n - 1`:
   - `sum1 += arr[i][i]`
   - `sum2 += arr[i][n - 1 - i]`
4. Return `abs(sum1 - sum2)`.

---

## 💻 Java Implementation

```java
public static int diagonalDifference(List<List<Integer>> arr) {
    int n = arr.size();
    int sum1 = 0;
    int sum2 = 0;

    for (int i = 0; i < n; i++) {
        sum1 += arr.get(i).get(i);
        sum2 += arr.get(i).get(n - 1 - i);
    }

    return Math.abs(sum1 - sum2);
}
