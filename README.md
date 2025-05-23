
# Generating Perfect Numbers

In UWindsor’s **COMP1400 Lab 3**, one of the exercises asked us to generate all **perfect numbers** between a given input range from **A to B**.

The lab provided pseudocode for a helper function `isPerfect()`, which checks whether a number is perfect. A naïve approach would be to loop through all values from **A to B**, checking each value using this function.

---

## 🧮 isPerfect() Pseudocode

```
Function isPerfect(n):
    sum ← 1
    divisor ← 2

    While divisor ≤ n / 2:
        If n mod divisor = 0:
            sum ← sum + divisor
        divisor ← divisor + 1

    If sum = n AND n ≠ 1:
        Return true
    Else:
        Return false
```

---

## ⏱️ Naïve Time Complexity

Let **N = B - A**, which is the number of values being checked.

- For a single number `x`, the function runs in **O(x / 2)** time.
- Therefore, the total time complexity for checking all numbers from **A to B** is approximately:

```
O(N * (x / 2)) ≈ O(N * N) = O(N²)
```

This quadratic time becomes infeasible for large ranges.

---

## ⚡ Optimized Approach

To solve this more efficiently, I used **number theory** — specifically:

- **Mersenne Primes**
- **Sieve of Eratosthenes** (a classic prime number generator used in cryptography)

Using this method, the time complexity drops to:

```
O(n * log(log(n)))
```

Which is **dramatically faster** than O(n²) for large input sizes.

---

## 🧪 How to Run the Code

You can find the optimized implementation in `generate_perfects.cpp`.

### 🛠️ Compile:
```bash
g++ -std=c++11 generate_perfects.cpp -o out.exe
```

### ▶️ Run:
```bash
./out.exe
```

---

## 📸 Sample Output

Running the optimized algorithm from 0 to 100,000 produces output like:

```
<img width="817" alt="generate_perfect_nums_output" src="https://github.com/user-attachments/assets/47697839-b4e3-4e99-9b6e-7f5bde59b1c3" />
```

- Naïve approach: **~11 seconds**
- Optimized algorithm: **~0.004 seconds**

---

## 📄 Further Reading

Refer to `generate_perfect_nums.pdf` (included in this repository) for:

- Intuition behind the optimization
- The algorithm's design and improvements
- A full **mathematical proof** of correctness and complexity

---

**Cheers! 🎉**
